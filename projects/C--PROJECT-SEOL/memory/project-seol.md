---
name: project-seol
description: "PROJECT SEOL — 사용자의 개인 업무 워크스페이스 (C:\\PROJECT_SEOL), 구글 드라이브 자료 + 홈페이지 + Claude cowork 환경"
metadata: 
  node_type: memory
  type: project
  originSessionId: 223ea91e-29fb-44ef-a776-7521c66966fa
  modified: 2026-08-18T00:19:03.620Z
---

사용자는 `C:\PROJECT_SEOL`에 개인 업무 워크스페이스를 만들고 있다 (2026-08-18 시작).
목적은 현재 회사와 앞으로 다닐 회사에서의 업무 최적화.
(2026-09-25 에 `OneDrive\바탕 화면\claude system\PROJECT_SEOL` 에서 옮겨 왔다.)

구성:
- `index.html` — 자료 검색 · 프로젝트 보드 홈페이지 (자동 생성물, 직접 수정 금지)
- `tools/sync.ps1` — 구글 드라이브(`G:\내 드라이브`) 복사 + 홈페이지 재빌드
- `tools/index.template.html` — 홈페이지 디자인 원본
- `data/drive/` — 드라이브 문서 · 이미지 복사본 (설치파일 zip/exe/bin/msi 약 9.5GB는 제외)
- `docs/` — 사용자가 직접 만드는 결과물
- `CLAUDE.md` — 업무 배경과 문서 작성 규칙

아직 초안 단계이며 사용자가 "지금 당장 완성할 필요는 없다"고 밝혔다. 이어서 할 만한 일:
docs/ 템플릿 채우기, 프로젝트별 진행 상황 트래킹, 문서 자동 생성.

**Why:** 사용자가 자료 위치를 매번 설명하지 않아도 되도록 만든 구조라, 후속 작업에서
이 배치를 그대로 따라야 의미가 있다.
**How to apply:** 이 폴더에서 작업할 때는 `CLAUDE.md`를 먼저 읽고, 결과물은 `docs/`에 만든다.
드라이브에 새 자료가 올라온 뒤에는 `powershell -File tools\sync.ps1`을 실행해 갱신한다.

관련: [[user-gmp-validation-engineer]], [[powershell-korean-bom]]

## 다른 PC 로 이어가기 (2026-09-25 개편)

**일하는 곳과 오가는 길을 나눈다.** 작업 폴더는 각 PC 의 진짜 로컬 디스크
(`C:\PROJECT_SEOL`), 오가는 길은 내 드라이브 안의 bare git 저장소
(`<드라이브>:\내 드라이브\PROJECT_SEOL.git`, 원격 이름 `origin`).
이 PC 안 백업은 `C:\Users\newis\git\PROJECT_SEOL.git` (원격 이름 `local`).
주고받기는 `GIT SYNC.bat` — 담기 → 받기 → 보내기 순이고, 드라이브와 로컬 백업
양쪽에 넣는다. 절차 전체는 `docs/두 번째 PC 연결.md`.

**동기화 폴더 안에서 직접 일하지 않는다.** `G:` 는 스트리밍 가상 드라이브라
같은 파일 읽기가 92ms 대 8ms 로 10배 넘게 느리고, 두 PC 를 동시에 켜면 구글
드라이브가 `index (1).html` 같은 충돌본을 만든다. bare 저장소는 작업본이 없어
충돌본이 생기지 않는다. 깃허브 등 외부 저장소는 쓰지 않는다 (사용자가 거부).

기억은 저장소를 타지 않으므로 `context/` 에 사본을 두고 `tools/memory.ps1`
(기본=내보내기, `-Import`=되돌리기, `-Root`로 작업 폴더 지정)로 옮긴다.
경로 인코딩 규칙: 작업 폴더 경로의 영숫자가 아닌 문자를 모두 `-` 로 치환한 것이
`~/.claude/projects/` 아래 폴더 이름이다 (`C:\PROJECT_SEOL` → `C--PROJECT-SEOL`).

## 옵시디언 지식맵 (2026-08-24 추가)

`PROJECT_SEOL/GMP 지식맵/` 이 옵시디언 볼트다 (기존 개인 볼트
`OneDrive\문서\Obsidian Vault` 는 영어공부용이라 따로 둔다).
드라이브의 `2. 신입 주차별 직무교육 자료` 를 뼈대로 만든 것으로,
`HOME` → 5갈래(규정 / 절차 / 문서·SOP / 설비 / 품질시스템) + 주차 축 구조.
`GMP 마인드맵.canvas` 가 마인드맵 뷰.

**원본 PDF 는 볼트에 복사하지 않고 `file:///G:/내 드라이브/...` 링크로만 건다.**
노트 본문의 `- [ ]` 는 사용자가 자료를 읽고 채울 자리 — Claude 가 추측으로 채우지 말 것.
