# 하마월드 3 (7 vs 7 FPS)

웹에서 바로 하는 3D 팀전 슈터입니다. 솔로 전용 랜덤 큐로 7 vs 7을 만들고, 빈 자리는 봇이 채웁니다.

## 파일
| 파일 | 설명 |
|---|---|
| `index.html` | 게임 본체 (GitHub Pages 첫 화면) |
| `admin.html` | 개발자·어드민 페이지 (신고 · 정지 · 추방 · 접속 현황) |
| `database.rules.json` | Firebase Realtime Database 보안 규칙 (`hw3/` 경로) |

## 게시 방법 (GitHub Pages)
1. 이 저장소를 **Public**으로 만들어 파일을 모두 올립니다.
2. 저장소 **Settings → Pages → Branch: `main` / `/ (root)`** 로 저장합니다.
3. 잠시 뒤 아래 주소로 열립니다.
   - 게임: `https://<GitHub사용자명>.github.io/<저장소이름>/`
   - 어드민: `https://<GitHub사용자명>.github.io/<저장소이름>/admin.html`

## Firebase 설정
1. Firebase 콘솔에서 하마월드 3 전용 프로젝트를 만듭니다 (월드 1·2와 분리).
2. **Authentication**: "익명"과 "이메일/비밀번호"를 켜고, 개발자 계정(`simonlee2011@naver.com`)을 추가합니다. 이메일 인증을 완료해야 개발자 권한이 적용됩니다.
3. **Authentication → Settings → 승인된 도메인**에 `<GitHub사용자명>.github.io`를 추가합니다.
4. **Realtime Database**를 만들고 **규칙** 탭에 `database.rules.json` 내용을 붙여넣어 게시합니다.
5. 프로젝트 설정 → 내 앱(웹)의 설정값을 `admin.html` 안의 `FIREBASE_CONFIG`에 붙여넣습니다. (공개되어도 되는 값입니다.)

## 참고
- 게임(`index.html`)은 아직 Firebase에 연결되기 전이라 기록이 브라우저(localStorage)에 저장됩니다.
- 어드민 페이지에서 개발자는 비밀번호만 입력하면 됩니다 (이메일은 `admin.html`에 고정). 비밀번호 자체는 파일에 적지 마세요.
