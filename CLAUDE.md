# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
# 로컬 개발 서버 실행
npm start

# 프로덕션 빌드
npm run build

# 테스트 실행 (watch 모드)
npm test

# 단일 테스트 파일 실행
npm test -- --testPathPattern=App.test.js --watchAll=false
```

## Docker

이 프로젝트는 Docker 학습을 위한 프로젝트입니다. `Dockerfile.dev`를 사용해 개발 컨테이너를 빌드합니다.

```bash
# 개발용 Docker 이미지 빌드
docker build -f Dockerfile.dev -t frontend-dev .

# 컨테이너 실행 (포트 3000 바인딩, 소스 코드 볼륨 마운트)
docker run -p 3000:3000 -v /app/node_modules -v $(pwd):/app frontend-dev
```

`Dockerfile.dev`는 `node:lts-alpine3.12` 이미지 기반이며, `npm run start`로 개발 서버를 실행합니다.

## Architecture

Create React App(CRA) 기반의 React 18 애플리케이션입니다. 기본 CRA 구조를 유지하고 있습니다.

- `src/App.js` — 메인 컴포넌트
- `src/index.js` — 진입점, ReactDOM으로 App을 렌더링
- `src/App.test.js` — `@testing-library/react` 기반 테스트
- `public/index.html` — HTML 템플릿
