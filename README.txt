PWA 패키지 — DataForge PWA 빌더 (https://dataforge.ai.kr/vibe/pwa)
================================================================

[포함 파일]
  index.html  PWA 코드가 이미 적용된 페이지
  manifest.json   앱 정보 (이름·색상·아이콘)
  sw.js           서비스 워커 (오프라인·캐시)
  icons/          앱 아이콘 세트
  snippet.html    index.html <head>에 붙여넣을 코드 (참고용 — 이미 적용됨)

[적용 방법]
  1. ZIP 안의 모든 파일(index.html 포함)을 사이트 루트에 업로드
     ※ <head> 스니펫은 index.html에 이미 삽입되어 있습니다
  2. GitHub Pages / Vercel에 배포(push)

[고해상도 화면 보정]
  - pdf.js를 쓰는 페이지라면 스마트폰(레티나 화면)에서 흐리게 보이는 문제를
    자동으로 보정합니다 (devicePixelRatio 반영, 최대 3배)
  - pdf.js가 없는 페이지에서는 아무 동작도 하지 않습니다
  - 앱이 자체적으로 transform을 지정해 렌더링하면 건드리지 않습니다

[설치 확인]
  - PC Chrome  : 주소창 오른쪽 설치 아이콘
  - 모바일 Chrome: 메뉴 → 앱 설치 (또는 홈 화면에 추가)
  - iPhone Safari: 공유 → 홈 화면에 추가

[재배포 시]
  sw.js 상단의 CACHE 버전을 올려야 (v1 → v2) 새 콘텐츠가 반영됩니다.
