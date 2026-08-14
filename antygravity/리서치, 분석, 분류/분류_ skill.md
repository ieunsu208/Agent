---
name: data-classification
description: "수집된 리서치 원시 데이터나 텍스트를 사전에 정의된 분류 체계에 따라 맵핑하고, 각 항목의 분류 근거가 포함된 classification-result.md를 작성한다."
argument-hint: "[분류할 대상 원본 데이터 경로]"
disable-model-invocation: true
---

# 사단(Sadan) UX/UI 레퍼런스 데이터 분류 수행

## 0. 담당 조직: 2팀 - 분류 팀 (Classification Team)
* **담당 역할:** 2단계 레퍼런스 데이터 분류 및 `classification-result.md` 작성
* **팀원 체계:** 분류 팀장(총괄 승인), 창의적 팀원(감성/가치관 분류), 직관적 팀원(커머스 분류)

## 데이터 분류 수행

이 Skill은 승인된 원본 데이터를 정해진 기준에 맞게 분류하고 구조화하는 역할만 수행한다. 새로운 데이터를 스스로 창작하거나, 기준에 없는 임의의 카테고리를 생성하지 않으며 별도의 분석 프로세스는 수행하지 않는다.

## 승인 게이트

1. `${CLAUDE_PROJECT_DIR}/CLAUDE.md`와 `output/workflow-status.md`를 읽는다.
2. 이전 단계(예: 데이터 수집)가 `approved`인지 확인한다.
3. `input/taxonomy.md` (분류 기준서)가 존재하는지 확인하고 기준을 숙지한다.
4. 기준 파일이나 원본 데이터가 없으면 사용자에게 무엇이 필요한지 알리고 중단한다.

## 입력

사용자 요청: `$ARGUMENTS`

- 인수가 비어 있으면 신규 수집 데이터(`new_references.txt`)와 기존 리서치 데이터(`master_references.txt`)를 함께 기본 원본 데이터로 사용하여 통합 분류를 수행한다.
- 입력된 원본 데이터(new_references.txt 및 master_references.txt)의 전체 개수와 각각의 고유 식별자(ID) 또는 출처를 파악한다.

## 분류 절차

1. **기준 매핑:** `new_references.txt` 및 `master_references.txt`에 포함된 각 데이터 항목을 읽고 `taxonomy.md` (또는 지정된 분류 체계)에 정의된 대/중/소분류 카테고리에 매핑한다.
2. **우선순위 및 다중 분류:** 한 항목이 여러 기준에 부합할 경우, 가장 핵심적인 '주 분류(Primary)'와 보조적인 '부 분류(Secondary)'를 명확히 나눈다.
3. **근거 추출:** 왜 해당 카테고리로 분류했는지, 데이터 원문에서 1~2문장의 명확한 근거(사실, 키워드)를 추출한다.
4. **예외 처리 (Unclassified):** 기존 분류 기준에 전혀 맞지 않는 항목은 억지로 끼워 넣지 않고 `[미분류/기타]` 항목으로 엄격히 격리한다.

## 작성

1. `templates/classification-template.md`의 필수 구조를 사용한다. (템플릿이 없을 경우 명확한 표 형태로 작성)
2. 분류 결과 표는 다음 열을 포함해야 한다: `[항목명] | [주 분류] | [부 분류] | [분류 근거] | [출처 번호]`
3. 미분류 데이터는 문서 하단의 `[추가 검토 필요 데이터]` 섹션에 따로 모아두고, 필요한 경우 새로운 카테고리 신설을 사용자에게 제안한다.

## 저장과 상태

1. 기존 `output/02_classification/classification-result.md`가 있으면 `archive/` 디렉토리에 타임스탬프 이름으로 보존한다.
2. 새 분류 결과를 `output/02_classification/classification-result.md`에 저장한다.
3. `output/workflow-status.md`에서 분류 단계를 `draft`로 변경한다.
4. 기존 분류 결과가 크게 변경되었으면 다음 단계를 `stale` 상태로 변경하되 파일은 삭제하지 않는다.

## 완료 전 검사

- `master_references.txt`와 `new_references.txt`에 있던 원본 데이터 항목이 단 하나라도 누락되었는가? (원본 개수 = 분류된 개수 + 미분류 개수 일치 확인)
- 기준에 없는 카테고리를 임의로(환각) 만들어냈는가?
- 에이전트의 주관적인 추측이 아닌, 원문에 기반한 분류 근거가 명시되었는가?
- 미분류 항목이 빠짐없이 하단에 기록되었는가?

완료 후 생성된 파일명, 총 분류 완료 항목 수, 미분류 개수, 승인 대상, 다음 명령을 간략히 보고하고 멈춘다.
