# 하이엔드 향수 브랜드 로고 레퍼런스 및 Flow 프롬프트 작성 가이드 (logo.md)

## 1. Flow 이미지 생성 기능 활용 및 프롬프트 작성 규칙
- **이미지 레퍼런스 분석**: `참고 자료/` 폴더 안의 로고 레퍼런스 이미지를 분석하여 Flow AI 이미지 생성 도구에서 고품질 심볼 마크를 생성할 수 있는 프롬프트를 작성한다.
- **영문 프롬프트 작성**: 작성하는 모든 프롬프트(Prompt) 및 부정 프롬프트(Negative Prompt)는 **영문(English)**으로 작성한다.
- **재실행 제약 수칙 (Execution Guard)**: 이미 실행 및 작성 완료된 이미지 프롬프트는 사용자의 **"재실행"** 명령이 입력되기 전까지 임의로 다시 작성하거나 덮어쓰지 않는다.
- **출력 파일 위치 및 작성 규격**:
  - 작성된 프롬프트 결과물은 `output/flow.md` 파일에 누적(Append)하여 저장한다.
  - 레퍼런스 이미지 파일 이름을 대제목(`# 파일이름.jpg`)으로 작성하고, 그 아래쪽에 `**Prompt**:` 및 `**Negative Prompt**:` 양식으로 프롬프트를 기록한다.

---

## 2. 브랜드 컨셉 및 디자인 제약 조건 (Core Specs)
- **브랜드 컨셉**: 전통 마패를 현대적 오브제로 재해석하여, 향의 농도로 일상의 깊이를 더하는 향수 브랜드
- **배경색**: 흰색 고정 (Pure Flat White Background, `#FFFFFF`)
- **로고색**: 단색 검정 고정 (Monochrome / Solid Black, `#000000`)
- **디자인 스타일**: 현대적 한국적 여백미(Neo-Korean Minimalist Aesthetic), 하이엔드 향수 감성(Haute Perfumery Elegance), 미니멀 2D 플랫 라인 아트 및 정갈한 메달리온/엠블럼 심볼 마크

---

## 3. 프롬프트 작성 원칙 및 금지 조건 (Prompt Separation & Negative Rules)
1. **프롬프트 역할 분리 원칙 (Positive Only vs. Negative Only)**:
   - **`Prompt`**: 무엇을 그릴지(What to draw)만 순수 긍정문으로 명확히 묘사한다. 긍정 프롬프트 본문 내에 `no text`, `no 3d`, `no mockups` 등의 'no ~' 부정어 작성을 엄격히 금지한다.
   - **`Negative Prompt`**: 배제할 모든 요소(글자, 3D, 목업, 색상, 왜색, 중국풍 등)를 전담하여 일괄 기술한다.
2. **배경색 및 로고색 고정**:
   - `Prompt`: `monochrome solid black on pure flat white background`
   - `Negative Prompt`: `color, gradient, colorful, dark background, gray background`
3. **목업(Mockup) 및 3D 배제 (Negative Prompt 전담)**:
   - `Negative Prompt`: `3d effects, 3d mockup, realistic photo, texture, shadow, paper texture, embossing, bottle mockup, card mockup`
4. **텍스트 / 글자 / 문자 완전 배제**:
   - `Prompt`: `standalone symbol mark only, flat 2D graphic emblem`
   - `Negative Prompt`: `text, letters, words, font, typography, alphabet, brand name, signature, watermark`
5. **복잡하고 과도한 디테일 배제**:
   - `Prompt`: `clean simple vector lines`
   - `Negative Prompt`: `complex lines, cluttered lines, overly detailed, ornate patterns, complex background`
6. **중국풍 및 일본풍(왜색) 클리셰 디테일 절대 금지 (Strict No-Chinese & No-Japanese Rule)**:
   - `Prompt`: 오직 **순수한 한국 고유의 절제미와 여백의 미(Neo-Korean Minimalist Aesthetic)** 및 **전통 마패(馬牌) 인장 조형**만을 적용
   - `Negative Prompt`: `chinese style, chinese motifs, chinese patterns, japanese style, japanese motifs, japanese crest, kamon, zen circle, torii, japanese patterns`
7. **프롬프트 본문 내 파일명/참조 문구 언급 절대 금지 (Pure Standalone Prompts)**: 프롬프트 본문(`**Prompt**:`) 내에 특정 레퍼런스 이미지 파일명(예: `참고1.jpg`, `로고 초안N.png` 등)이나 `inspired by [파일명]`, `based on [이미지명]`과 같은 사진/파일 직접 지칭 문구를 절대 포함하지 않는다.
8. **동일/중복 이미지 수집 및 분석 배제 (Strict No Duplicates)**: 레퍼런스 수집 및 프롬프트 생성 시 기존에 이미 수집된 이미지와 동일하거나 중복되는 이미지는 엄격히 제외한다. 반드시 파일 해시(SHA-256) 및 시각적 조형 구조를 검증하여 100% 상호 독립적이고 독창적인 레퍼런스만을 다룬다.

---

## 4. `output/flow.md` 작성 규격 예시
```markdown
# 참고 이미지.jpg

**Prompt**:
A sophisticated haute perfumery logo mark combining Neo-Korean minimalist aesthetic with modern line art, reinterpreting the traditional Korean Mapae horse token into a contemporary fragrance icon. Featuring an abstract horse head silhouette with sleek horizontal mane lines symbolizing scent diffusion, topped with a delicate starburst motif representing fragrance concentration, monochrome solid black on pure flat white background, standalone symbol mark only, clean simple vector lines, flat 2D graphic emblem

**Negative Prompt**:
text, letters, words, font, typography, alphabet, brand name, color, gradient, 3d effects, 3d mockup, realistic photo, texture, shadow, paper texture, chinese style, chinese motifs, chinese patterns, japanese style, japanese motifs, japanese crest, kamon, zen circle, torii, complex background, ornate patterns, complex lines, cluttered lines
```