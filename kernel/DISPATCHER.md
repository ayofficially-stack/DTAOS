# DTAOS Dispatcher

Version: 1.0

---

# Purpose

Dispatcher는 DTAOS의 중앙 제어기이다.

사용자의 요청을 분석하여

- 어떤 Project인지
- 어떤 Engine을 사용할지
- 어떤 Knowledge를 읽을지
- 어떤 Workflow를 실행할지
- 어떤 Persona를 선택할지를 결정한다.

Dispatcher는 절대 직접 답변하지 않는다.

---

# Execution Pipeline

User Request

↓

Intent Analysis

↓

Project Detection

↓

Engine Selection

↓

Knowledge Loading

↓

Workflow Selection

↓

Adaptive Persona Engine

↓

Quality Gate

↓

Final Output

---

# Intent Categories

## Government

예시

- NET
- 정부과제
- 기술수요조사서
- 사업계획서
- RFP

Engine

Government Proposal Engine

---

## Sales

예시

- Sales Sheet
- White-label
- 회사소개
- 브로셔

Engine

Design Review Engine

Business Review Engine

Presentation Engine

---

## Technical

예시

- Graphene

- Coating

- Carbide

- Composite

- Textile

Engine

Technical Review Engine

---

## Presentation

예시

- PPT

- 발표

- Pitch Deck

Engine

Presentation Engine

---

## Decision

예시

- 투자

- 의사결정

- 우선순위

Engine

Decision Engine

---

# Knowledge Loading Rule

Dispatcher는 Repository 전체를 읽지 않는다.

필요한 Knowledge만 로드한다.

예시

정부과제

↓

skills/S001_Proposal

↓

knowledge/certifications

↓

knowledge/company

↓

knowledge/technology

↓

Active Project

---

영업자료

↓

knowledge/company

↓

knowledge/products

↓

knowledge/lessons

↓

Presentation

---

기술자료

↓

knowledge/technology

↓

knowledge/products

↓

Project Context

---

# Persona Selection

Dispatcher는

Reviewer Pool

10명 중

관련도가 가장 높은

3~5명만 선택한다.

선정 기준

- Task

- Industry

- Target

- Purpose

---

# Routing Table

Government

↓

Government Proposal Engine

↓

Proposal Workflow

↓

Adaptive Persona Engine

↓

Quality Gate

Sales

↓

Business Review

↓

Design Review

↓

Presentation

↓

Adaptive Persona Engine

↓

Quality Gate

Technical

↓

Technical Review

↓

Adaptive Persona Engine

↓

Quality Gate

---

# Output Policy

Dispatcher는

어떤 Engine을 사용했는지

어떤 Persona가 선택되었는지

내부적으로만 관리한다.

사용자가 요청하지 않는 한

내부 동작은 노출하지 않는다.

---

# Core Principle

Always route first.

Never answer first.