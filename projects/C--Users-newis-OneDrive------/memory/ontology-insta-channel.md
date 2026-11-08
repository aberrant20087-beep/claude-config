---
name: ontology-insta-channel
description: "ONTOLOGY 101 인스타 채널 — 매일 기초 개념 1개 + 관련 이슈 1개 카드뉴스, 사용자 학습 목적"
metadata:
  node_type: memory
  type: project
  originSessionId: 561aecb3-7f33-45cb-8be8-4086c30422d3
  modified: 2026-10-28T13:18:18.543Z
---

2026-09-27 시작. 폴더 `바탕 화면\ontology-insta` (CLAUDE.md 에 절차 있음).
사용자는 "소식" 채널이 아니라 **기초 개념부터 순서대로 + 개념과 연결된 이슈 하나씩** 전하는 방식을 원했고,
그 과정으로 본인도 온톨로지를 공부하는 게 주목적. 그래서 post.json 에 게시 안 되는 `study` 심화 노트가 있다.

- 2026-09-28 변경: 주제는 curriculum.md 순서가 아니라 **사용자가 매일 직접 준다** → `topics/<날짜>.md` 에 적고, (있으면) `drafts/<날짜>/outline.md` 를 뼈대로 씀. 주제 파일 없으면 예약 작업은 아무것도 안 만듦.
- 매일 20:00 예약 작업 `ontology-101-daily-draft` 가 초안만 생성 (09-28 20→17시, 09-29 다시 20시로).
- 게시 경로: Instagram API with Instagram Login + 공개 GitHub 저장소(raw URL)로 이미지 호스팅. 토큰은 `.env` (사용자가 직접 작성).
- 렌더: Node + Edge headless (이 PC 의 python 은 스토어 스텁이라 없음). 렌더 1회에 수 분 걸림.

