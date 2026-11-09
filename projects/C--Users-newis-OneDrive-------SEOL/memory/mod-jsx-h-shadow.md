---
name: mod-jsx-h-shadow
description: "seol-eng 모드(register.tsx)의 JSX는 h()로 바뀌므로 변수 이름 h 금지, Button은 key·label·onPress, onPress는 10초 안에 끝내기"
metadata:
  node_type: memory
  type: reference
  originSessionId: 463287d2-1705-4bd8-96e4-69c326fdaca4
  modified: 2026-11-08T12:26:21.477Z
---

오른쪽 패널 모드 `seol-eng`(`C:\Users\newis\.claude\dev-mods\463287d2-1705-4bd8-96e4-69c326fdaca4\seol-eng\hooks\register.tsx`)를 고칠 때 tsc가 못 잡는 실행 오류들(2026-11-08):
- JSX가 `h(...)` 호출로 바뀐다. `.map(h => ...)`처럼 변수 이름을 `h`로 쓰면 "h is not a function"으로 패널이 깨진다.
- Button은 `key`·`label`·`onPress`가 모두 있어야 그려진다(없으면 빈 패널).
- onPress·훅은 10초 제한. 오래 걸리는 계산(eng_levels.py 약 13초)은 `$.process.spawn`을 기다리지 않고 돌린 뒤 `$.ui.invalidate('ui.render')`.
- 그리기 오류는 `SEOL/tools/.seol_eng_error.log`에 남는다. 확인: `npx --yes -p typescript@5.6.3 tsc -p <모드>/.claude-plugin/types/tsconfig.json`(Temp 폴더에서).
