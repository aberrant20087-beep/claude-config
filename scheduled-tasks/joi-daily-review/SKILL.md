---
name: joi-daily-review
description: 매일 08:10(근무 전) JOI 세션에 그날 조사 기록 검토를 요청 (직접 조사·수정하지 않음)
---

JOI(조이) 세션에 오늘의 조사 기록 검토를 요청하는 작은 작업이다. 이 실행에서는 조사·파일 수정·커밋을 하지 않는다. 한국어로 쓴다.

1. `mcp__ccd_session_mgmt__list_sessions`(필요하면 ToolSearch로 먼저 불러온다)로 보관되지 않은 세션 중 제목이 정확히 "3. JOI (조이)"인 세션을 찾는다. 여러 개면 lastActivityAt이 가장 최근인 것. 없으면 "JOI 세션을 찾지 못함" 한 줄만 남기고 끝낸다.
2. 그 세션의 sessionId로 `SendMessage`(to: sessionId)를 보낸다. 내용:
"오늘 조사 기록 검토를 부탁합니다(매일 09:00 자동 요청). `organize/CLAUDE.md`의 'JOI 세션의 매일 검토' 순서대로 `organize/DAILY_LOG.md`와 AI 지도 분야별 기록 `organize/atlas/log/*.md`의 지난 검토 뒤 새 칸을 검토하고, 분야마다 출처를 원문으로 확인한 뒤, 기록에 'JOI 검토' 줄을 붙이고 얼에게 두세 줄로 보고해 주세요. 밤사이 앱이 꺼져 건너뛴 분야 루프가 있으면(`organize/atlas/runs.local.json`과 예약 작업 실행 기록) 다시 돌려 주세요. 새 칸이 없으면 그렇다고만 보고해 주세요."
3. 보냈으면 "JOI 검토 요청 보냄" 한 줄로 끝낸다.

얼의 Chrome과 앱 오른쪽 창은 쓰지 않는다.