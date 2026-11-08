---
name: deploy-stale-build
description: "배포 보류 중 일부만 올릴 때 옛 빌드 폴더를 쓰지 말고, 배포 직전 공개본과 비교해 자기 파일만 바꾼다"
metadata:
  node_type: memory
  type: feedback
  originSessionId: 9d97f2e5-8aa0-4e6a-9d0a-70f345e0abc0
  modified: 2026-11-07T19:06:45.654Z
---

2026-11-07 SEORI가 sense.html만 되돌리려고 자기 배포 폴더에 남은 옛 main 빌드(cae36384)를 그대로 올렸다. 그 사이 JOI가 배포한 organize 수정이 옛 판으로 돌아갔다.

**Why:** 여러 세션이 수시로 main에 배포하므로, 몇 시간 전 빌드도 이미 남의 최신 배포보다 오래됐다. 반대로 `build_site.py`를 새로 돌리면 다른 세션의 아직 배포 안 한 로컬 수정이 섞인다.
**How to apply:** 배포 직전에 `python tools/deploy_guard.py site --mine "sense.html" "music.html" "art.html" "sense/*"`를 돌린다(총괄이 만든 도구, 11-08 안내). 도구가 없을 때는 보류 중이거나 일부만 올릴 때는 배포 직전에 site/의 각 파일을 지금 공개본과 비교해(curl 등) 공개본으로 덮고, 자기 파일만 로컬 판으로 둔 뒤 배포한다(SEOL DESIGN 방식). 배포 뒤 남의 페이지도 하나 이상 공개본과 같은지 확인한다. 관련: [[deploy-own-folder]]
