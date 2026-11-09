---
name: local-preview-house
description: "로컬은 승인 전 영상 홈(seol-home-house.html)을 연다. 고친 건 로컬에 바로 반영, 배포만 얼 승인 (11-08)"
metadata:
  node_type: memory
  type: feedback
  originSessionId: 95c1b620-4983-4fd0-8768-8e391da160ab
  modified: 2026-11-08T09:37:01.319Z
---

얼에게 로컬을 열어 줄 때는 http://127.0.0.1:8766/seol-home-house.html (승인 전 영상 홈)을 Edge로 연다. 고친 내용은 로컬 승인 전 파일에 바로 모두 반영하고, 배포만 얼이 승인한다. (2026-11-08 얼 지시)

**Why:** 얼은 로컬로 계속 보면서 문제점과 개선점을 찾는다. 배포 안 했다고 로컬까지 멈추면 확인이 안 된다.

**How to apply:** 로컬 서버는 `python tools/local_preview.py 8766` (/ → 영상 홈, 방 주소 → *-hero.html; 그냥 http.server면 / 가 폴더 목록이 뜸). 담당 세션이 고치면 로컬 house 파일에 즉시 반영하게 한다. 승인 전 판을 seol-home.html에 섞지 않는 규칙([[pending-home-file]])은 그대로. [[open-in-edge]]
