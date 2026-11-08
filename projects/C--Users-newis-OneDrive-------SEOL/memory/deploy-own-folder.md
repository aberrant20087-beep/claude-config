---
name: deploy-own-folder
description: SEOL 배포는 세션마다 전용 영문 폴더에 새로 복사해서 올린다 (공용 seol-deploy 동시 복사 충돌)
metadata:
  node_type: memory
  type: project
  originSessionId: bab58595-c7ec-4bef-b1ac-96c0b55918bf
  modified: 2026-10-24T12:41:04.727Z
---

SEOL 공식 사이트(Cloudflare Pages `seol`) 배포 때 여러 세션이 `C:\Users\newis\seol-deploy`에 동시에 복사하면, 파일이 일부만 들어간 배포가 생긴다(2026-10-24 실제 발생: 4개 파일만 업로드되고 /api 404).

**Why:** 하위 세션 여럿이 같은 폴더를 rm/cp 하며 겹침. POI 세션이 각 세션 전용 폴더를 쓰자고 제안함(POI는 `seol-deploy-poi`).
**How to apply:** POI TO YEONI 세션은 `C:\Users\newis\seol-deploy-p2y`에 `site/`, `functions/`, `wrangler.toml`을 새로 복사한 뒤 그 폴더에서 CLAUDE.md의 wrangler@3.114.17 명령으로 배포한다. 배포 뒤 `/api/waitlist`와 바뀐 파일 내용을 꼭 확인한다.
