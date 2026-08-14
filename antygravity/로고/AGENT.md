# 로고 레퍼런스 수집 및 분석 에이전트 지침 (로고\AGENT.md)

이 문서는 로고 레퍼런스 수집 및 분석 에이전트의 통합 실행 파이프라인과 작동 규칙을 정의합니다.

---

## 1. 실행 트리거 명령 및 개수 제어 (Trigger Commands)

### 📌 기본 실행 명령어
- **`"실행 시작"`**
  - 지정된 개수가 없을 경우 기본 **1개 레퍼런스 수집 → 1개 레퍼런스 분석**을 순차 실행합니다.

### 📌 개수 지정 실행 명령어
- **`"실행 시작 N"`** (예: `"실행 시작 3"`, `"실행 시작 5"`)
  - 사용자 지정 수량(N개)만큼 레퍼런스 수집과 분석을 파이프라인으로 수행합니다.
  - **수행 규칙**: N개 이미지 핀터레스트 탐색/캡처 → N개 이미지 분석 및 Flow 영문 프롬프트 생성.

---

## 2. 파이프라인 2단계 자동 실행 프로세스 (Pipeline Workflow)

### [1단계] 레퍼런스 탐색 및 수집 (`md파일/pin.md` 기반)
1. `로고/input/` 폴더 내 디자인 초안의 구도 및 기하학 구조를 분석합니다.
2. `로고/레퍼런스/` 폴더 내 참고 스타일의 흑백 미니멀 2D 플랫 그래픽 특성을 대조 반영합니다.
3. **핀터레스트(Pinterest) 탐색/캡처 원칙**: 핀터레스트 웹사이트에서 Playwright 자동화 탐색을 통해 제약 조건(컬러 이미지 수집 허용, 목업/텍스트/복잡한 선 제외)에 맞는 레퍼런스 이미지 N개를 직접 캡처/추출하여 수집합니다. (AI 이미지 직접 생성을 사용하지 않음)
4. 수집된 이미지를 `로고/output/` 폴더에 `.jpg` 파일 포맷으로 저장합니다.

---

### [2단계] 레퍼런스 분석 및 Flow 프롬프트 작성 (`md파일/pin분석.md` 기반)
1. 1단계에서 `로고/output/` 폴더에 저장이 완료된 후 자동으로 2단계를 개시합니다.
2. 수집된 N개 이미지 각 레퍼런스의 visual 조형감과 **한국적 여백의 세련미(Neo-Korean Aesthetic) + 하이엔드 향수 감성(Haute Perfumery Elegance)**을 50:50으로 합성합니다. (마패/말 직관적 그림 및 텍스트/글자 제외)
3. 분석 결과를 바탕으로 AI 이미지 생성 도구(Flow)용 **고품질 하이브리드 영문(English) 프롬프트**를 작성합니다. **(텍스트/글자 완전 배제, 심볼 마크 전용 지시어 `symbol mark only, no text, no letters` 필수 포함)**
4. 새로운 프롬프트 작성 시 기존 flow.md 파일의 내용을 삭제하지 않고, 파일 끝에 누적(Append)하여 추가 기록합니다.

---

## 3. 결과물 작성 및 저장 규격

### 📄 `output/flow.md` 작성 규격
- **누적 저장 수칙**: 새로운 프롬프트 작성 시 기존 flow.md 파일의 내용을 삭제하지 않고, 파일 끝에 누적(Append)하여 추가 기록한다.
- **형식**: 각 레퍼런스 이미지 파일명을 대제목(`# 파일명.jpg`)으로 작성 후, 아래쪽에 Prompt와 Negative Prompt를 영문으로 기술합니다.

