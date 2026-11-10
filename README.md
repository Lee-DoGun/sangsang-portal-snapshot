# 상생협력포털 — 전체 화면 정적 스냅샷

GS리테일 상생협력포털(Next.js 데모)의 전체 화면을 서버 접속 없이 브라우저에서 한 번에 볼 수 있는 정적 스냅샷 사이트입니다.

## 접속 주소

**https://lee-dogun.github.io/sangsang-portal-snapshot/index.html**

## 포함 화면 (68페이지, 8개 섹션)

| 섹션 | 내용 |
|---|---|
| 홈 | 포털 랜딩 (`/`) |
| 로그인 | 공급사/임직원 로그인·2차 인증·세션 시나리오 (`/login`) |
| 회원가입 | 공급사 회원가입 (`/signup`) |
| 알림 | 알림 센터 (`/notifications`) |
| 권한관리 | 권한 관리 화면 (`/permissions`) |
| 공급사 포털 | 주문·ASN·정산·반품·상품·재고 등 37개 메뉴 (`/supplier/**`) |
| 임직원 포털 | 발주·클레임·정산·공급사 관리 등 18개 메뉴 (`/retailer/**`) |
| 운영자 포털 | 테넌트·회원·공지·과금·시스템(EAI 연계) 등 10개 메뉴 (`/operator/**`) |

## 특징

- 단일 `index.html` (약 595KB) — CSS 전부 인라인, 폰트 data URI 내장, 외부 참조 없음
- 서버 연결이 끊겨도 오프라인으로 열람 가능 (파일로 저장해도 동작)
- 상단 내비게이션 바에서 섹션별 바로가기
- 버튼·입력 등 상호작용은 동작하지 않는 정적 렌더 스냅샷

## 재생성 방법

원본 저장소에서 최신 빌드 후 스냅샷을 재수집·재조립할 수 있습니다:

```bash
npm run build
# 3199 포트 등으로 next start 후 scripts/build-static-snapshot.mjs로 라우트 HTML 수집
node scripts/build-static-snapshot.mjs
```

## 기준일

- 스냅샷 수집: 2026-11-10 (main 브랜치 최신 빌드 기준)
