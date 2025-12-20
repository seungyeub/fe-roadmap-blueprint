# 🌐 네트워크 경로 한 번에 잡기 (주소창→화면)

## 1. URL 파싱과 DNS (재귀 질의의 흐름)
- 브라우저/OS/리졸버 캐시 → 루트 → TLD → 권한 있는 네임서버 → A/AAAA 레코드 획득
- **TTL**: 캐시 유효기간. TTL이 남아있으면 재조회 생략

## 2. TCP 3-Way & TLS 1.3
- TCP: SYN → SYN/ACK → ACK
- TLS 1.3: **단축된 핸드셰이크**, 기본 전방 보안(Perfect Forward Secrecy)
- **ALPN**: HTTP/1.1 vs HTTP/2/3 선택, **SNI**: 동일 IP 가상 호스팅

## 3. HTTP/1.1 vs 2 vs 3
- **1.1**: keep-alive(직렬 요청), HOLB(헤드-오브-라인 블로킹) 존재
- **2**: 단일 TCP 연결에 **멀티플렉싱**, HPACK 헤더 압축
- **3**: **QUIC/UDP**, 연결 이동/손실 복원에 유리, 지연/패킷손실에 탄탄

## 4. 응답 품질/전달
- **TTFB**: 서버 처리+네트워크 지연 복합 지표
- **Content-Encoding**: gzip/br(zstd 일부), **Content-Type/Charset**
- **HSTS**: HTTP→HTTPS 강제; 중간자 공격 완화
EOF

# (2) HTTP 기본(메서드/상태/캐시/쿠키/CORS) 노트
cat > 01_CS_Basics/http_fundamentals.md << 'EOF'
# 📡 HTTP Fundamentals — 메서드/상태/캐시/쿠키/CORS

## 1) 메서드 & 멱등성
| Method | 의미 | 멱등 | 사용 예 |
|---|---|---|---|
| GET | 조회 | ⭕ | 문서/리소스 가져오기 |
| POST | 생성/행위 | ❌ | 폼 제출/업로드 |
| PUT | 전체 치환 | ⭕ | 문서 전체 대체 |
| PATCH | 부분 수정 | ❌ (보통) | 일부 필드 업데이트 |
| DELETE | 삭제 | ⭕ | 리소스 제거 |

## 2) 상태코드
- 2xx: 200 OK / 201 Created / 204 No Content
- 3xx: 301 Moved Permanently / 302 Found / 307/308 (메서드 유지)
- 4xx: 400 Bad Request / 401 Unauthorized / 403 Forbidden / 404 Not Found / 429 Too Many Requests
- 5xx: 500 Internal Server Error / 502 Bad Gateway / 503 Service Unavailable

## 3) 캐시 전략 (강력/검증/무효화)
- 강력 캐시: `Cache-Control: max-age=600` → 만료 전 **네트워크 무통신**
- 검증 캐시: `ETag` ↔ `If-None-Match` → **304**로 대역 절약
- 보강 지시자: `must-revalidate`, `stale-while-revalidate`, `stale-if-error`
- 민감정보: `no-store`(디스크 저장 금지), `private`(공유캐시 금지)
- 캐시 키: `Vary: Accept-Encoding, Origin, User-Agent` 등

## 4) 쿠키
- 속성: Secure/HttpOnly/SameSite(Lax/Strict/None)/Path/Domain/Max-Age
- **SameSite=None → Secure 필수** (크롬 정책)
- 인증 토큰: HttpOnly + Secure + 짧은 수명 + 서버 검증(회전/로그아웃 처리)

## 5) CORS
- 단순 요청 조건: 특정 메서드/헤더/컨텐츠 타입
- 프리플라이트: `OPTIONS` → `Access-Control-Allow-*`로 허용
- 크리덴셜: `Allow-Origin: *`와 **동시 사용 불가**, 반드시 구체 Origin
EOF

# (3) 렌더링 파이프라인/성능 노트
cat > 01_CS_Basics/browser_rendering.md << 'EOF'
# 🖼️ 브라우저 렌더링 파이프라인 & 성능 포인트

## 1) CRP(HTML→DOM, CSS→CSSOM, Render Tree→Layout→Paint→Composite)
- **CSS는 렌더 차단**, JS는 파서 차단 가능 → `<script defer>`/`async`
- module 스크립트는 기본 **defer 동작**(순서 보장)

## 2) 이벤트 타이밍
- **DOMContentLoaded**: 초기 DOM 구성 완료(이미지 등 외부 리소스 불필요)
- **load**: 모든 리소스 로드 완료

## 3) 성능 지표 & 측정
- **FCP/LCP/CLS**(Web Vitals), TTI
- DevTools Performance/Network + Lighthouse
- `requestAnimationFrame`으로 애니메이션 동기화, **layout thrashing** 회피

## 4) 실무 체크리스트
- 첫 화면에 필요한 CSS만 **critical**로(나머지는 지연)
- 이미지: 크기/포맷, lazy 로딩, `width/height` 지정(레이아웃 점프 방지)
- 인터랙션: 메인스레드 점유 최소, `transform/opacity` 위주 변경