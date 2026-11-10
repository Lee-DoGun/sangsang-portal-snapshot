# 상상포털 정적 스냅샷 (실제 앱 실행본)

서버 없이 브라우저에서 **실제 상상포털 앱이 동작하는** 정적 스냅샷입니다.
Next.js 정적 익스포트(`output: "export"`)로 빌드한 결과물이며, 로그인 → 포털 → 메뉴 이동 → 버튼 동작까지 원본과 동일하게 동작합니다.

**접속 주소**: https://lee-dogun.github.io/sangsang-portal-snapshot/

## 구성

- 68개 라우트 전체가 실제 앱 JS(클라이언트 컴포넌트 + 목업 로직)로 동작합니다.
- `trailingSlash: true`로 각 경로가 디렉터리(`index.html`)로 출력되어 GitHub Pages에서 404 없이 이동합니다.
- `.nojekyll` 파일로 `_next` 정적 에셋이 서빙됩니다.
- 데이터는 목업(메모리 + localStorage 저장소) 기반이며, 일부 화면의 변경 사항은 브라우저 localStorage에 저장되어 새로고침 후에도 유지됩니다. 초기 상태로 되돌리려면 브라우저 사이트 데이터를 삭제하세요.

## 재생성 방법 (원본 저장소)

```bash
SNAPSHOT_EXPORT=1 npx next build
# out/ 내용을 이 저장소 루트에 복사하고 .nojekyll 유지
```

- `next.config.mjs`의 `SNAPSHOT_EXPORT=1` 모드가 `output: "export"`, `basePath: /sangsang-portal-snapshot`, `trailingSlash: true`를 적용합니다.
- 일반 빌드(`next build`)는 이 설정의 영향을 받지 않습니다.

기준 스냅샷: 2026-11-10 (원본 저장소 main 기준)
