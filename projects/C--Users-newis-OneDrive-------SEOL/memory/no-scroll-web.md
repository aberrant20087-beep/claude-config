---
name: no-scroll-web
description: 웹 페이지는 스크롤 없이 한 화면에 모두 들어가게 만든다
metadata:
  node_type: memory
  type: feedback
  originSessionId: 95c1b620-4983-4fd0-8768-8e391da160ab
  modified: 2026-10-24T07:33:58.578Z
---

웹 작업을 할 때는 페이지에 세로·가로 스크롤이 절대 생기지 않게 만든다(2026-10-24 지시). 스크롤이 필요하면 사용자가 따로 요청한다.

**Why:** 사용자가 SEOL 페이지를 모두 한 화면 레이아웃으로 원한다.
**How to apply:** 100vh/100vw 안에 맞추고, 넘치는 내용은 크기 조정·탭·넘김으로 처리한다. 폰 화면도 확인한다. SEOL `CLAUDE.md`에도 같은 규칙이 있다.
