# LogiFlow Pro — iPhone 홈 화면 앱 설치용 패키지

이 패키지는 기존 LogiFlow Pro HTML/JavaScript 기능을 유지한 **PWA(웹 앱)** 패키지입니다.
Mac/Xcode 없이 iPhone의 Safari에서 홈 화면에 추가해 앱처럼 실행할 수 있습니다.

## 먼저 알아둘 점
- 네이티브 iOS `.ipa`가 아니라, HTTPS 주소로 제공되는 웹 앱을 홈 화면에 추가하는 방식입니다.
- 따라서 인터넷에 HTTPS로 호스팅해야 합니다. 이 ZIP만 아이폰에서 열어서는 홈 화면 앱 설치가 되지 않습니다.
- 재고 데이터는 기존 `localStorage`에 저장되며, 해당 iPhone/브라우저에만 저장됩니다. 다른 기기와 자동 동기화되지 않습니다.
- 핵심 앱 파일은 캐시되도록 구성했지만 Tailwind/아이콘/웹폰트 CDN은 외부 인터넷 연결이 필요할 수 있습니다.

## 무료 배포 방법 예시: GitHub Pages
1. GitHub 계정으로 로그인하고 새 공개 저장소(repository)를 만듭니다.
2. 이 ZIP을 PC에서 압축 해제한 뒤, `index.html`, `manifest.webmanifest`, `service-worker.js`, `icons` 폴더를 저장소 최상위(root)에 업로드합니다.
3. 저장소의 Settings → Pages에서 배포 소스를 `Deploy from a branch`, 브랜치를 `main`, 폴더를 `/ (root)`로 선택하고 저장합니다.
4. GitHub Pages가 제공하는 `https://...github.io/.../` 주소가 생성될 때까지 기다립니다.

## iPhone에 설치
1. iPhone에서 **Safari**로 위 HTTPS 주소를 엽니다.
2. 하단 또는 상단의 공유 버튼(네모에서 위 화살표)을 누릅니다.
3. **홈 화면에 추가**를 선택합니다.
4. 이름을 `LogiFlow Pro`로 확인하고 **추가**를 누릅니다.
5. 홈 화면에 생긴 LogiFlow Pro 아이콘을 눌러 실행합니다.

## 포함 파일
- `index.html`: 기존 재고관리 앱과 기존 JavaScript 기능
- `manifest.webmanifest`: 홈 화면 앱 표시 설정
- `service-worker.js`: 앱 기본 파일 캐시
- `icons/`: iPhone 및 PWA 아이콘

## 데이터 주의
앱/브라우저 데이터 삭제, 사이트 데이터 초기화, 기기 변경 시 데이터가 사라질 수 있습니다.
중요한 재고 데이터는 정기적으로 별도 백업하는 것을 권장합니다.
