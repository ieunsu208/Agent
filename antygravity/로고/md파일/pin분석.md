# 핀터레스트 레퍼런스 분석 및 Flow 프롬프트 파이프라인 (pin분석.md)

## 1. 레퍼런스 분석 및 프롬프트 생성 프로세스
1. 핀터레스트(Pinterest) 탐색/캡처를 통해 `로고/output/` 폴더에 수집된 레퍼런스 이미지의 그래픽 구조, 형태, 라인, 구도, 시각적 요소를 상세 분석합니다.
2. 레퍼런스 이미지의 구도와 **"한국적 여백의 세련미(Neo-Korean Aesthetic)"** 및 **"하이엔드 향수 감성(Haute Perfumery Elegance)"**을 유기적으로 조합하여 **고품질 영문 프롬프트(English Prompt)**를 작성합니다.
   - **프롬프트 분리 원칙**: 긍정 프롬프트(`Prompt`)에는 `no ~` 부정어를 쓰지 않고 순수 긍정문(`standalone symbol mark only, clean simple vector lines`)으로만 구성하며, 글자/텍스트/3D/목업 등 배제할 요소는 `Negative Prompt`에 전담 배치합니다.
3. 새로운 프롬프트 작성 시 기존 flow.md 파일의 내용을 삭제하지 않고, 파일 끝에 누적(Append)하여 추가 기록합니다.

---

## 2. 하이브리드 영문 프롬프트 조합 공식 (Prompt Formula)
```text
[레퍼런스 이미지 조형 구도] + [Neo-Korean minimalist aesthetic & oriental spatial balance] + [haute perfumery scent diffusion motif] + [monochrome solid black on pure flat white background] + [standalone symbol mark only, clean simple vector lines, flat 2D graphic emblem]
```

- **긍정 프롬프트 필수 포함 키워드**:
  - `Neo-Korean minimalist aesthetic` (한국적 미니멀리즘 감성)
  - `haute perfumery fragrance logo mark` (하이엔드 향수 브랜드 마크)
  - `subtle oriental spatial balance & elegance` (정갈한 공간과 여백의 미)
  - `scent diffusion & olfactory depth motif` (향의 은은한 확산과 농도)
  - `standalone symbol mark only, clean simple vector lines, flat 2D graphic emblem` (순수 긍정 심볼 마크 전용 지시어)

- **수집 및 프롬프트 규칙**:
  - 핀터레스트 레퍼런스 수집 시 컬러(색상)가 있는 로고 이미지 수집 허용. (단, 목업 로고 제외)
  - `flow.md` 프롬프트 작성 시에는 수집 이미지의 색상과 무관하게 **배경은 순수 흰색 (`pure flat white background`)**, **로고색은 단색 검정 (`monochrome solid black`)**으로 고정 작성.
  - 모든 부정/제외 지시어는 `Negative Prompt`에 일괄 기재.

---

## 3. 작성 규격 및 저장 형식 (Output Format)
- **저장 위치**: `로고/output/flow.md`
- **언어 규격**: 반드시 **영문(English)** 작성
- **누적 저장 수칙**: 새로운 프롬프트 작성 시 기존 flow.md 파일의 내용을 삭제하지 않고, 파일 끝에 누적(Append)하여 추가 기록한다.
- **중복 이미지 배제 수칙**: 동일/중복 이미지는 수집 및 프롬프트 생성 대상에서 엄격히 제외하며, 100% 독창적인 고유 레퍼런스만을 대상으로 분석 및 프롬프트 작성을 수행한다.
- **연속 번호 대제목 수칙**: 동일 초안(예: `로고 초안5.jpg`)에 대해 이미 기존 `참고1`~`참고3`이 존재하는 상태에서 추가 수집을 수행할 경우, 덮어쓰지 않고 연장된 번호(`# 로고 초안5_참고4.jpg` ...)를 대제목으로 사용하여 누적 기록한다.
- **작성 형태**: 
  - 레퍼런스 이미지 파일 이름을 대제목(`# 파일이름.jpg`)으로 작성
  - 대제목 아래쪽에 `**Prompt**:` 및 `**Negative Prompt**:` 구조로 작성

### 📝 flow.md 누적 기재 예시
```markdown
# 로고_레퍼런스_1.jpg

**Prompt**:
A sophisticated haute perfumery logo mark combining Neo-Korean minimalist aesthetic with modern line art, featuring elegant concentric circular lines symbolizing scent diffusion and olfactory layering, refined oriental spatial balance, monochrome solid black on pure flat white background, sleek high-end fragrance identity, standalone symbol mark only, clean simple vector lines, flat 2D graphic emblem

**Negative Prompt**:
text, letters, words, font, typography, alphabet, brand name, color, gradient, 3d effects, 3d mockup, realistic photo, texture, shadow, Mapae illustration, horse picture, chinese style, japanese style, complex background, cluttered lines, complex lines, ornate patterns
```
