# 프로젝트: {프로젝트명}

이 파일은 Codex(및 하네스 `scripts/execute.py`)가 작업 시 따르는 프로젝트 규칙이다.
하네스는 각 step 실행 시 이 파일을 가드레일로 로드한다.

## 기술 스택
- {프레임워크 (예: Next.js 15)}
- {언어 (예: TypeScript strict mode)}
- {스타일링 (예: Tailwind CSS)}

## 아키텍처 규칙
- CRITICAL: {절대 지켜야 할 규칙 1 (예: 모든 API 로직은 app/api/ 라우트 핸들러에서만 처리)}
- CRITICAL: {절대 지켜야 할 규칙 2 (예: 클라이언트 컴포넌트에서 직접 외부 API를 호출하지 말 것)}
- {일반 규칙 (예: 컴포넌트는 components/ 폴더에, 타입은 types/ 폴더에 분리)}

## 개발 프로세스
- CRITICAL: 새 기능 구현 시 반드시 테스트를 먼저 작성하고, 테스트가 통과하는 구현을 작성할 것 (TDD)
- 커밋 메시지는 conventional commits 형식을 따를 것 (feat:, fix:, docs:, refactor:)

## 하네스 실행 규칙
- 각 step은 이 파일에 명시된 작업만 수행하고, 요청되지 않은 기능/파일을 만들지 말 것.
- AC(Acceptance Criteria)를 직접 실행해 검증한 뒤 `phases/<phase>/index.json`의 step status를 갱신할 것.
- 사용자 개입(API 키, 인증, 수동 설정 등)이 필요하면 즉시 `blocked` 처리하고 중단할 것.

## 명령어
npm run dev      # 개발 서버
npm run build    # 프로덕션 빌드
npm run lint     # ESLint
npm run test     # 테스트

## 하네스
python3 scripts/execute.py <phase-dir> [--push]   # phase의 step을 순차 실행 (codex exec 호출)
python3 -m pytest scripts/test_execute.py         # 하네스 테스트
