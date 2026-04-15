# 심신안정 (ChillClick) — 프로젝트 컨텍스트 스킬

> 새 세션에서 이 파일을 읽으면 프로젝트 전체 컨텍스트를 즉시 파악할 수 있습니다.

---

## 프로젝트 기본 정보

- **서비스명**: 심신안정 (ChillClick)
- **컨셉**: 클릭형 키링 감성 — SNL 코리아 키링 코너 레퍼런스
- **타겟**: 10~30대
- **GitHub 계정**: perry1995world

---

## 배포 정보

| 구분 | URL | 레포 |
|------|-----|------|
| 🌐 실서버 | https://perry1995world.github.io/chillclick/ | perry1995world/chillclick |
| 🧪 테스트 | https://perry1995world.github.io/chillclick-test/ | perry1995world/chillclick-test |

- **테스트 비밀번호**: 1234
- **배포 스킬**: `dual-deploy-ghpages` 사용

---

## 로컬 작업 환경

```bash
# 로컬 git 클론 경로
/tmp/chillclick_work/

# remote 구성
origin → perry1995world/chillclick     (실서버)
test   → perry1995world/chillclick-test (테스트)

# 실서버 배포
git push origin main

# 테스트 배포 (비밀번호 게이트 자동 삽입 필요)
git push test main
```

- **원본 파일 경로**: `/Users/perrykim/Library/Mobile Documents/com~apple~CloudDocs/🌍 Perry World/P1. Project/05. 심신안정/`
- **기획 스킬**: `.../v1.0/@skill/chillclick_v1.0.md`

> ⚠️ 실서버 배포 전 반드시 비밀번호 게이트 제거:
> ```python
> content = open('index.html').read()
> start = content.find('<!-- ====== PASSWORD GATE ====== -->')
> end = content.find('<!-- ====== /PASSWORD GATE ====== -->') + len('<!-- ====== /PASSWORD GATE ====== -->')
> open('index.html', 'w').write(content[:start] + content[end:])
> ```

---

## 레포 파일 구조

| 파일 | 설명 |
|------|------|
| `index.html` | 최신 버전 (GitHub Pages 서빙용) |
| `chillclick_v1.0.html` | 초기 단순 버전 |
| `chillclick_v1.0.2.html` | 다중 테마·회원 등급·광고 포함 버전 |
| `CHANGELOG.md` | 버전별 변경 이력 |
| `SKILL.md` | 이 파일 — 프로젝트 컨텍스트 |

---

## 현재 구현 상태

### 회원 등급
- **무료 회원** (기본값): 광고 있음, 159회 리셋 제한
- **유료 회원**: 광고 없음, 무제한, 클릭 수 localStorage 저장
- 우측 상단 뱃지 클릭으로 등급 토글 (↕)

### 테마
| 테마 | 상태 |
|------|------|
| 🏠 집가고싶다 | ✅ 구현 |
| 🎰 복권당첨 | ✅ 구현 |
| 💸 월급올려줘 | 🔒 잠금 |
| 😴 그냥쉬고싶다 | 🔒 잠금 |

### 광고 시스템
- **무료 회원 전용** (비회원·유료 회원 광고 없음)
- **50회** 클릭 → 키캡 4개에 광고 이미지 노출
- **51회** 클릭 → 팝업 노출 (5초 잠금 → 우측 상단 ✕ 버튼 활성)
- 100/101회, 150/151회도 동일하게 반복

### 광고 키캡 4개 브랜드 (고정)
| 위치 | 브랜드 | 색상 |
|------|--------|------|
| 좌상 | ☕ Starbucks | 스타벅스 그린 |
| 우상 | 🍕 배달의민족 | 배민 민트 |
| 좌하 | 🛋️ 오늘의집 | 블루 |
| 우하 | 🛍️ 29CM | 블랙 |

### 기타
- 클릭 수 공유 버튼 (텍스트 복사·네이티브 공유)
- 무료 회원 159회 리셋 팝업 (유료 전환 유도)
- 배경 키캡 장식 (테마별 다름)
- 헤더·탭 배경 고정 (bg-key 겹침 방지)

---

## 주요 함수 목록

| 함수 | 역할 |
|------|------|
| `setTheme(name, el)` | 테마 전환 |
| `toggleTier()` | 뱃지 클릭 무료↔유료 토글 |
| `setTier(tier, el)` | 회원 등급 설정 |
| `checkAdKeys()` | 50/100/150회 키 광고 체크 |
| `checkAdPopup()` | 51/101/151회 팝업 체크 |
| `showAdKeyLayer()` | 키캡 광고 이미지 표시 |
| `showAd()` | 광고 팝업 표시 (5초 카운트다운) |
| `closeAd()` | 광고 팝업 닫기 + 키 광고 숨김 |
| `saveCount()` | 유료 회원 localStorage 저장 |
| `loadCount()` | 유료 회원 localStorage 불러오기 |
| `resetPremiumCount()` | 유료 회원 클릭 수 초기화 |
| `showReset()` | 159회 리셋 팝업 |
| `buildBgKeys()` | 배경 키캡 장식 생성 |

---

## CHANGELOG 요약

### v1.0.2 (2026-04-16)
- 광고 UI: 키캡 이미지 + 5초 팝업 방식
- 유료 회원 클릭 수 localStorage 저장
- 뱃지 클릭으로 등급 토글
- 하단 계정 전환 버튼 제거
- 헤더/탭 배경 고정
- 비회원 등급 제거 (무료·유료만 운영)
- progressFill 버그 수정

### v1.0.0 (2026-04-15)
- 기본 클릭 인터랙션
- 테마·회원 등급·광고 시스템
- GitHub Pages 이중 배포 세팅
