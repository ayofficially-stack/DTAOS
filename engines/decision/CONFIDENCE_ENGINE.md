# Confidence Engine

Version: 1.0

---

## Purpose

Confidence Engine explains why a decision recommendation is reliable.

Confidence is not a decorative percentage. It must be supported by Engine findings, Reviewer agreement, Evidence quality, and Risk level.

---

## Confidence Formula

| Component | Weight |
|---|---:|
| Engine Consensus | 40 |
| Reviewer Consensus | 30 |
| Evidence Quality | 20 |
| Risk Adjustment | 10 |

Total = 100

---

## Engine Consensus

Engine Consensus measures whether selected Engines identify the same finding.

Example:

```text
Business Engine: Buyer Benefit 부족
Design Engine: Buyer Benefit visibility 약함
Presentation Engine: Core Message 약함

Consensus: 3 / 3
Score: 40 / 40
```

---

## Reviewer Consensus

Reviewer Consensus measures agreement among selected Reviewers.

Example:

```text
5 reviewers selected
4 reviewers agree
Score: 24 / 30
```

---

## Evidence Quality

Evidence Quality measures whether the recommendation is supported by credible evidence.

Examples:

- 실측 데이터
- 시험성적서
- 특허
- 고객사 PoC
- 논문
- 공식 문서
- 실제 산출물 분석

---

## Risk Adjustment

Risk Adjustment reflects implementation risk.

| Risk Level | Score |
|---|---:|
| Low | 8-10 |
| Medium | 4-7 |
| High | 0-3 |

---

## Decision Output Requirement

Each major decision must include:

```text
Decision:
Engine Consensus:
Reviewer Consensus:
Evidence Quality:
Risk Adjustment:
Final Confidence:
Reason:
Missing Evidence:
Next Validation:
```

---

## Fail Conditions

Confidence must not be used if:

- no Engine result exists
- no Reviewer result exists for high-stakes work
- evidence is missing
- risk is unknown
- percentage is not explained

---

## Status

Version: 1.0

Architecture: Approved
