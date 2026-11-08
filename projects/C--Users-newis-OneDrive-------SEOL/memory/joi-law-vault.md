---
name: joi-law-vault
description: "JOI 역할 = 법·제도·규정 정리·연결; 옵시디언 볼트 위치와 규칙, 나중에 SEOL Link 페이지로 옮길 예정"
metadata:
  node_type: memory
  type: project
  originSessionId: 34dab449-1ded-4110-ba54-2112ce38065a
  modified: 2026-10-31T14:01:55.164Z
---

JOI(조이, Organize) 세션의 일은 세상의 법·제도·규정을 정리하고 연결하는 것이다. AI 시대 규칙과 "AI가 한 일을 사람이 검증하는 법"을 중점으로 다루고, 현재 화두와 곧 다가올 화두부터 정리한다. 사업자등록·상표 출원은 별도 세션의 일이다.

- 볼트: `C:\Users\newis\OneDrive\바탕 화면\법제도규정_지식그래프` (2026-10-12 생성, 2026-10-18 구조 개편)
- 조이 페이지 = 세상의 모든 법률·규정·가이드라인 정리. 구조(사용자 승인 2026-10-18): `10_법률·규정/`과 `20_가이드라인/` 아래 같은 분야 13개 폴더(01 헌법·행정 … 13 국제·통상), 여러 법에 걸친 주제는 `30_쟁점`. 나라는 폴더가 아니라 `관할` 속성으로 나눈다. 분야를 합칠지는 나중에 정하기로 했다.
- 2026-10-18 B안 진행: 13개 분야 핵심 법령 105개를 기본 정리 노트(tag `핵심법령`)로 추가했다. A안(국가법령정보센터 Open API로 한국 법령 전체 목록 자동 수집)은 사용자가 open.law.go.kr에서 OC 신청을 해야 진행 가능하다(아직 신청 전).
- 채우는 순서: 디지털·AI(1차 완료) → 보건·의료·바이오(GMP, 1차 완료) → 지식재산 → 금융 → 노동 → 환경 → 나머지
- 노트 속성: 구분/분야(목록, 첫 번째가 폴더)/유형/관할/상태/시행일/화두/확인일 + 태그 `분야/<짧은이름>`(그래프 색). 검증이 덜 된 사실에는 ⚠️ 확인 필요를 붙인다.
- 노트를 추가하거나 옮긴 뒤에는 `python 98_도구/build_map.py`를 실행해 `00_지도/분야 지도.md`를 다시 만든다.
- 조이 캐릭터 이미지(`characters/3d-joy.webp`, `cutout/Joy_3D.png`)도 JOI 세션이 직접 관리한다(SEOL CLAUDE.md 규칙).
- **Why:** 사용자가 "일단 옵시디언으로 정리하고, 페이지 개설이 끝나면 옮기자"고 했다.
- 조이 페이지 공개(2026-10-18): https://seol-dqx.pages.dev/organize.html. 볼트를 고친 뒤에는 `python tools/build_organize_data.py` → `python tools/build_site.py` → (바로) 전용 배포 폴더 `C:\Users\newis\seol-deploy-joi`로 복사 → CLAUDE.md의 배포 명령 순서로 반영한다. 공용 `seol-deploy`나 남의 폴더는 쓰지 않는다(2026-10-24 규칙). '2. 사업자 및 상표' 세션은 `-biz`(사용자 지시: 페이지를 고치면 매번 배포).
- **How to apply:** Link 별자리로 옮길 때는 SEOL `tools/build_link_data.py`의 VAULTS에 이 볼트를 추가한다(colorBy tag `분야/…`; 폴더 기준이면 색이 2개뿐이다). 2026-10-28 연이 세션이 VAULTS에 id "law"로 추가해 공개함(태그 `분야/…` 색 + `path:00_지도`). 볼트를 고치면 SEOL에서 `python tools/build_link_data.py`를 다시 돌려야 Link에 반영된다. 새 이슈는 이슈 레이더와 타임라인을 함께 갱신한다.
- 작업을 시작하거나 끝낼 때 SEOL\STATUS.json의 조이(key "joy") 섹션과 today 목록을 고치고 `python tools/status_md.py`를 실행한다(SEOL CLAUDE.md "작업현황" 참고).
- 사용자는 한도에 맞춰 노트북이 켜져 있는 동안 계속 작업하기를 원한다. 예약 작업(매일 09:00 GMP, 20:00 ONTOLOGY)이 쓸 주간 한도 몫은 남겨 둔다.
- 2026-10-31 얼 결정: 볼트의 법·가이드라인 나열은 뭘 만들었는지 알기 어렵다. 규제 정리는 분야별 AI 활용 안으로 넣고(활용 → 쟁점 → 조항), 얼이 가장 강한 GMP의 제약·바이오를 기준으로 만든 뒤 통과하면 다른 분야를 같은 형식으로 만든다. 볼트의 FDA CSA·AI 신뢰성·Annex 22·약사법 GMP 노트에는 조사로 확인된 오류가 남아 있어 고칠 대상이다.
- 분야별 AI 현황 페이지 `ai-now.html`(2026-10-31 첫 배포): 뼈대는 JOI, 분야 내용은 `organize/now/<분야>.js`의 하위 세션이 맡는다(사용자 지시). 숨김 Browser pane에서는 JS·스크린샷이 멈추므로 화면 점검은 Chrome headless + iframe(375×740) 방식이 안정적이다.
