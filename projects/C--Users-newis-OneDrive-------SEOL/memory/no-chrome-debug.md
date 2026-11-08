---
name: no-chrome-debug
description: "얼의 Chrome을 Claude in Chrome으로 조작하지 않는다(디버깅 띠 때문에 화면이 흔들림), 확인은 화면에 안 띄우는 방법으로"
metadata:
  type: feedback
---

얼(2026-11-08, 다른 세션을 통해 전달): "디버깅 먼저 끄라고". Claude in Chrome이 붙으면 Chrome 위에 '디버깅 중' 띠가 떠서 화면이 흔들린다.

**Why:** 얼이 쓰는 Chrome 화면을 방해한다.
**How to apply:** `mcp__claude-in-chrome__*` 도구를 쓰지 않는다. 앱 오른쪽 브라우저 창도 쓰지 않는다. 페이지 확인은 curl, 파일 비교, 화면에 안 뜨는 headless Edge(puppeteer, scratchpad의 shot2.mjs·flow.mjs)로 한다(Edge는 따로 만든 임시 프로필 userDataDir + timeout 60, 끝나면 남은 headless 프로세스 확인 — 얼의 프로필에 붙으면 멈춤, 메모리 빠듯). 얼에게 보여 줄 때만 `Start-Process msedge`로 연다. [[open-in-edge]]
