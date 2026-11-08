---
name: pending-home-file
description: "승인 전 새 홈(집·벤치·자매 영상)은 seol-home-house.html에서 작업, seol-home.html은 승인된 판만"
metadata:
  node_type: memory
  type: project
  originSessionId: 9d4cb431-0360-43be-a828-b5b89cc8532c
  modified: 2026-11-07T12:42:10.350Z
---

2026-11-07: 얼 확인 전 새 홈(통유리 집, 자매 영상 go-*.mp4, seol-hero.js 머리 그림)이 다른 세션 배포(build_site.py가 seol-home.html을 그대로 묶음)에 섞여 공개됐다. 얼이 "예전 홈으로"를 골라 되돌렸다(00b9d834 배포, 공개본 파일 비교 후 index.html만 교체).

**Why:** build_site.py는 작업 폴더의 seol-home.html을 index.html로 올리므로, 승인 전 판을 그 파일에 두면 누가 배포하든 공개된다.
**How to apply:** 새 홈은 로컬 `seol-home-house.html`(http://localhost:8731/seol-home-house.html)에서 작업하고, 얼이 승인하면 seol-home.html로 옮긴다. sense·embrace의 머리 그림 판은 담당 세션이 되돌리는 중이고, organize는 머리 그림을 꺼 둔 상태다. 배포할 때는 site/를 공개본과 비교해 자기 파일만 바꾼다. [[deploy-own-folder]]