- 2026-09-28 DAY 01 첫 게시 (계정 sogn_97). API(.env·git remote) 미설정이라 Claude 앱 내장 브라우저에서 게시: 사용자가 파일 8장 직접 선택 → Claude가 4:5 비율·캡션 입력 → 사용자 확인 후 공유. 게시 전 최종안(카드+캡션) 반드시 보여줄 것.
- 2026-09-29 사용자 지시: **당분간 게시는 이 방식으로 고정** — Claude가 내장 브라우저로 instagram.com 열기 + slides 폴더 탐색기로 열기 → 사용자가 사진 8장 넣음 → Claude가 4:5·캡션 입력 → 공유는 사용자 확인 후. publish.mjs(API) 는 git remote 미설정이라 실패함, 쓰지 말 것.
- 2026-10-01 DAY 03 게시(Dd6pgASkid3)도 같은 방식. 이때 Claude가 메모리를 안 보고 publish.mjs 실행·Chrome 확장 연결을 시도해 헤맸고 사용자가 답답해함 → **"올려줘" 요청이 오면 바로 내장 브라우저(mcp__Claude_Browser__)로 instagram.com 열기.** Claude in Chrome 확장은 연결 안 됨(연결 브라우저 0개). 게시 후 `drafts/<날짜>/published.json` 에 permalink 기록.
- 2026-09-29: 예약 작업 20:00 으로 변경. 캡션에 URL 넣지 않음(인스타 캡션 링크 안 눌림). 초안 완성되면 PNG를 채팅에 바로 띄워 보여줄 것(review.html 은 안 보인다고 함).
- 카드 디자인: 검은 배경 + 연주황(#ffc25c) + 제목 Jua/본문 Gowun Dodum ("AI 느낌" 싫어함). 마지막 카드 하단은 '생각해보기' 대신 다음 주제 예고.
- 2026-10-02 사용자 지시: **기생충·봉준호 예시 다시 쓰지 말 것** (DAY 04·05에 연달아 써서 지적). 예시는 **기초과학**(물·원소·행성 등)을 우선. CLAUDE.md 에도 반영함.
- 2026-10-05 사용자 지시: **학습 방식 = 이해 → 연결 → 구조화** — 카드 주제가 아니라 Claude가 매 주제를 다루는 방식(개념 이해 → 지난 DAY와 연결 → 전체 지도에 구조화). CLAUDE.md 에 반영. 처음엔 이걸 DAY 08 카드 제목으로 잘못 넣었다가 지적받음.
- 2026-10-08 사용자 지시 (DAY 09 초안 피드백): ① **예시는 주제마다 다른 소재** — DAY 08 태양계 숙제를 DAY 09에 또 써서 지적받음, 카레 요리로 교체. ② **캡션은 카드 내용 복붙 금지** — 카드에 없는 배경·뒷이야기·읽는 팁·질문으로 쓸 것. ③ 논문을 다루면 캡션에 **논문 출처**(제목·저자·arXiv 번호·날짜·종류)를 적을 것. DAY 10 예고는 '온톨로지 엔지니어링'으로 정함. CLAUDE.md 에 반영함.
- 해시태그: 게시물 1,000개 이하 태그는 빼기 (팔로워 늘리려는 목적). 예시는 검색 없이 바로 이해되는 관계로 (불고기-재료-소고기 같은).

**Why:** 방향 전환(뉴스→개념 학습)을 잊으면 다시 뉴스 요약형으로 만들게 된다.
- 2026-09-28 사용자 지시: **이 채널 작업은 GMP·제약 업무와 절대 엮지 않는다.** 예시는 영화·음식 같은 일상 소재로. (예전 DAY 01 초안의 GMP 예시는 따라 하지 말 것)

**How to apply:** 사용자가 준 주제를 우선(curriculum.md 는 참고용)하고, 예시·심화 노트 어디에도 GMP 업무를 끌어오지 않는다.

- **2026-10-17 사용자 지시: 채널을 영어로 글로벌 운영.** 카드·캡션·해시태그 전부 영어(post.json `"lang":"en"`), 한국에서만 통하는 예시는 영어권 예시로. study 노트·채팅은 한국어 유지. 이미 올린 DAY 01~18은 영어판(post.en.json → `render.mjs <날짜> en` → slides-en/)을 만들고, 한국어 게시물은 **보관(archive)** 후 영어판을 새로 게시하기로 함(삭제 아님 — 좋아요·댓글 보존). 예약 작업 프롬프트·CLAUDE.md 도 영어로 갱신.
- **2026-10-17 사용자 지시: 매 회차 첫 카드(표지) = 위 절반 실제 영상 + 아래 절반 글** (다른 계정들처럼). 영상은 Pexels 무료 스톡에서 주제에 맞게 후보를 보여주고 사용자가 고르면 내려받음 → `tools/videocover.mjs` → `slides/1-video.mp4`. 테슬라 공개 영상 같은 뉴스·기업 영상은 쓰지 않기로 합의(저작권). 사용자는 후보를 '직접 보고' 고르길 원함(앱 브라우저 창에 Pexels 검색 탭을 띄워 보여줌). DAY 19 = Pexels 8322057 빈티지 회중시계 내부(분홍 시계는 사용자가 별로라 교체 — 색이 튀는 영상보다 클래식·차분한 톤 선호, 후보는 썸네일을 한 장에 모아 채팅에 보여주길 원함). 다음 주제 DAY 20 = 테슬라 Roadster(2026-10-15 공개)를 바탕으로 '자동차냐 비행기냐, 분류의 경계' (topics/2026-10-18.md).
- 2026-10-18 DAY 20 = Deoz4SXkkds (영어판, 표지 영상 없이 1.png — 사용자 "이번엔 영상 넣지마"). 사용자가 한글 검토판도 원함 → `post.ko.json` → `render.mjs <날짜> ko` → slides-ko/ (게시 안 함, 이해용). DAY 21 = AI·생명공학 결합(살아있는 뉴런 컴퓨터, 테슬라의 반대 방향), topics/2026-10-19.md.
- 2026-10-19 DAY 21 = DerakBfkka8. 표지 영상은 Pexels 대신 **Claude가 코드로 직접 만든 3D 뉴런 영상**(tools/gen-neurons3d.mjs → videocover.mjs; 사용자가 격자 빼고 3D로 요청). 사용자 선호: **영상·썸네일은 채팅에 파일로 바로** (링크·브라우저 창 X), mp4는 채팅에서 자동재생 안 되니 **미리보기는 GIF로 변환해서** 보여줄 것. DAY 22 = '현재 없는 데이터는 무엇인가?' (topics/2026-10-20.md, 후성유전학 등 실험해야 아는 데이터 메모 포함).
- **2026-10-15 최종 결정: 게시는 앞으로 계속 웹(Claude in Chrome)으로.** 사용자가 토큰 방식보다 크롬 열어두는 게 편하다고 함. publish.mjs 는 쓰지 않음(.env 에 토큰 없음 — 실행하면 카드 PNG 를 공개 GitHub seol-consultant/SEOL 에 push 한 뒤 실패함). 순서: [[insta-web-upload-crop]] 의 크롬 경로. 초안 보여줄 때 캡션은 채팅 본문에 바로. DAY 16 = DeeuGsgkvJz. DAY 17 = DehBm_-Ekqs (2026-10-15, 사용자가 "공유 바로 하자 너가"로 승인 → 같은 크롬 경로로 한 번에 성공).
- (이전 기록) 2026-10-10 사용자 지시: **매일 직접 로그인하기 싫음 → API 게시로 전환 중.** 계정은 비즈니스로 전환 완료. Claude 는 비밀번호 입력 불가라 브라우저 로그인 대행 안 됨. publish.mjs 를 고쳐 **카드 PNG 만** 별도 공개 저장소(`.public/` clone, 예: ontology-insta-cards)로 push 하도록 함(이 폴더 전체 공개 방지). 남은 일: 사용자가 Meta 토큰 발급·.env 작성, GitHub 공개 저장소 생성 → Claude 가 .public clone(브랜치 main) → --dry 시험. 연결 후엔 사용자가 카드 검토하고 "올려" 하면 Claude 가 publish.mjs 실행 (CLAUDE.md 규칙 갱신). 예약 작업은 여전히 게시 금지.
- 2026-10-21 DAY 22 = DeuJhJcEpXh (빈 페이지 넘기는 손 Pexels 29251301 표지). 예시는 고양이 대신 일란성 쌍둥이 지문. 한국어 학습판 slides-ko 도 만듦. DAY 23 = '없는 데이터 중 가장 가치가 높아질 데이터' (topics/2026-10-21.md).
- **2026-10-21 운영자 지시: 오늘부터 영어판·한국어판을 매일 둘 다 게시** (한국어판은 더 이상 검토용이 아님). post.json → slides/, post.ko.json → slides-ko/, 표지 영상도 양쪽(`videocover.mjs <날짜> <영상>` / `... ko`). CLAUDE.md 에 반영.
- 2026-10-21 DAY 23 게시: 영어 https://www.instagram.com/sogn_97/p/DewfMYQEllz/ · 한국어 https://www.instagram.com/sogn_97/p/DewflrSEs47/ (둘 다 표지 영상 포함 8장).
- **표지 영상은 스톡보다 직접 만드는 쪽을 선호**: DAY 23 때 Pexels '지도 그리는 손' 후보를 운영자가 "기존 그림에 선을 갖다 대는 것뿐"이라며 거절 → `tools/mapdraw.mjs` 로 **백지에서 세계 지도가 그려지는** 영상을 직접 만들어 씀 (Natural Earth 110m 퍼블릭 도메인 외곽선, assets/map/, 결과는 assets/video/generated/). DAY 21 뉴런 영상과 같은 흐름.
- DAY 24 = 'AI가 참과 거짓을 구별하는 방법' (topics/2026-10-22.md, 운영자 지정 2026-10-21).
- 2026-10-23 DAY 25 게시: 영어 https://www.instagram.com/sogn_97/p/De1xzlZEgNy/ · 한국어 https://www.instagram.com/sogn_97/p/De1yE8GErvD/ . 표지는 tools/fence.mjs(울타리 산점도) — 운영자가 "영상 다른거 창작해봐"로 breadth 막대에서 교체. 카드 3 예시는 운영자 요청으로 '지도 앱'→'자이언트 판다'. 주의: render.mjs 가 slides/ 를 비워 1-video.mp4 가 지워짐 → 렌더 후 videocover 재실행.
- 2026-10-24 DAY 26 (AI→SI 이름 바꾸기) 게시: 영어 https://www.instagram.com/sogn_97/p/De4Q-g7kh5m/ · 한국어 https://www.instagram.com/sogn_97/p/De4SEf7kgBP/ . 표지는 운영자 요청으로 백악관 공식 사진(공공저작물) 줌인 영상 — [[insta-cover-video-self-made]] 예외. DAY 27 = 'AI 모델은 어떻게 만들어지고 왜 버전마다 다른가' (topics/2026-10-25.md).
- 2026-10-27 DAY 29 (사람마다 다른 '특이점') 초안 — 표지 EHT 블랙홀 M87* 사진(CC BY 4.0). **운영자 지시 2026-10-27: DAY 30부터 새 단계 = '분야별 AI 활용·난이도 현황'** (분야마다 AI 가 어디까지 쓰이고 얼마나 어려운지). 특정 분야 순서는 아직 안 정함 — topics/ 파일로 받을 것.
- 2026-10-27 DAY 29 게시: 영어 https://www.instagram.com/sogn_97/p/De_908qklSC/ · 한국어 https://www.instagram.com/sogn_97/p/De_-KgLkjC4/ . 운영자 피드백: **인물을 비교할 땐 그 사람이 무엇을 하는/어느 회사 사람인지와 구체적 예측(연도)을 같이 표시**할 것.
- 2026-10-28 DAY 30 '분야별 AI ① 노화 연구' (운영자 "노화분야 연구부터 간단히") 게시: 영어 https://www.instagram.com/sogn_97/p/DfChESbkrMx/ · 한국어 https://www.instagram.com/sogn_97/p/DfChWzUkq2F/ . 이슈 CeMM 조직 시계(Nature Medicine 2026-08), 표지 Commons 정상 폐 조직 사진. 분야별 단계 순서: ① 노화 → ② 암 연구(DAY 31, topics/2026-10-29.md). 의료 분야라도 건강 조언 아님 한 줄 넣고 제약 소식(AI 신약)은 뺌.
