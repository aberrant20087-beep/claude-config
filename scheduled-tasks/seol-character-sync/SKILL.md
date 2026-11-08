---
name: seol-character-sync
description: SEOL 캐릭터 이미지가 바뀌었으면 SEOL Home 아티팩트의 소개란 캐릭터를 새 이미지로 다시 게시
---

SEOL 홈페이지(아티팩트 https://claude.ai/artifact/BtCMPb5mcyaq9PEXZHb6zG)의 Sense 소개란 캐릭터 이미지를 최신 캐릭터 그림과 맞추는 작업이다. 사용자에게 하는 말은 모두 한국어로 쓴다.

1. 다음을 실행한다 (Bash):
   python "C:/Users/newis/OneDrive/바탕 화면/SEOL/tools/sync_characters.py"
   - 출력 마지막 줄이 NO_CHANGE 이면 아무것도 하지 말고 "변경 없음" 한 줄만 남기고 끝낸다. 다른 파일은 읽거나 바꾸지 않는다.
   - 출력이 CHANGED ... 이면 2번으로 간다.

2. 스크래치패드 디렉터리(없으면 작업 디렉터리)에 새 폴더 seol-sync 를 만들고 다음을 실행한다:
   python "C:/Users/newis/OneDrive/바탕 화면/SEOL/tools/sync_characters.py" --out "<seol-sync 폴더 절대경로>"
   그러면 <seol-sync>/characters/3d-seori.webp, 3d-poi.webp, 3d-joy.webp, 3d-yeoni.webp 가 생긴다. 네 장을 Read 로 열어 투명 배경의 캐릭터 그림인지 눈으로 확인한다. 깨졌거나 캐릭터가 아니면 게시하지 말고 그 사실만 보고하고 끝낸다.

3. Artifact 도구로 action "read", url https://claude.ai/artifact/BtCMPb5mcyaq9PEXZHb6zG 를 읽는다. 결과가 알려 주는 저장된 페이지 파일(전체 페이지 HTML)을 내용 수정 없이 그대로 쓴다. 페이지 파일이 작업 디렉터리나 스크래치패드 밖에 있으면 <seol-sync>/index.html 로 복사해서 쓴다.

4. Artifact 도구로 다시 게시한다:
   - action "publish", url https://claude.ai/artifact/BtCMPb5mcyaq9PEXZHb6zG
   - file_path: 3번의 페이지 파일 (HTML 내용은 바꾸지 않는다)
   - root: <seol-sync 폴더 절대경로>
   - files: {"characters/3d-seori.webp":"characters/3d-seori.webp","characters/3d-poi.webp":"characters/3d-poi.webp","characters/3d-joy.webp":"characters/3d-joy.webp","characters/3d-yeoni.webp":"characters/3d-yeoni.webp"}
   - label: "캐릭터 이미지 자동 반영"
   - icon 은 넘기지 않는다.
   게시가 충돌로 거절되면 거절 결과가 넘겨준 최신 페이지 내용으로 다시 3~4번을 한 번 더 한다. force 는 절대 쓰지 않는다.

5. 게시에 성공했을 때만 다음을 실행해 '게시 완료'로 기록한다:
   python "C:/Users/newis/OneDrive/바탕 화면/SEOL/tools/sync_characters.py" --mark
   그리고 바탕화면 SEOL 폴더 사본도 맞춘다: <seol-sync>/characters/*.webp 는 이미 SEOL/characters 와 같으므로 따로 복사할 필요는 없다.

6. 어떤 캐릭터(CHANGED 뒤 이름들)가 바뀌어 몇 번째 버전으로 게시됐는지 한국어 한두 줄로 보고한다.

지켜야 할 것: SEOL/characters 의 이미지 파일을 직접 고치거나 지우지 않는다(스크립트가 하는 백업·재생성만 허용). Cloudflare 배포(wrangler)는 하지 않는다. 페이지 HTML·영상·다른 파일은 바꾸지 않는다.