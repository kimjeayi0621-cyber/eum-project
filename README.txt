# E:UM 공동 데이터베이스 연결형 시제품

## 준비물
- GitHub 계정
- Supabase 계정 및 프로젝트
- Vercel 계정

## 1. Supabase 데이터베이스 준비
1. https://supabase.com 에서 새 프로젝트를 만듭니다.
2. 왼쪽 SQL Editor를 열고 `supabase_setup.sql`의 전체 내용을 붙여넣어 실행합니다.
3. Authentication > Providers에서 Anonymous Sign-Ins(익명 로그인)를 활성화합니다. 메뉴 명칭은 화면 버전에 따라 다를 수 있습니다.
4. Project Settings > API에서 Project URL과 anon/public key를 복사합니다. service_role/secret key는 절대 사용하거나 공개하지 마세요.

## 2. config.js 설정
`config.js`의 SUPABASE_URL과 SUPABASE_ANON_KEY에 위 두 값을 넣습니다. anon/public key는 RLS 정책이 반드시 적용된 상태에서만 프런트엔드에 넣습니다.

## 3. GitHub에 올리기
1. GitHub에서 새 저장소를 만듭니다.
2. `index.html`, `config.js`, `supabase_setup.sql`을 저장소 최상위에 올립니다.

## 4. Vercel 배포
1. https://vercel.com 에서 GitHub로 로그인합니다.
2. Add New > Project에서 저장소를 가져옵니다.
3. Framework Preset은 Other, Build Command와 Output Directory는 비워두고 Deploy합니다.
4. 생성된 주소를 열어 확인합니다.

## 동작 범위
- 익명 인증으로 브라우저별 사용자 ID 생성
- 프로필, 프로젝트 게시글을 Supabase에 공동 저장
- 로그인된 시제품 사용자들이 프로젝트 목록을 함께 열람
- 매칭 요청 저장 및 요청 내역 확인

## 아직 구현하지 않은 기능
- 실시간 채팅
- 매칭 요청 수락/거절 화면
- 신고/차단 및 관리자 기능
- 실제 서비스 수준의 신원 확인

## 안전 안내
학교 발표용 가상 시제품입니다. 실제 이름, 전화번호, 주소, 이메일 등 개인정보를 입력하지 마세요. 익명 계정은 계정 복구가 어려울 수 있습니다. 실제 서비스로 공개하기 전에는 연령 보호, 신고·차단, 개인정보 처리방침, 접근 제어를 별도로 설계해야 합니다.
