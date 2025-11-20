# 🧭 FE Roadmap Blueprint ![Last commit](https://img.shields.io/github/last-commit/seungyeub/fe-roadmap-blueprint?label=last%20updated)

> 프론트엔드 학습을 위한 **커리큘럼·설계·레퍼런스** 저장소입니다.
> 진행 로그: [`fe-roadmap-progress`](https://github.com/seungyeub/fe-roadmap-progress) · 실습 코드: [`fe-roadmap-lab`](https://github.com/seungyeub/fe-roadmap-lab)

🕒 **마지막 갱신:** 2025-11-17

---

## 📘 Repository Overview

- **역할:** 학습의 ‘설계도’ 역할을 하는 **정적 지식 베이스**
- **구성 원칙:** 번호 기반(00~10) 상위 섹션, 내부는 주제별 마크다운
- **관계:** Progress(진행/로그) · Lab(실습)과 교차 링크

---

## 🧱 Main Sections

- **00_Guides** — 로드맵 개요, 읽는 순서, 용어/스타일 가이드
- **01_CS_Basics** — 네트워크, 브라우저 렌더링, HTTP/HTTPS, 보안, 스토리지
- **02_JavaScript** — 실행 컨텍스트, 스코프/호이스팅, this/클로저, 프로토타입, 비동기, 모듈, 성능
- **03_TypeScript** — 타입 기초, 인터페이스, 제네릭, 유틸리티, 고급 타입, 내로잉
- **04_React** — 기초, 상태관리, 테스트, 성능, Next.js
- **05_API_Integration** — REST, Axios, WebSocket, API 설계 가이드
- **06_Project_Practice** — 코드 품질, 배포, CI/CD 등 실전 운영 가이드
- **07_Testing** — Vitest/Jest, RTL, E2E(Cypress)
- **08_Collaboration** — Git 워크플로우, 코드리뷰, 이슈/PR 템플릿
- **09_Performance** — 최적화 체크리스트, 번들 분석, Lighthouse
- **10_SystemDesign** — FE 아키텍처, Micro-Frontend, 확장성 패턴

---

## 📂 Folder Structure

```bash
fe-roadmap-blueprint/
├── 00_Guides/
├── 01_CS_Basics/
├── 02_JavaScript/
├── 03_TypeScript/
├── 04_React/
├── 05_API_Integration/
├── 06_Project_Practice/
├── 07_Testing/
├── 08_Collaboration/
├── 09_Performance/
├── 10_SystemDesign/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   └── pull_request_template.md
├── LICENSE
└── README.md
```
---

## ✍️ Contribution

- 문서 파일은 kebab_case.md를 사용합니다.
- 내부 링크는 상대 경로로 작성합니다. (예: ../02_JavaScript/closure.md)
- 큰 구조 변경 시, PR에 섹션 간 링크 영향을 체크리스트로 포함해주세요.

---

## 🧩 License

본 저장소는 MIT License를 따릅니다. 자세한 내용은 [`LICENSE`](https://github.com/seungyeub/fe-roadmap-blueprint/blob/master/LICENSE)를 확인해 주세요.
