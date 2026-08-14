# 핀터레스트 레퍼런스 수집 파이프라인 (pin.md)

## 1. 실행 조건 및 트리거 (Trigger Command)
- **실행 명령어**: `"레퍼런스 수집 시작해"`

## 2. 수집 프로세스 (Collection Process)
1. `로고/input/` 폴더 안의 이미지(예: `로고 초안1.jpg`)의 구조 및 컨셉을 분석합니다.
2. `로고/레퍼런스/` 폴더 안의 참고 이미지(예: `레퍼런스 이미지.jpg`) 스타일(흰색 배경, 단색 검정 미니멀 2D 플랫 마크)을 대조하여 반영합니다.
3. 핀터레스트(Pinterest)에서 조건에 부합하는 유사한 레퍼런스 이미지를 캡처/추출합니다.
4. 수집한 이미지를 `로고/output/` 폴더에 `.jpg` 포맷으로 저장 및 생성합니다.

---

## 3. 브랜드 정보 및 디자인 제약 조건 (Core Specs)
- **브랜드 컨셉**: 전통 마패를 현대적 오브제로 재해석하여, 향의 농도로 일상의 깊이를 더하는 향수 브랜드
- **배경색**: 흰색 (Flat White Background, `#FFFFFF`)
- **로고색**: 단색 검정 (Monochrome / Solid Black, `#000000`)
- **디자인 스타일**: 미니멀 2D 플랫 라인 아트, 현대적 엠블럼/원형 메달리온 심볼
- **금지 조건**:
  - 색상이 들어간 로고 (컬러, 그라데이션 금지)
  - 목업(Mockup)이 되어있는 로고 (3D 효과, 종이 엠보싱, 패키지 합성 제외)

---

## 4. 핀터레스트 레퍼런스 탐색 검색어 (Pinterest Search Queries)
- `black and white minimalist medallion logo design`
- `monochrome perfume brand logo symbol flat`
- `modern traditional seal logo mark black`
- `geometric circular emblem logo design minimalist`
- `minimalist badge logo design black line art`

---

## 5. 자동화(Playwright) 필터링 규칙 (Scraping Rules)
- **포함 키워드**: `logo design`, `minimalist logo`, `monochrome logo`, `flat logo`, `emblem symbol`
- **제외 키워드**: `mockup`, `3d`, `packaging`, `bottle`, `colored`, `gradient`, `paper`, `emboss`
- **저장 경로**: `로고/output/*.jpg`