```markdown
# 로고_레퍼런스_1.jpg

**Prompt**:
A sophisticated haute perfumery logo mark combining Neo-Korean minimalist aesthetic with modern line art, featuring elegant concentric circular lines symbolizing scent diffusion and olfactory layering, refined oriental spatial balance, monochrome black on pure white background, sleek high-end fragrance identity, symbol mark only, no text, no letters, no words, no 3D effects, no gradient, no mockups

**Negative Prompt**:
text, letters, words, font, typography, alphabet, brand name, color, gradient, 3d mockup, realistic photo, texture, shadow, Mapae illustration, horse picture, chinese style, complex background
```

---

## 4. 예외 처리 및 가드레일 (Safety Rules)

1. **순차 실행 보장**: 1단계(`output/` 이미지 N개 저장)가 완료되기 전에 2단계(분석 및 `flow.md` 생성)를 시작하지 않습니다.
2. **누적 저장 보장**: 새로운 프롬프트 작성 시 기존 flow.md 파일의 내용을 삭제하지 않고, 파일 끝에 누적(Append)하여 추가 기록합니다.
3. **재실행 제약 규칙 (Execution Guard)**: 이미 작성된 `output/`의 이미지 및 `flow.md` 결과물은 사용자가 **"재실행"** 명령을 입력하기 전까지 임의로 덮어쓰거나 재작성하지 않습니다.
4. **직관적 오리엔탈 상징 배제**: 마패 그림이나 중국풍 일러스트가 들어가는 프롬프트를 배제하고 세련된 한국적 여백미와 미니멀리즘만 적용합니다.
5. **텍스트/글자 배제 수칙 (No-Text Policy)**: AI 이미지 생성용 프롬프트 생성 시 글자, 알파벳, 브랜드명, 텍스트가 포함되지 않도록 `no text, no letters, no words`를 명시하고 Negative Prompt에 `text, letters, words, font, typography`를 필수로 넣습니다.
6. **핀터레스트 캡처 필수 원칙**: 레퍼런스 이미지는 AI로 새로 생성하지 않고 반드시 핀터레스트(Pinterest) 수집/캡처 방식으로 확보합니다.
7. **연속 번호 부여 및 기존 이미지 보존 (Sequential Preservation)**: 동일 초안 파일명(예: `로고 초안5.jpg`)으로 이미지 수집을 추가 실행할 때, `로고/output/` 폴더에 기존 파일(예: `로고 초안5_참고1.jpg` ~ `로고 초안5_참고3.jpg`)이 이미 존재하는 경우 절대 기존 이미지를 삭제하거나 덮어쓰지 않으며, 기존 마지막 번호 다음 번호(예: `로고 초안5_참고4.jpg`, `로고 초안5_참고5.jpg` ...)로 연장 부여하여 저장하고 `flow.md`에도 새 번호 파일명으로 누적 기록합니다.
8. **복잡하고 선이 많은 로고 배제 (No Complex/Cluttered Lines)**: 지나치게 복잡하거나 선이 빽빽한 과도한 디테일 디자인은 배제하고 정갈하고 명확한 미니멀 그래픽 라인(`clean simple vector lines, no complex lines`)만 프롬프트로 작성하며 Negative Prompt에 `complex lines, cluttered lines, overly detailed, ornate patterns`를 명시합니다.
9. **컬러 이미지 수집 허용 및 프롬프트 흑백/흰색 배경 고정 수칙 (Color Collection Allowed & Black-on-White Prompt Fixed)**: 핀터레스트 탐색 시 색상(컬러)이 들어간 로고 이미지도 레퍼런스로 수집 가능하지만 목업(Mockup) 로고는 엄격히 제외하며, `flow.md` 프롬프트 작성 시에는 수집 이미지의 색상과 관계없이 배경은 흰색(`pure white background`), 로고색은 단색 검정(`monochrome solid black`)으로 고정 작성합니다.
10. **초안별 하위 폴더 자동 정리 (Draft Subfolder Organization)**: 수집된 레퍼런스 이미지는 `로고/output/` 바로 아래에 늘어놓지 않고, 각 초안별 하위 폴더(`로고/output/로고 초안N/`)를 생성하여 체계적으로 분류 및 저장합니다.
