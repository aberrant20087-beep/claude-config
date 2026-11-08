# claude-config (비공개)

얼의 Claude Code 규칙·스킬·기억. 다른 컴퓨터에서도 같은 방식으로 일하기 위한 저장소. 대화 기록·로그인 정보는 들어 있지 않다.

## 들어 있는 것
- `CLAUDE.md` — 모든 세션 공통 규칙 (poteto 모드, 한국어, 앱 화면 건드리지 않기)
- `settings.json` — 출력 방식(Concise), 권한 모드 등 (비밀 값 없음)
- `skills/` — 사용자 스킬 (스킬 안의 `node_modules`는 빠짐 → 필요하면 그 스킬 폴더에서 `npm install`)
- `scheduled-tasks/` — 예약 작업 설명 (예약 자체는 새 컴퓨터 앱에서 다시 만들어야 함)
- `projects/*/memory/` — 프로젝트별 기억. 폴더 이름은 프로젝트 경로에서 나온다.
  - SEOL 기억: `projects/C--Users-newis-OneDrive-------SEOL/memory/`

## 다른 컴퓨터에서 받기
1. Claude Code(데스크톱 앱)를 설치하고 한 번 로그인한다. `C:\Users\<이름>\.claude`가 생긴다.
2. 빈 폴더에 받은 뒤 `.claude`에 복사한다 (로그인 파일을 덮지 않도록 clone을 바로 `.claude`에 하지 않는다).
   ```
   git clone https://github.com/<계정>/claude-config.git %USERPROFILE%\claude-config
   robocopy %USERPROFILE%\claude-config %USERPROFILE%\.claude /E /XD .git
   ```
3. SEOL 저장소를 받는다: `git clone https://github.com/<계정>/seol.git "<원하는 위치>\SEOL"`
4. SEOL을 다른 경로에 두면 기억 폴더 이름이 달라진다. 경로의 `:` `\` 한글·공백을 `-`로 바꾼 이름으로
   `projects/C--Users-newis-OneDrive-------SEOL/memory`를 복사한다 (예: `C:\work\SEOL` → `projects/C--work-SEOL/memory`).
5. 배포하려면 그 컴퓨터에서 `npx.cmd wrangler@3.114.17 login`으로 Cloudflare에 다시 로그인한다 (로그인 정보는 저장소에 없음).

## 일부러 뺀 것
대화 기록(`projects/*/*.jsonl`), `.credentials.json`, `.claude.json`, sessions·file-history·cache 등 앱 내부 파일,
실명·회사 이메일이 든 기억 파일 2종(`user-gmp-validation-engineer.md`, `video-tool-gemini.md`), `skills-backup-*`.
