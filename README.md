# 상생협력포털 — 전체 화면 정적 스냅샷

GS리테일 상생협력포털(Next.js 데모)의 전체 화면을 서버 접속 없이 브라우저에서 열람할 수 있는 정적 스냅샷 사이트입니다.

## 접속 주소

**https://lee-dogun.github.io/sangsang-portal-snapshot/index.html**

## 구성 (화면 68개 + 목차 1개 = 69개 HTML)

- `index.html` — 전체 화면 목차. 섹션별로 정리된 링크 목록 제공.
- 화면별 개별 HTML 68개 — 목차 링크 또는 각 화면 안의 메뉴 링크 클릭으로 이동.

| 섹션 | 화면 수 | 원본 경로 |
|---|---|---|
| 홈 | 1 | `/` |
| 로그인 | 1 | `/login` |
| 회원가입 | 1 | `/signup` |
| 알림 | 1 | `/notifications` |
| 권한관리 | 1 | `/permissions` |
| 공급사 포털 | 37 | `/supplier/**` |
| 임직원 포털 | 18 | `/retailer/**` |
| 운영자 포털 | 10 | `/operator/**` |

## 특징

- 페이지별 개별 HTML — 화면 안의 메뉴 링크(`/supplier/users` 등)가 스냅샷 페이지로 이동합니다(이전 단일 파일 버전에서는 내부 링크가 전부 404였습니다).
- CSS 전부 인라인, 폰트 data URI 내장, 외부 참조 없음 — 오프라인에서도 열람 가능.
- 각 페이지 상단에 목차 내비게이션 바.
- 팝업(공지 다이얼로그)의 닫기·다시 보지 않기 버튼 동작.
- 그 외 버튼·입력 등 상호작용은 동작하지 않는 정적 렌더 스냅샷.

## 재생성 방법

원본 저장소에서 최신 빌드 후 스냅샷을 재수집·재조립할 수 있습니다:

```bash
npm run build
# 3199 포트 등으로 next start 후 scripts/build-static-snapshot.mjs로 라우트 HTML 수집
node scripts/build-static-snapshot.mjs
# /tmp/snapshot/site/*.html 을 이 저장소 루트로 복사해 커밋
```

## 기준일

- 스냅샷 수집: 2026-11-10 (main 브랜치 최신 빌드 기준)
