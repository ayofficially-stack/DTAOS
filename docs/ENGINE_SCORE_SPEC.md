# DTAOS Engine Score Specification

Version: 1.0

---

## Purpose

This specification defines how every Engine calculates and explains scores.

A score without basis is invalid.

---

## Required Score Card

Every Engine score must include:

- Metric
- Weight
- Result
- Evidence
- Reason
- Deduction
- Final Score

---

## Evidence Card Format

Each major finding must include:

- Finding
- Evidence
- Impact
- Recommendation
- Confidence

---

## Example

Metric: CTA

Weight: 10

Result: 6

Evidence: CTA is present but weakly emphasized.

Reason: the next action is not visually dominant.

Deduction: -4

---

## Pass Criteria

| Result | Meaning |
|---|---|
| 90-100 | Pass |
| 75-89 | Conditional Pass |
| 0-74 | Fail |

---

## Rules

1. Do not use scores without evidence.
2. Explain every major deduction.
3. Do not average unrelated Engine scores into one conclusion.
4. Use Conditional Pass when output is usable but needs correction.
5. Use Fail when a failure condition is detected.

---

## Relationship with Confidence Engine

Engine Score measures Engine result quality.

Confidence measures final decision reliability.

---

## Status

Version: 1.0

Architecture: Approved
