# 스윗밸런스 자사몰 홈페이지

바쁜 직장인과 운동하는 사람을 위한 스윗밸런스(샐러드·건강 간편식) 한 페이지 자사몰입니다.
오늘 컨디션을 고르면 한 끼를 딱 하나만 골라 주는 **점심 고민 해결 버튼**이 이 페이지의 주인공입니다.

## 배포 주소

| | 주소 |
|---|---|
| 홈페이지 | https://hyeonheo-glitch.github.io/my-homepage-hyeon.heo/ |
| 제작 원페이저 | https://hyeonheo-glitch.github.io/my-homepage-hyeon.heo/docs/sweetbalance-homepage-onepager.html |

`main` 브랜치에 푸시되면 GitHub Actions가 자동으로 배포합니다 (`.github/workflows/deploy-pages.yml`).
워크플로가 Pages를 직접 활성화하므로 별도 설정 없이 첫 배포가 진행됩니다.
만약 권한 문제로 활성화에 실패하면 **Settings → Pages → Source** 를 `GitHub Actions` 로 한 번만 바꿔 주세요.

## 화면 구성

| | 섹션 | 내용 |
|---|---|---|
| 01 | 첫 화면 | 헤드라인 "오늘도 균형있게" + CSS로 그린 균형 도넛 (단백질 40% / 채소 30% / 곡물·좋은 지방 30%) |
| 02 | 대표 제품 | 콥샐러드를 주인공 카드로, 서브 메뉴 3종 |
| 03 | **점심 고민 해결 버튼** | 시간 · 컨디션 · 목표를 고르면 9개 메뉴 중 하나를 추천하고 근거를 함께 표시. 담은 메뉴는 주간 기록에 누적 |
| 04 | 브랜드 소개 | 미션, 퍼스낼리티(Warm · Fresh · Honest), 슬로건 |

### 점심 고민 해결 버튼

- 시간(2) × 컨디션(5) × 목표(3) = **30가지 조합**
- 무작위 뽑기가 아니라 조리시간·칼로리·단백질·식이섬유·컨디션 적합도를 **점수화**해 한 개를 고릅니다
- 추천 이유를 3줄 근거로 함께 보여줍니다 — `단백질 32g — 한 끼로 목표를 거의 다 채웁니다`
- 최근 추천은 점수를 깎아, 같은 조합을 다시 눌러도 다른 메뉴가 나옵니다
- 담은 끼니 수 / 누적 단백질 / 누적 채소는 브라우저 `localStorage`에 저장됩니다

## 파일

| 파일 | 설명 |
|---|---|
| `index.html` | 홈페이지 본체. HTML·CSS·JS가 모두 이 한 파일에 들어 있습니다 |
| `docs/sweetbalance-homepage-onepager.html` | 무엇을 만들었는지 한 장으로 정리한 문서 |
| `.github/workflows/deploy-pages.yml` | GitHub Pages 자동 배포 워크플로 |

## 디자인 기준

**SweetBalance Brand Design System Manual (Ver. 2025.07.25)** 을 따릅니다.

- 컬러 — Vital Green `#00614E`, Harmony Green `#007C5E`, 배경은 Sunshine White `#FDFFE6`
  (포인트색은 "한 화면에 Secondary는 하나만" 규칙에 따라 Seed Green `#84BA45` 하나만 사용)
- 타이포 — Montserrat(영문 UI) / Pretendard(한글 본문) / Chewy · 삼립호빵체(디스플레이 전용)
- 형태 — 8px 리듬, 워크호스 radius 14px, CTA는 pill, 섀도우는 전부 그린 틴트
- 모션 — 120 / 220 / 420ms, 바운스 · 패럴랙스 · 지속 루프 애니메이션 없음

## 로컬에서 보기

```
git clone https://github.com/hyeonheo-glitch/my-homepage-hyeon.heo.git
```

`index.html` 을 브라우저로 열면 됩니다. 빌드 도구나 서버가 필요 없습니다.
외부 이미지 링크가 없고 브랜드 로고·마스코트·폰트를 파일에 내장해, 오프라인에서도 그대로 동작합니다.
