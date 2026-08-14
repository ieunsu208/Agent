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

## 3. 금지 조건 (Strict Prohibitions & Negative Rules)
1. **색상이 들어간 로고 금지**: 수집/참고한 레퍼런스 이미지에 색상이 있더라도 프롬프트는 무조건 **순수 흰색 배경 (`pure white background`)** 및 **단색 검정 로고 (`monochrome solid black`)**로 고정한다.
2. **목업(Mockup) 로고 절대 금지**: 3D 입체 효과, 종이 엠보싱, 질감(texture), 그림자(shadow), 패키지/병/명함 합성 목업 금지 (`no 3d effects, no mockup, no realistic photo, no shadow, no paper texture`).
3. **텍스트 / 글자 / 문자 포함 절대 금지**: 알파벳, 한글, 브랜드명, 폰트, 타이포그래피 완전 배제 (`symbol mark only, no text, no letters, no words, no font, no typography`).
4. **복잡하고 과도한 디테일 금지**: 지나치게 복잡한 선이나 조밀한 pattern 제외 (`clean simple vector lines, no complex lines, no cluttered lines`).
5. **중국풍 및 일본풍(왜색) 클리셰 디테일 절대 금지 (Strict No-Chinese & No-Japanese Rule)**:
   - 중국 전통 문양, 한자, 용/봉황, 과도한 오리엔탈 장식 배제 (`no chinese style, no chinese motifs, no chinese patterns`)
   - 일본 전통 가몬(家紋, Kamon), 토리이, 젠(Zen) 엔소 서클, 와비사비 등 왜색 요소 완전 배제 (`no japanese style, no japanese motifs, no japanese crest, no kamon, no zen circle, no torii, no japanese patterns`)
   - 오직 **순수한 한국 고유의 절제미와 여백의 미(Neo-Korean Minimalist Aesthetic)** 및 **전통 마패(馬牌) 인장 조형**만을 적용한다.
6. **프롬프트 본문 내 파일명/참조 문구 언급 절대 금지 (Pure Standalone Prompts)**: 프롬프트 본문(`**Prompt**:`) 내에 특정 레퍼런스 이미지 파일명(예: `참고1.jpg`, `로고 초안N.png` 등)이나 `inspired by [파일명]`, `based on [이미지명]`과 같은 사진/파일 직접 지칭 문구를 절대 포함하지 않는다. 레퍼런스는 조형적 감각을 도출하는 도구로만 사용하고, 프롬프트는 독립적인 **브랜드 컨셉, 조형적 구성, 선의 흐름, 미학적 특성**만을 순수하게 서술하여 독창적인 심볼 마크를 생성하도록 작성한다.

---

## 4. `output/flow.md` 작성 규격 예시
```markdown
# 참고 이미지.jpg

**Prompt**:
A sophisticated haute perfumery logo mark combining Neo-Korean minimalist aesthetic with modern line art, reinterpreting the traditional Korean Mapae horse token into a contemporary fragrance icon. Featuring an abstract horse head silhouette with sleek horizontal mane lines symbolizing scent diffusion, topped with a delicate starburst motif representing fragrance concentration, monochrome solid black on pure flat white background, symbol mark only, clean simple vector lines, no text, no letters, no words, no 3D effects, no gradient, no mockups

**Negative Prompt**:
japanese style, japanese motifs, japanese crest, kamon, zen circle, torii, chinese style, chinese motifs, chinese patterns, color, gradient, 3d mockup, paper texture, shadow, text, letters, words, font, typography, complex background, realistic photo, ornate patterns
```