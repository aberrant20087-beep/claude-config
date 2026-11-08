---
name: account-migration
description: "2026-11-01 Claude 계정 변경 준비 완료, 복원은 새 계정 로그인 뒤. 절차는 ACCOUNT_MIGRATION.md"
metadata:
  node_type: memory
  type: project
  originSessionId: 4406c953-9eef-4f93-8dfc-fd10e6c7f950
  modified: 2026-11-01T11:40:52.498Z
---

얼이 2026-11-01 Claude 계정을 바꾸려고 백업과 인수인계를 맡겼다. 절차·상태는 SEOL `ACCOUNT_MIGRATION.md`, 백업은 `C:\Users\newis\OneDrive\바탕 화면\seol-account-backup-20261101`.

**Why:** 앱의 세션 목록·그룹, 클라우드 예약작업, 커넥터, 아티팩트는 계정에 묶여 있고 대화 기록·메모리·스킬은 PC에 있다.

**How to apply:** 새 계정 첫 세션은 그 문서를 읽고 복원 여부, 커넥터, `설이 영감 정리` 재생성, 옛 계정 예약작업 끄기를 확인한다. `tools/account_restore.py`는 모의 시험만 통과했다.
