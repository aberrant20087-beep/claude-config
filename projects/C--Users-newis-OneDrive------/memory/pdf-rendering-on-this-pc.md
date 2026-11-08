---
name: pdf-rendering-on-this-pc
description: 이 PC에서 Claude는 PDF를 직접 못 읽음 — PROJECT_SEOL\tools\render.ps1로 PNG 변환 후 읽을 것
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 223ea91e-29fb-44ef-a776-7521c66966fa
  modified: 2026-08-18T00:56:42.303Z
---

이 PC에는 `pdftoppm`(poppler)이 없어서 **Read 도구로 PDF를 열면 실패한다.**
그래서 사용자는 지금까지 도면을 볼 때마다 직접 캡처를 떠서 넘겨야 했다.

해결책으로 `PROJECT_SEOL\tools\render.ps1`을 만들어 두었다. Windows 내장
`Windows.Data.Pdf` WinRT API로 PDF를 PNG로 렌더링하므로 추가 설치가 필요 없다.

```
powershell -File tools\render.ps1 "명인제약 Generation"          # 파일명 일부로 검색
powershell -File tools\render.ps1 "명인제약 Generation" -Tiles 2  # 4분할 확대
powershell -File tools\render.ps1 -List
```
결과는 `data\_render\*.png`. 그 경로를 Read 로 읽으면 도면이 그대로 보인다.

**Why:** 사용자가 명시적으로 "캡처 없이 네가 직접 볼 수 있는 프로그램을 만들어 달라"고 요청했다.
캡처를 요구하는 것은 이제 불필요한 부담이다.

**How to apply:** 도면 · PDF 를 봐야 하면 사용자에게 캡처를 요청하지 말고 render.ps1 을 먼저 실행한다.
P&ID 의 밸브 태그 · 배관 규격 같은 작은 글씨는 기본 배율로는 부정확하니 `-Tiles 2` 이상으로 확대할 것.
(2000px 단일 렌더에서는 표제란과 장비 리스트 정도가 확실하게 읽힌다.)

관련: [[project-seol]], [[powershell-korean-bom]]
