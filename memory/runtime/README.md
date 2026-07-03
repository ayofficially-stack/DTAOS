# Runtime Memory

Version: 1.0

---

## Purpose

Runtime Memory는 DTAOS의 현재 작업 상태를 저장한다.

Knowledge는 사실과 지식을 저장하고,

Decision은 판단을 저장하며,

Runtime은 현재 무엇을 하고 있는지를 저장한다.

---

## Components

CURRENT_PROJECT

↓

CURRENT_TASK

↓

NEXT_ACTION

↓

SESSION_STATE

---

## Rule

Runtime Memory는 과거 기록 저장소가 아니다.

항상 현재 상태만 유지한다.