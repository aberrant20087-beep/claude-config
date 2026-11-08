---
name: ad-motion-2d-only
description: "광고 영상은 무료로: 힉스필드 구독은 비용 때문에 그만, Remotion으로 기존 3D 캐릭터 그림을 움직여 만든다(2026-11-08). 2D 선화 캐릭터 판은 보관만"
metadata:
  node_type: memory
  type: project
  originSessionId: 9d4cb431-0360-43be-a828-b5b89cc8532c
  modified: 2026-11-08T04:57:38.426Z
---

2026-11-08 얼 결정: 힉스필드 구독은 돈이 너무 많이 나가서 쓰지 않는다. 영상은 **무료로** 만든다. 첫 방법은 **Remotion**(코드로 만드는 영상, Claude 스킬 `remotion-dev/skills`)이다. 기존 3D 캐릭터 그림(`characters/3d-*.webp`, `walk-*.webp`, `cutout/*.png`)을 그대로 움직이므로 외형이 바뀌지 않는다. 3D처럼 몸이 도는 움직임이 꼭 필요하면 그다음에 Kaggle 무료 GPU + Wan 2.2(이미지→영상)를 검토한다. 이 PC는 그래픽 카드가 없어 AI 영상 모델을 직접 못 돌린다.

(이전 2026-11-07 결정: 힉스필드 구독해 3D로, 얼 지시 전 대기 → 위 결정으로 바뀜.)

`marketing/ad-motion/`의 2D SVG 모션그래픽(2D 선화 캐릭터)은 중단된 시안으로 보관만 한다. 2D로 다시 그린 캐릭터는 실제 서비스에 쓰지 않는다. Remotion은 2D 그림을 새로 그리는 게 아니라 3D 캐릭터 그림을 쓰는 것이라 이 규칙과 맞다.

**Why:** 얼이 "힉스필드로 구독해 가면서 쓰니깐 너무 돈 많이 나가. 절약이 아니라 그냥 무료로 영상 제작할 수 있는 방법, 캐릭터는 내가 만들어 놓은 캐릭터로" → 추천 중 "Remotion부터".
**How to apply:** 광고(로고 낙하 → What's your dream? → And why? → 설이 선화→3D → 해안가 이야기 → UFO → 벤치)를 다시 만들 때 기존 예고편 자산(`trailer/gemini_handoff/keyframes`, `clips`, `refs`)과 3D 이미지·`group.webp`를 재사용해 Remotion으로 합성한다. 유료 API·구독은 얼에게 먼저 묻는다. 광고는 로컬에서만, 배포하지 않음. Remotion 프로젝트는 OneDrive 밖 `C:\Users\newis\tools\seol-video`.
