# 핀터레스트 레퍼런스 수집 파이프라인 (pin.md)

## 1. 실행 조건 및 트리거 (Trigger Command)
- **실행 명령어**: `"레퍼런스 수집 시작해"`

## 2. 수집 프로세스 (Collection Process)
1. `로고/input/` 폴더 안의 이미지(예: `로고 초안1.jpg`)의 구조 및 컨셉을 분석합니다.
2. `로고/레퍼런스/` 폴더 안의 참고 이미지(예: `레퍼런스 이미지.jpg`) 스타일(흰색 배경, 단색 검정 미니멀 2D 플랫 마크)을 대조하여 반영합니다.
3. **핀터레스트(Pinterest) 캡처/추출 필수**: 핀터레스트(Pinterest) 웹사이트에서 조건에 부합하는 유사한 레퍼런스 이미지를 Playwright 크롤링/캡처 방식으로 직접 추출합니다.
4. 수집한 이미지를 `로고/output/` 폴더에 `.jpg` 포맷으로 저장 및 생성합니다.

---

## 3. 브랜드 정보 및 디자인 제약 조건 (Core Specs)
- **브랜드 컨셉**: 전통 마패를 현대적 오브제로 재해석하여, 향의 농도로 일상의 깊이를 더하는 향수 브랜드
- **프롬프트 고정 배경색**: 흰색 (Flat White Background, `#FFFFFF`)
- **프롬프트 고정 로고색**: 단색 검정 (Monochrome / Solid Black, `#000000`)
- **디자인 스타일**: 미니멀 2D 플랫 라인 아트, 현대적 엠블럼/원형 메달리온 심볼 (순수 심볼 마크 전용)
- **수집 및 금지 조건**:
  - **컬러 로고 수집 허용**: 핀터레스트 수집 시 색상이 들어간 로고 이미지 수집 가능
  - **목업 로고 절대 제외**: 목업(Mockup)이 되어있는 로고 (3D 효과, 종이 엠보싱, 패키지/명함 합성 제외)
  - **텍스트 배제**: 텍스트/글자/알파벳/브랜드명 제외 (심볼 전용)

---

## 4. 핀터레스트 레퍼런스 탐색 검색어 (Pinterest Search Queries)
- `black and white minimalist medallion logo design`
- `monochrome perfume brand logo symbol flat`
- `modern traditional seal logo mark black`
- `geometric circular emblem logo design minimalist`
- `minimalist badge logo design black line art`

---

## 5. 자동화(Playwright) 필터링 규칙 (Scraping Rules)
- **포함 키워드**: `logo design`, `minimalist logo`, `flat logo`, `emblem symbol` (컬러 수집 허용)
- **제외 키워드**: `mockup`, `3d`, `packaging`, `bottle`, `paper`, `emboss`, `text`, `letters`, `words`, `typography`
- **저장 경로 및 파일명 규칙**: `로고/output/로고 초안N/*.jpg` (각 초안별 하위 폴더 생성 및 저장, 동일 초안 추가 수집 시 해당 폴더의 기존 번호에 이어서 `로고 초안X_참고N.jpg` 번호 연장 및 이미지 보존)
