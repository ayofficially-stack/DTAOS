# DTAOS Boot Loader

> DeepTech AI Operating System
>
> Boot Document

---

# Purpose

이 문서는 새로운 AI 환경(ChatGPT, Claude, Gemini 등)에서 DTAOS를 빠르게 복원하기 위한 부트 문서이다.

새로운 대화를 시작할 경우 가장 먼저 이 문서를 확인한다.

---

# Current Version

DTAOS v0.2

---

# Current Phase

Foundation Build

---

# Current Sprint

Sprint 3

---

# Current Focus

Build the first AI Employee (S001 Proposal)

---

# Core Documents

Read in the following order.

1 PRINCIPLES.md

2 PROJECT_STATUS.md

3 ARCHITECTURE.md

4 README.md

5 Current Skill README

6 Current Skill File

---

# Current Repository Structure

docs/
knowledge/
personas/
skills/
templates/
workflows/
automation/

---

# AI Operating Rules

- Follow DTAOS Principles.
- Follow current Architecture.
- Review PROJECT_STATUS before starting.
- Do not change architecture without approval.
- Update CHANGELOG when major changes occur.
- Decisions override newly generated assumptions.

---

# Resume Command

When starting a new AI session, use the following instruction.

"DTAOS를 시작합니다.

BOOT.md를 기준으로 DTAOS를 초기화합니다.

PROJECT_STATUS.md를 확인하여 현재 프로젝트 상태를 복원합니다.

If Lessons Learned exists, it becomes part of the operating rules for the current session.

이전 승인 사항, Decision, Lessons, 거부된 방향을 복원한 뒤 작업을 이어갑니다."

---

# Resume Context

Recover the project state in the following order.

1. Project Status
2. Latest Decisions
3. Latest Lessons
4. Active Project Case
   - README.md
   - PROJECT_CONTEXT.md
   - DECISIONS.md
   - REVIEW.md
   - OUTPUTS.md
   - PROJECT_LOG.md
5. Rejected Approaches
6. Preferred Workflow
7. Preferred Deliverable
8. Pending Tasks

Never recreate an approved solution.

Never repeat rejected approaches.

Always continue from the latest validated state.

Recovery Rules

When Latest Decisions or Latest Lessons reference one or more files,

read every referenced file before continuing.

When an Active Project Case exists,

read every project document in the case folder before continuing.

Never assume the contents.

Recover only from the referenced documents.


---

# Startup Checklist

- Restore Project Status
- Restore Current Sprint
- Restore Latest Decisions
- Restore Latest Lessons
- Restore Active Tasks
- Restore AI Employees
- Restore Architecture
- Restore Design Rules
- Restore Open Decisions
- Read Latest Decisions
- Read Latest Lessons
- Read Active Project Case

Then continue the latest unfinished task.


---

## Version Check

During boot:

- Verify document versions.
- Report version mismatches.
- Recommend synchronization before continuing.

---


---

# Repository Access

DTAOS assumes that the AI can access the repository defined for the current session.

If repository access is unavailable:

- Report the limitation immediately.
- Do not fabricate recovery results.
- Recover only from documents that are actually accessible.
- Clearly identify any missing files or unavailable content.

Never infer that a referenced document is empty unless it has actually been read.

GitHub remains the Source of Truth.

---


Status : Active

Last Updated: 2026-07-02