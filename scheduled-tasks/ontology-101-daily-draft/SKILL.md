---
name: ontology-101-daily-draft
description: 매일 20시, AI 총괄 섹션의 INSTAGRAM 세션에 오늘 초안 작업을 넘김 (이 세션에선 작업 안 함)
---

이 예약 세션은 전달만 한다. 초안 작업은 여기서 하지 않는다 (운영자 지시 2026-11-04: 인스타 작업은 매일 새 세션이 아니라 'INSTAGRAM' 세션에서. 2026-11-07부터 INSTAGRAM 세션은 AI 총괄 섹션 아래에 있다).

1. 오늘 날짜(YYYY-MM-DD, 로컬 시간)를 확인한다.
2. ToolSearch 로 mcp__ccd_session_mgmt__send_message 와 mcp__ccd_session_mgmt__archive_session 을 불러온다.
3. send_message 로 session_id "local_45dfa607-395f-4c5a-88bf-cb0d1de38ea0" (제목 INSTAGRAM, AI 총괄 섹션) 에 아래 메시지를 보낸다. <오늘> 은 실제 날짜로 바꾼다.
   "[예약 20:00] <오늘> ONTOLOGY 101 초안 시간입니다. C:\Users\newis\OneDrive\바탕 화면\ontology-insta\daily-draft.md 절차대로 오늘(<오늘>) 초안을 만들어 주세요. 게시는 하지 말고, 끝나면 카드·캡션을 보여주세요."
4. 결과가 delivered 또는 queued 이면, archive_session 으로 이 예약 세션 자신("self" 또는 get_session self 의 sessionId)을 보관하고 "INSTAGRAM 세션으로 넘김"으로 끝낸다.
5. 전달이 실패하면(세션이 없음 등) 보관하지 말고, 실패 이유를 적은 뒤 daily-draft.md 절차를 이 세션에서 직접 실행한다.

절대 tools/publish.mjs 를 실행하지 않고 게시하지 않는다. .env 는 읽지 않는다.