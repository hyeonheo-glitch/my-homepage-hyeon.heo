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
| 02 | 대표 제품 | 구운 고구마와 촉촉한 그릴드 닭가슴살 샐러드를 주인공 카드로, 나머지 3종을 서브로 |
| 03 | **점심 고민 해결 버튼** | 시간 · 컨디션 · 목표를 고르면 4개 메뉴 중 하나를 추천하고 근거를 함께 표시. 담은 메뉴는 주간 기록에 누적 |
| 04 | 브랜드 소개 | 미션, 퍼스낼리티(Warm · Fresh · Honest), 슬로건 |
| 05 | 구매처 | 샐러드 업계 1위 배너, 자사몰 · 마켓컬리 · 쿠팡 주문 채널 |

### 점심 고민 해결 버튼

- 시간(2) × 컨디션(5) × 목표(3) = **30가지 조합**
- 무작위 뽑기가 아니라, 제품 설명에서 도출한 가중치(단백질·가벼움·든든함·속편함·에너지)를 **점수화**해 한 개를 고릅니다
- 추천 이유를 근거로 함께 보여줍니다 — `그릴드 닭가슴살이 들어가 단백질을 챙기기 좋아요.`
- 최근 추천은 점수를 깎아, 같은 조합을 다시 눌러도 다른 메뉴가 나옵니다
- 담은 끼니 수와 고른 메뉴 종류는 브라우저 `localStorage`에 저장됩니다

## 파일

| 파일 | 설명 |
|---|---|
| `index.html` | 홈페이지 본체. HTML·CSS·JS가 모두 이 한 파일에 들어 있습니다 |
| `assets/menu/` | 메뉴 사진. 파일을 넣으면 이모지 접시가 자동으로 사진으로 바뀝니다 |
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

## 배포 전 확인 사항

- [ ] `assets/menu/` 에 메뉴 사진 4장 넣기 (없으면 이모지 접시로 표시됩니다)
- [ ] **"샐러드 업계 1위" 근거 표기** — 표시·광고의 공정화에 관한 법률상 순위·최상급
      표현은 조사기관 · 집계 기준 · 기준 시점을 함께 밝혀야 합니다.
      `index.html`의 `.rank-note` 문구를 실제 근거로 교체해 주세요.
- [ ] 마켓컬리 · 쿠팡 링크를 실제 브랜드관 주소로 교체
- [ ] 제품별 칼로리 · 단백질 · 가격 확정 시 영양 표기 복원
