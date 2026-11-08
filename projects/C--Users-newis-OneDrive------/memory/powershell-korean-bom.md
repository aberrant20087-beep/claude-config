---
name: powershell-korean-bom
description: 한글이 든 .ps1은 UTF-8 BOM 필수, .bat 내용에는 한글을 절대 넣지 말 것 (PowerShell 5.1 / cmd.exe)
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 223ea91e-29fb-44ef-a776-7521c66966fa
  modified: 2026-08-18T00:59:32.452Z
---

## .bat 에는 한글을 넣지 말 것 (더 심각한 함정)

cmd.exe 는 배치 파일을 **OEM 코드페이지**로 읽는다. UTF-8 로 저장된 한글이 들어가면
멀티바이트 시퀀스가 깨지면서 **줄 구조 자체가 무너져** 엉뚱한 토큰이 명령으로 실행된다.
실제로 `PROJECT SEOL 열기.bat` 에 한글 echo 를 넣었더니 `'rver.ps1'`, `'-ExecutionPolicy'`,
`'/b'` 가 각각 명령어로 해석되며 홈페이지가 아예 실행되지 않았다.
`chcp 65001` 을 맨 앞에 넣어도 신뢰할 수 없다.

**해결:** .bat 은 순수 ASCII 로만 유지하고, 한글 안내 메시지는 .bat 이 호출하는
PowerShell 스크립트(`tools\start.ps1` 패턴)에서 출력한다. 파일명에 한글이 있는 건 괜찮고
내용만 문제다. 저장 후 `([System.IO.File]::ReadAllBytes($bat) | ? { $_ -gt 127 }).Count` 가
0 인지 검증할 것.

## 한글 .ps1 은 UTF-8 BOM 필수

이 환경의 PowerShell은 Windows PowerShell 5.1이라, BOM 없는 `.ps1` 파일을 시스템 ANSI
코드페이지(CP949)로 읽는다. 한글 문자열 리터럴이나 한글 경로(`G:\내 드라이브`)가 들어간
스크립트를 Write 도구로 저장하면 UTF-8 BOM 없이 저장되어 문자열이 깨진다.

**Why:** 실제로 `PROJECT_SEOL\tools\sync.ps1`에서 `(최상위)` 문자열이 깨져 출력되고
드라이브 경로도 잘못 해석될 뻔했다. 실행은 되지만 결과물만 조용히 망가지는 유형이라
발견이 늦어진다.

**How to apply:** 한글이 든 .ps1을 만든 뒤 다음으로 BOM을 붙인다.
```
$c = Get-Content $p -Raw -Encoding UTF8
[System.IO.File]::WriteAllText($p, $c, (New-Object System.Text.UTF8Encoding $true))
```
반대로 다른 도구가 읽을 파일을 스크립트에서 쓸 때는 BOM 없는 UTF-8
(`New-Object System.Text.UTF8Encoding $false`)을 쓴다.

또한 이 PC의 `python`은 Windows Store 스텁이라 실제로 동작하지 않고 node도 없다.
스크립팅은 PowerShell로 해야 한다.

관련: [[project-seol]]
