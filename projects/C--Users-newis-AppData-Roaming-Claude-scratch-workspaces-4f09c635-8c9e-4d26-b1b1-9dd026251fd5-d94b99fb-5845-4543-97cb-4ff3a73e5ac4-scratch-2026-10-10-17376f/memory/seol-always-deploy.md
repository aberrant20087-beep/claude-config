---
name: seol-always-deploy
description: SEOL homepage changes must always be deployed to the public Cloudflare address without asking
metadata:
  node_type: memory
  type: feedback
  originSessionId: fd333e5d-6b17-46e8-b3f3-1a57cb036a97
  modified: 2026-10-17T05:28:55.083Z
---

After any change to the SEOL homepage, deploy it to the public site (https://seol-dqx.pages.dev, Cloudflare Pages project `seol`) as well as the artifact — don't ask first.

**Why:** The user said on 2026-10-17 "앞으로 공개주소로 다 배포해" after being asked for deploy confirmation.
**How to apply:** Build with `python tools/build_site.py` in the SEOL folder, copy `site/` to an ASCII path, and deploy from inside that folder. The exact working command is in SEOL/CLAUDE.md ("공식 사이트 배포"). Also keep the $1 sign-up button (join.html) from the monetization session in the site source. See [[reply-in-korean]].
