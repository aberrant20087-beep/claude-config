---
name: gmp-daily-issues
description: GMP 규제 동향을 검색해 PROJECT SEOL 홈페이지 맨 위 이슈란을 갱신한다
---

PROJECT SEOL 홈페이지 맨 위의 「오늘의 GMP 이슈」란을 갱신한다.

## 대상
신승근 — 바이오써포트 GXP 솔루션 사업본부, GMP 밸리데이션·적격성평가 엔지니어(신입).
주 업무는 제약사 설비의 DQ/IQ/OQ/PQ 문서 작성·검토, URS 검토, RTM 작성.
**적격성평가·밸리데이션·데이터 완전성·제조지원설비(공조/제조용수/압축공기/멸균기)** 관련 소식을 최우선으로 고른다.

## 할 일

1. WebSearch 로 최근 1~7일 GMP 규제 동향을 찾는다. 검색어 예:
   - "식약처 GMP 고시 개정 행정예고"
   - "식약처 밸리데이션 가이드라인"
   - "FDA warning letter data integrity pharmaceutical"
   - "EMA Annex revision GMP"
   - "PIC/S PI guidance update"
   - "의약품 GMP 회수 행정처분"

2. **3~6건**을 고른다.
   - 날짜가 확인되지 않는 것은 넣지 않는다.
   - 요약은 검색으로 확인한 내용만 쓴다. 추측하거나 지어내지 않는다.
   - 규정 번호·조항은 출처에 그렇게 적혀 있을 때만 쓴다.
   - 이 사람은 이 정보를 실제 GMP 업무에 쓴다. 확실하지 않으면 빼는 쪽을 택한다.
   - 가능하면 요약 끝에 "이 사람 업무와의 관련"을 한 문장 덧붙인다.

3. 아래 파일에 UTF-8(BOM 없음) JSON 으로 덮어쓴다.
   `C:\Users\newis\OneDrive\바탕 화면\claude system\PROJECT_SEOL\data\_gmp_issues.json`

   ```json
   { "at":"2026-09-09 09:00", "date":"2026-09-09", "status":"ok", "note":"",
     "items":[ { "kind":"kr", "title":"...", "summary":"...", "source":"...", "date":"2026-09-08", "url":"https://..." } ] }
   ```
   kind: kr(국내) · global(해외) · guide(가이드라인) · recall(회수) · bs(사내)

   확인된 것이 없으면:
   `{ "at":"...", "date":"...", "status":"none", "note":"오늘은 확인된 새 이슈가 없습니다.", "items":[] }`

4. PowerShell 로 쓸 때는 반드시:
   `[System.IO.File]::WriteAllText($path, $json, (New-Object System.Text.UTF8Encoding $false))`
   (Windows PowerShell 5.1 이라 한글이 깨질 수 있다)

5. 마지막에 `tools\sync.ps1 -SkipCopy` 를 돌린다. 홈페이지는 10분마다 파일을 다시 읽지만,
   새로 여는 창에도 바로 반영되게 하려면 이게 필요하다.

## 하지 말 것
- 공유 드라이브(`G:\공유 드라이브`)는 건드리지 않는다.
- 이슈를 지어내지 않는다. 검색으로 확인되지 않으면 빈 목록으로 남긴다.
- `index.html` 을 직접 고치지 않는다 (자동 생성물이다).

끝나면 무엇을 몇 건 넣었는지 한 줄로 보고한다.