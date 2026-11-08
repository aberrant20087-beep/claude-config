---
name: project-seol
description: "PROJECT SEOL — 사용자의 개인 업무 워크스페이스 (바탕화면), 구글 드라이브 자료 + 홈페이지 + Claude cowork 환경"
metadata: 
  node_type: memory
  type: project
  originSessionId: 223ea91e-29fb-44ef-a776-7521c66966fa
  modified: 2026-08-18T00:19:03.620Z
---

사용자는 `바탕 화면\PROJECT_SEOL`에 개인 업무 워크스페이스를 만들고 있다 (2026-08-18 시작).
목적은 현재 회사와 앞으로 다닐 회사에서의 업무 최적화.

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

## 다른 PC 로 이어가기 (2026-08-18 추가)

바탕 화면이 OneDrive 백업 대상이라 프로젝트 파일과 `CLAUDE.md` 는 자동으로 따라간다.
따라가지 않는 것은 기억뿐이라 `PROJECT_SEOL/context/` 에 사본을 두고
`tools/memory.ps1` (기본=내보내기, `-Import`=되돌리기, `-Root`로 작업 폴더 지정)로 옮긴다.
경로 인코딩 규칙: 작업 폴더 경로의 영숫자가 아닌 문자를 모두 `-` 로 치환한 것이
`~/.claude/projects/` 아래 폴더 이름이다.

사용자는 회사 PC 에서도 Claude Code 를 설치해 쓰는 방식(웹/GitHub 경유가 아니라)을 원한다.
회사 보안 정책에 막힐 수 있어 claude.ai 접속 → OneDrive 개인계정 로그인 → 무관리자 설치
순으로 확인하기로 했다. 회사 문서 사본(`data/drive/`)은 GitHub 에 올리지 않는다.

## 옵시디언 지식맵 (2026-08-24 추가)

`PROJECT_SEOL/GMP 지식맵/` 이 옵시디언 볼트다 (기존 개인 볼트
`OneDrive\문서\Obsidian Vault` 는 영어공부용이라 따로 둔다).
드라이브의 `2. 신입 주차별 직무교육 자료` 를 뼈대로 만든 것으로,
`HOME` → 5갈래(규정 / 절차 / 문서·SOP / 설비 / 품질시스템) + 주차 축 구조.
`GMP 마인드맵.canvas` 가 마인드맵 뷰.

**원본 PDF 는 볼트에 복사하지 않고 `file:///G:/내 드라이브/...` 링크로만 건다.**
노트 본문의 `- [ ]` 는 사용자가 자료를 읽고 채울 자리 — Claude 가 추측으로 채우지 말 것.
