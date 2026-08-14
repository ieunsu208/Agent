# 핀터레스트 레퍼런스 분석 및 Flow 프롬프트 파이프라인 (pin분석.md)

## 1. 레퍼런스 분석 및 프롬프트 생성 프로세스
1. `로고/output/` 폴더 안의 수집된 레퍼런스 이미지의 그래픽 구조, 형태, 라인, 구도, 시각적 요소를 상세 분석합니다.
2. 레퍼런스 이미지의 구도와 **"한국적 여백의 세련미(Neo-Korean Aesthetic)"** 및 **"하이엔드 향수 감성(Haute Perfumery Elegance)"**을 유기적으로 조합하여 **고품질 영문 프롬프트(English Prompt)**를 작성합니다.
   - 마패/말 등의 직접적인 그림 묘사는 완전 배제합니다.
3. 새로운 프롬프트 작성 시 기존 flow.md 파일의 내용을 삭제하지 않고, 파일 끝에 누적(Append)하여 추가 기록합니다.

---

## 2. 하이브리드 영문 프롬프트 조합 공식 (Prompt Formula)
```text
[레퍼런스 이미지 조형 구도] + [Neo-Korean minimalist aesthetic & oriental spatial balance] + [haute perfumery scent diffusion motif] + [monochrome black on pure white background]
```

- **필수 포함 키워드**:
  - `Neo-Korean minimalist aesthetic` (한국적 미니멀리즘 감성)
  - `haute perfumery fragrance logo mark` (하이엔드 향수 브랜드 마크)
  - `subtle oriental spatial balance & elegance` (정갈한 공간과 여백의 미)
  - `scent diffusion & olfactory depth motif` (향의 은은한 확산과 농도)

- **자동 제외 키워드 (Negative)**:
  - `Mapae`, `horse medallion`, `chinese illustration`, `colored`, `gradient`, `3d mockup`, `photo`, `texture`

---

## 3. 작성 규격 및 저장 형식 (Output Format)
- **저장 위치**: `로고/output/flow.md`
- **언어 규격**: 반드시 **영문(English)** 작성
- **누적 저장 수칙**: 새로운 프롬프트 작성 시 기존 flow.md 파일의 내용을 삭제하지 않고, 파일 끝에 누적(Append)하여 추가 기록한다.
- **작성 형태**: 
  - 레퍼런스 이미지 파일 이름을 대제목(`# 파일이름.jpg`)으로 작성
  - 대제목 아래쪽에 `**Prompt**:` 및 `**Negative Prompt**:` 구조로 작성

### 📝 flow.md 누적 기재 예시
```markdown
# 로고_레퍼런스_1.jpg

**Prompt**:
A sophisticated haute perfumery logo mark combining Neo-Korean minimalist aesthetic with modern line art, featuring elegant concentric circular lines symbolizing scent diffusion and olfactory layering, refined oriental spatial balance, monochrome black on pure white background, sleek high-end fragrance identity, no 3D effects, no gradient, no mockups

**Negative Prompt**:
color, gradient, 3d mockup, realistic photo, texture, shadow, Mapae illustration, horse picture, chinese style, complex background
```
