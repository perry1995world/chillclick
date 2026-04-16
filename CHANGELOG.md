# Changelog — 심신안정 (ChillClick)

---

## [1.5.0] — 2026-04-17

### Added
- 테마 4종 완성: 집가고싶다 🏠 / 복권당첨 🍀 / 월급올려줘 💸 / 그냥쉬고싶다 😴
- 유료 회원 기록 저장 시스템 (날짜별 클릭 수 저장, 수정, 삭제)
- 이용약관 페이지 (`terms.html`)
- 개인정보처리방침 페이지 (`privacy.html`)
- 하단 푸터 (이용약관 / 개인정보처리방침 / 문의하기 링크)
- 광고 팝업 즉시 닫기 버튼 (5초 잠금 제거)
- "광고주 모집합니다" 자체 광고 스타일 적용
- Apple App Store 심사 대비 코드 입력 버튼 숨김 처리
- Vercel Analytics 삽입 (`/_vercel/insights/script.js`)
- GitHub → Vercel 배포 이전 (비공개 레포 지원)
- 레포 비공개 전환 (chillclick, grillo, grillo-test, sakyung, yiyun)
- App Store 제출 준비: Capacitor iOS 프로젝트 구성
- Apple 개인정보 매니페스트 (`PrivacyInfo.xcprivacy`) 추가
- 앱 아이콘 1024×1024 생성 (심·신·안·정 키캡 디자인)
- App Store 스크린샷 생성기 (`make-screenshots.html`)
- 버전 스냅샷 저장: `version/chillclick_v1.5.html`

### Changed
- 배포 환경: GitHub Pages → Vercel
- 유료 회원 전환 팝업: 4개 혜택 리스트 박스 제거, 심플하게 변경
- 배경(bgKeys) z-index 수정 → 콘텐츠 뒤로 고정 (겹침 버그 해결)
- 비밀번호 게이트: 테스트 서버 전용 → 라이브 서버로 이전 (pw: 1234)
- 문의 이메일: `minwoo5836@gmail.com` 전체 페이지 통일

### Removed
- 테스트 서버 레포 (`chillclick-test`) 삭제
- 유료 회원 전환 팝업 내 4개 항목 리스트 박스

---

## [1.0.2] — 2026-04-16

### Added
- 키캡 4개에 테마별 광고 이미지 표시 (비회원·무료 회원)
- 광고 팝업 5초 잠금 → 이후 우측 상단 ✕ 닫기 버튼 활성화
- 유료 회원 클릭 수 localStorage 저장·유지·수동 리셋
- 유료 회원 전환 시 저장된 클릭 수 자동 복원
- 테마 전환 시 광고 이미지 세트 자동 변경
- 유료 회원 데모 스위처에 클릭 수 초기화 버튼 추가
- GitHub Pages 이중 배포 (실서버 / 테스트서버)
- 테스트서버 비밀번호 게이트 (pw: 1234)
- 레포 README에 실서버·테스트 링크 표기

### Changed
- 광고 UI: 전체화면 오버레이 → 키캡 이미지 + 팝업 방식으로 변경
- 레포명: `sweet-home-sweet` → `chillclick`

### Removed
- 무료 회원 클릭 수 진행바 제거

### Fixed
- `setTheme()` 내 존재하지 않는 `progressFill` 참조 버그 수정

---

## [1.0.0] — 2026-04-15

### Added
- 기본 클릭 인터랙션 (키캡 누르기 애니메이션, 사운드, 파티클, 플로팅 텍스트)
- 테마 시스템: 집가고싶다 🏠 / 복권당첨 🎰 (잠금: 월급올려줘·그냥쉬고싶다)
- 회원 등급 시스템 프로토타입 (비회원·무료·유료 switcher)
- 광고 시스템: 비회원 50회 / 무료 회원 50·100·150회 트리거
- 무료 회원 159회 리셋 팝업 (유료 전환 유도)
- 클릭 수 공유 기능 (텍스트 복사·네이티브 공유)
- 파일 버전 관리 시작: `version/chillclick_v1.0.html`

---

## [1.8.0] — 예정

### 계획 중
- (v1.8 작업 내용 추가 예정)
