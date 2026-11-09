---
name: verify-in-eol-browser
description: '확인했다' 보고에는 브라우저·주소를 적고, 얼이 쓰는 로컬 Edge(127.0.0.1:8766)에서도 보이는지 확인
metadata:
  type: feedback
---

'확인했다'고 보고할 때는 어느 브라우저·주소에서 확인했는지 적는다. 헤드리스 확인만으로 끝내지 말고, 얼이 실제로 쓰는 로컬(http://127.0.0.1:8766, Edge)에서도 보이는지 확인한다.

**Why:** 2026-11-08 포이 4번 별표1·13이 얼의 Edge '내 자료'에 없었다. IndexedDB(poi-files)는 브라우저마다 따로라, 헤드리스에 넣은 자료가 얼의 Edge에는 없었다. 총괄이 `_local_docs/` + `tools/local_preview.py` + `tools/local_seed.js`(POI.readFile로 넣고, 이미 있는 자료는 그대로 둠, 배포 안 됨)로 해결했다.

**How to apply:** 브라우저 저장소(IndexedDB·localStorage)에 기대는 기능은 헤드리스 결과를 얼의 화면 결과로 보고하지 않는다. 로컬 자료가 필요하면 `_local_docs/`와 local_seed 장치를 쓴다. 화면은 띄우지 않는다([[no-chrome-debug]], [[open-in-edge]]).
