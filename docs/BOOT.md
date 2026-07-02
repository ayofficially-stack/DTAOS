# DTAOS Boot Loader

> DeepTech AI Operating System
>
> Boot Document

---

# Purpose

이 문서는 새로운 AI 환경(ChatGPT, Claude, Gemini 등)에서 DTAOS를 빠르게 복원하기 위한 부트 문서이다.

새로운 대화를 시작할 경우 가장 먼저 이 문서를 확인한다.

The goal of BOOT is not to initialize DTAOS.

The goal of BOOT is to resume DTAOS from its latest validated state.

---

# Current Execution State

Managed by NEXT.md

---

# Core Documents

1 PRINCIPLES.md

2 ARCHITECTURE.md

3 Specification/Documentation.md

4 Specification/Boot_Recovery.md

5 NEXT.md

6 PROJECT_STATUS.md

7 README.md

8 Current Skill README

9 Current Skill File

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
- Restore the current execution state from NEXT.md before reading PROJECT_STATUS.md.
- Do not change architecture without approval.
- Update CHANGELOG when major changes occur.
- Decisions override newly generated assumptions.
- Read only existing files.
- Never infer Resume Action.
- Resume from NEXT.md.
- Load only knowledge related to the active project.

---

# Resume Command

When starting a new AI session, use the following instruction.

"DTAOS를 시작합니다.

BOOT.md를 기준으로 DTAOS를 초기화합니다.

NEXT.md를 확인하여

현재 Execution State를 복원합니다.

그 이후 PROJECT_STATUS.md를 확인하여

현재 프로젝트를 복원합니다. 

If Lessons Learned exists, it becomes part of the operating rules for the current session.

이전 승인 사항, Decision, Lessons, 거부된 방향을 복원한 뒤 작업을 이어갑니다."

---

# Resume Context

Recover the project state in the following order.

1. Execution State (NEXT.md)
2. Project Status
3. Latest Decisions
4. Latest Lessons
5. Active Project Case
   - README.md
   - PROJECT_CONTEXT.md
   - DECISIONS.md
   - REVIEW.md
   - OUTPUTS.md
   - PROJECT_LOG.md
6. Related Lessons
7. Related Technology
8. Related Templates
9. Rejected Approaches
10. Pending Tasks

Never recreate an approved solution.

Never repeat rejected approaches.

Always continue from the latest validated state.

---


# Recovery Rules

When Latest Decisions or Latest Lessons reference one or more files,

read every referenced file before continuing.

When an Active Project Case exists,

read every project document in the case folder before continuing.

Never assume the contents.

Recover only from the referenced documents.

Read only documents required for
the active project.

Do not restore unrelated knowledge.


---

## Startup Checklist

- Restore Current Execution State
- Restore Project Status
- Restore Resume Action
- Restore Latest Decisions
- Restore Latest Lessons
- Restore Active Tasks
- Restore AI Employees
- Restore Architecture
- Restore Design Rules
- Restore Open Decisions
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