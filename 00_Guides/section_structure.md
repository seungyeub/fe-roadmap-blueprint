# 🧱 Section Structure – 섹션별 구성 설계

> 이 문서는 `01_CS_Basics`, `02_JS`, `03_TS` 등
> 각 상위 폴더 안에 어떤 토픽 파일들을 둘지, **대략적인 설계도를 정리**합니다.

---

## 1. 01_CS_Basics

```bash
01_CS_Basics/
  ├── overview.md
  ├── network.md
  ├── http.md
  ├── browser-rendering.md
  ├── caching.md
  ├── security-basics.md
  └── etc.md
```

- overview.md
  - CS 섹션 전체 개요, 어떤 항목들을 다룰지 요약
- network.md
  - LAN/WAN, IP, DNS, TCP/UDP, 포트, 라우팅 등
- http.md
  - HTTP 요청/응답 구조, 메서드(GET/POST/PUT/DELETE…), 상태 코드, 헤더
- browser-rendering.md
  - DOM, CSSOM, 렌더 트리, Reflow/Repaint, JS 파싱/실행 순서
- caching.md
  - 브라우저 캐시, ETag, Cache-Control, CDN 개념
- security-basics.md
  - XSS, CSRF, CORS, HTTPS/TLS 등

---

## 2. 02_JS

```
02_JS/
  ├── overview.md
  ├── basics.md
  ├── scope-closure-this.md
  ├── prototype-oo.md
  ├── async.md
  ├── modules-bundling.md
  └── etc.md
```

- basics.md
  - 변수, 타입, 연산자, 조건/반복, 함수 기초
- scope-closure-this.md
  - 실행 컨텍스트, 스코프 체인, 클로저, this 바인딩
- prototype-oo.md
  - 프로토타입 체인, 클래스 문법, 상속
- async.md
  - 콜백, Promise, async/await, 이벤트 루프 개념
- modules-bundling.md
  - ES Module, CommonJS, 번들링 개념(Vite/Webpack과 연결)

---

## 3. 03_TS

```
03_TS/
  ├── overview.md
  ├── basics.md
  ├── type-system.md
  ├── generics.md
  ├── utility-types.md
  └── ts-config-env.md
```

- basics.md
  - 기본 타입, 인터페이스, 타입 별칭
- type-system.md
  - 좁히기(narrowing), 유니온/인터섹션, 타입 추론
- generics.md
  - 제네릭 함수/인터페이스/클래스
- utility-types.md
  - Partial, Pick, Omit, Record, Readonly 등
- ts-config-env.md
  - tsconfig 주요 옵션, React+TS 환경 구성

---

## 4. 04_React
```
04_React/
  ├── overview.md
  ├── basics.md
  ├── hooks.md
  ├── component-patterns.md
  ├── performance.md
  ├── react-query-swr.md
  └── etc.md
```

- basics.md
  - JSX, 컴포넌트, props/state, 이벤트 처리
- hooks.md
  - useState, useEffect, useMemo, useCallback, useRef 등
- component-patterns.md
  - 컨테이너/프레젠테이셔널, Compound Components 등
- performance.md
  - 렌더링 최적화, memo, Suspense, 코드 스플리팅
- react-query-swr.md
  - 서버 상태 관리 도구 개념