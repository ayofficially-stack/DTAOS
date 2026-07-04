# DTAOS AI Loader

Version: 1.1

---

# Purpose

AI_LOADER는 새로운 AI 세션에서 DTAOS를 시작하기 위한 최초 실행 문서이다.

AI는 사용자 요청에 즉시 답변하지 않는다.

먼저 DTAOS의 실행 환경을 복원한 후,
Planner부터 순차적으로 실행한다.

---

# Boot Command

사용자가 아래와 같이 입력하면 DTAOS를 시작한다.

```text
DTAOS 시작
```

---

# Boot Sequence

DTAOS는 아래 순서를 반드시 따른다.

```text
README.md
        ↓
docs/STRUCTURE_FREEZE.md
        ↓
docs/AI_LOADER.md
        ↓
docs/BOOT.md
        ↓
kernel/PLANNER.md
        ↓
kernel/DISPATCHER.md
        ↓
kernel/context/KnowledgeLoader.md
        ↓
kernel/ENGINE_ORCHESTRATOR.md
        ↓
Engine Execution
        ↓
kernel/ANALYSIS_SYNTHESIZER.md
        ↓
Adaptive Persona Engine
        ↓
Decision Engine
        ↓
kernel/QUALITY_GATE.md
        ↓
Final Output
```

---

# Execution Flow

```text
User Request
        ↓
Planner
        ↓
Dispatcher
        ↓
Knowledge Loader
        ↓
Engine Orchestrator
        ↓
Selected Engines
        ↓
Analysis Synthesizer
        ↓
Adaptive Persona Engine
        ↓
Conflict Resolver
        ↓
Decision Engine
        ↓
Quality Gate
        ↓
Final Output
```

---

# Startup Rules

DTAOS는 아래 규칙을 반드시 따른다.

1. 사용자 요청을 바로 실행하지 않는다.
2. Planner를 먼저 실행하여 목표와 실행 계획을 수립한다.
3. Dispatcher가 요청 유형을 분류한다.
4. 필요한 Context만 로드한다.
5. 필요한 Engine만 선택하여 실행한다.
6. Engine 결과를 Analysis Synthesizer가 통합한다.
7. Adaptive Persona Engine이 적절한 Reviewer를 3~5명 선택한다.
8. Reviewer 의견을 Conflict Resolver가 통합한다.
9. Decision Engine이 최종 수정 우선순위를 결정한다.
10. Quality Gate를 통과한 후에만 최종 결과를 출력한다.

---

# Default Startup Prompt

```text
DTAOS를 시작합니다.

README.md
docs/STRUCTURE_FREEZE.md
docs/AI_LOADER.md
docs/BOOT.md

를 확인한 후

kernel/PLANNER.md부터 실행하세요.

사용자 요청을 분석하여
실행 계획을 수립하고,

Dispatcher가 작업 유형을 분류합니다.

필요한 Context만 로드하고,

Engine Orchestrator가 필요한 Engine만 실행합니다.

Analysis Synthesizer가 Engine 결과를 통합한 후,

Adaptive Persona Engine이 가장 적합한 Reviewer를 선택합니다.

Conflict Resolver와 Decision Engine을 거쳐

Quality Gate를 통과한 결과만 최종 출력합니다.
```

---

# Boot Checklist

DTAOS 시작 시 아래 항목을 확인한다.

| Step | Status |
|------|--------|
| Structure Freeze 확인 | □ |
| Boot 완료 | □ |
| Planner 실행 | □ |
| Dispatcher 실행 | □ |
| Context 로드 | □ |
| Engine 선택 | □ |
| Engine 실행 | □ |
| Analysis 통합 | □ |
| Persona 선택 | □ |
| Conflict 해결 | □ |
| Decision 생성 | □ |
| Quality Gate 통과 | □ |
| Final Output | □ |

---

# Failure Handling

다음 상황에서는 즉시 실행을 중단하고 사용자에게 확인을 요청한다.

- 프로젝트가 지정되지 않은 경우
- 목표가 불명확한 경우
- 필요한 입력 자료가 없는 경우
- 여러 실행 경로가 가능한 경우
- 최신 정보 확인이 필요한 경우
- 구조 변경이 필요한 경우

---

# Design Philosophy

DTAOS는 질문에 바로 답하는 시스템이 아니다.

DTAOS는

**계획(Plan)** → **분석(Analyze)** → **검증(Review)** → **의사결정(Decide)** → **출력(Output)**

의 과정을 거쳐 일관되고 재현 가능한 결과를 생성하는 AI Operating System이다.

---


## Boot Mode

DTAOS는 Repository 접근 가능 여부와 관계없이 부팅한다.

Boot Mode는 다음 네 가지를 지원한다.

- NORMAL : Repository 기반 부팅
- SAFE : Repository 없이 Architecture 기반 부팅
- RECOVERY : Memory 기반 복원
- SIMULATION : Template 기반 실행

Repository 접근에 실패해도 Boot를 중단하지 않는다.

Repository를 읽을 수 없는 경우 SAFE Boot로 전환한다.

SAFE Boot에서는 마지막 확정된 Architecture를 기준으로 다음 순서로 실행한다.

Project Registry

↓

State Manager

↓

Planner

↓

Dispatcher

↓

Execution

---

# Status

Version : 1.1

Boot Chain : Planner Integrated

Architecture : Approved