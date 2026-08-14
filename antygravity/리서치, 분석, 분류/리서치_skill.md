---
name: sadan-research
description: "사단 브랜드 컨텍스트를 바탕으로 타 산업군 80% cross-benchmarking 및 8대 UX 아키타입 기준을 적용하여 유사 사이트를 제외하고 new_references.txt를 작성하는 순수 리서치 스킬 v3.0"
argument-hint: "[리서치 대상 카테고리 또는 키워드]"
disable-model-invocation: true
---

# 프로젝트: 사단(Sadan) 웹사이트 기획 및 자동 리서치 에이전트 지시서 v3.0

---

## 0. 담당 조직: 1팀 - 리서치 팀 (Research Team)
* **담당 역할:** 1단계 UX/UI 레퍼런스 데이터 수집 및 검증
* **팀원 체계:** 리서치 팀장(총괄 및 검증), 창의적 팀원(이종 산업 융합 발굴), 직관적 팀원(이커머스 지표 검증)

---

## 1. 브랜드 컨텍스트 (Brand Identity)

- **브랜드명:** 사단 (士團)
- **브랜드 정의:** 조선 암행어사의 마패 헤리티지를 현대적으로 재해석한 커스텀 레이어링 향수 브랜드
- **핵심 가치:** 유일성, 실용성, 스토리텔링
- **디자인 무드:** 오리엔탈 모던 (Oriental Modern). 한지, 스톤, 자연적 질감과 견고하고 맑은 투명 용기의 시각적 대비. 정갈하고 차분한 미니멀 룩앤필.

## 2. 카테고리 배분 및 8대 UX 아키타입 필수 규칙

1. **향수/뷰티 카테고리:** **최대 20% 이내 엄격 제한** (이솝, 르 라보, 바이레도 등 유사 D2C 반복 배제)
2. **타 산업군 Cross-Benchmarking (최소 80%):** 전통 차(Tea) 블렌딩, 하이엔드 시계/주얼리 커스텀, 전통 공예/박물관 아카이브, 에디토리얼 패션 등
3. **8대 UX 레이아웃 아키타입 분산 필수:**
   - 1) Split-Screen Canvas (50:50 분할)
   - 2) Horizontal Scroll Timeline (가로 스크롤)
   - 3) Interactive Configurator / Builder (실시간 커스텀 조립)
   - 4) Chapter-based Editorial Magazine (챕터 해금형)
   - 5) Interactive Accordion Matrix (아코디언 매트릭스)
   - 6) Full-Bleed Object Showcase (1열 고해상도 포커스)
   - 7) Filter-Driven Dynamic Grid (다차원 필터 갤러리)
   - 8) Minimalist Step-by-Step Flow (단계별 가이드)

## 3. 필수 검증 및 유사성 필터링 (Anti-Similarity)

1. **링크 유효성:** HTTP 200 정상 페이지 필수.
2. **중복 필터:** 루트 도메인/브랜드 중복 제거.
3. **기능 조합 중복 캡:** `2열 Grid + Slide Cart + 향 노트 아코디언` 조합은 전체의 10% 초과 금지.
4. **유사도 스코어 Audit:** 탐색 동선 및 UI 조합이 70% 이상 일치하는 사이트 제거.

## 4. 작성 및 저장 (`new_references.txt`)

- 브랜드 이름:
- 링크: (URL)
- 산업군 카테고리:
- UX 레이아웃 아키타입:
- 주요 프론트엔드 기능:
- 적합한 이유:

## 5. 완료 전 검사 및 최종 응답

- [ ] 향수/뷰티 비율 20% 이내 검증
- [ ] 8대 UX 레이아웃 아키타입 균등 분산 검증
- [ ] 동일 UI 기능 조합 중복 배제 검증

위 작업이 완료되면 어떠한 부연 설명 없이 오직 **"완료"**라는 단어 하나만 응답하고 종료한다.
