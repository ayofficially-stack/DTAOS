# DTAOS Project Registry

Version: 1.0

---

# Purpose

Project Registry는 DTAOS가 관리하는 모든 Project의 목록이다.

Planner는 사용자가 Project ID만 입력해도
Registry를 통해 Project를 식별한다.

---

# Registered Projects

| Project ID | Name | Status | Priority | Folder |
|------------|------|---------|----------|--------|
| P001 | GrapheneAll White-label Sales Sheet | Active | High | projects/P001_GrapheneAll |
| P002 | DTAOS Development | Active | High | projects/P002_DTAOS |

---

# Lookup Rule

User Input

↓

Project ID

↓

Registry Lookup

↓

PROJECT_CONTEXT.md

↓

Execution

---

# Rules

모든 Project는 Registry에 등록되어야 한다.

중복된 Project ID는 허용하지 않는다.

Status는 Active / Completed / Archived 중 하나를 가진다.

Folder는 실제 Project 경로를 가리킨다.

---

# Status

Registry Active