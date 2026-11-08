---
name: insta-cover-video-self-made
description: 인스타 표지 영상은 스톡에서 찾지 말고 코드로 직접 만들 것 (Pexels 금지)
metadata:
  node_type: memory
  type: feedback
  originSessionId: a509f5b2-332d-44aa-a2e2-66237d83f3c7
  modified: 2026-10-26T14:34:09.543Z
---

표지 영상은 Pexels 같은 스톡 사이트에서 찾지 않는다 — 후보를 제시하지도 않는다. 매 회차 주제에 맞는 1080x676 무음 mp4 를 `tools/` 의 생성 도구로 직접 그린다 (mapdraw.mjs = 해안선 그리기, threeroads.mjs = 한 점에서 길 셋이 뻗고 하나가 흩어짐). 맞는 도구가 없으면 mapdraw.mjs 를 본보기로 새로 하나 만든다 — 픽셀 버퍼에 그려 ffmpeg stdin 으로 흘려보내는 구조. 결과는 `assets/video/generated/` 에 두고, `node tools/videocover.mjs <날짜> <영상> 0 8` 과 `... ko` 로 표지를 합친다.

**Why:** 운영자 지시 2026-10-22 — "무료 라이선스말고 너가 만들어, 앞으로 저기서 찾지마". 스톡 영상은 주제와 미묘하게 어긋나고 고르는 과정이 일만 늘린다.

**예외 (2026-10-24, DAY 26):** 운영자가 실제 사건 사진을 직접 요청하면 미국 연방정부 공식 사진(whitehouse.gov/gallery, "Official White House Photo by …" — 공공저작물)을 쓸 수 있다. 통신사(Getty·AP·로이터) 사진은 인스타에 많이 돌아도 저작권 있음 → 금지. 사진은 천천히 다가가는 8초 영상(ffmpeg zoompan)으로 만들어 `assets/video/<출처-id>/` 에 source.json 과 두고, 캡션 출처 줄 앞에 `📷 Cover photo: Official White House Photo by <이름>` 을 넣는다.

**바뀜 (2026-10-26):** 운영자 지시 "예시 사진은 찾아. 영상 직접 만드는거는 이슈적인 요소가 없을때만". 이제 기본은 이슈 사진 — 이슈에 실제 장면·인물·사물이 있으면 자유 이용 사진(미국 연방정부 공식 사진, Wikimedia Commons 퍼블릭도메인·CC BY/BY-SA)을 찾아 쓰고, 보여줄 요소가 없을 때만 코드로 그린다. 스톡(Pexels)·통신사·언론사 사진은 계속 금지.

**How to apply:** [[ontology-insta-channel]] 매일 초안. 만든 뒤 ffmpeg 로 프레임 한두 장 뽑아 눈으로 확인. [[insta-no-abbreviations-no-cats]] 의 카드 문구 규칙과 함께 본다.
