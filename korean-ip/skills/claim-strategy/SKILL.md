---
name: claim-strategy
description: >
  Build a Korean patent claim strategy before drafting claim language. Use after
  invention intake or prior-art review to define the protection target, candidate
  independent-claim architecture, fallback layers, claim categories, actor/
  implementation boundaries, unity issues, and description-support plan. This
  skill does not determine patentability or draft the final claims.
last_verified: 2026-10-02
freshness_window: 6 months
freshness_category: regulatory
verified_against:
  - https://www.law.go.kr/lsLawLinkInfo.do?chrClsCd=010202&lsJoLnkSeq=1000690062
  - https://www.law.go.kr/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030488019
  - https://law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030489313
  - https://law.go.kr/lsLinkCommonInfo.do?chrClsCd=010202&lspttninfSeq=121414
  - https://law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lspttninfSeq=121419
  - https://kipo.go.kr/ko/kpoContentView.do?menuCd=SCD0200146
---

# Korean Patent Claim Strategy

**Status: DRAFT**

## Purpose

Decide **what the claims should protect and how the claim set should be structured** before writing claim language.

This skill sits between:
- invention intake / prior-art analysis; and
- claim drafting.

It produces a strategy map, not final claims.

## Source register

Read:
`../../references/korean-patent-drafting-sources.md`

Distinguish legal requirements from drafting heuristics.

## Required inputs

Use as much of the following as is available:
- invention disclosure / inventor interview notes;
- drawings or architecture diagrams;
- known prior art or prior-art search result;
- product/process description;
- business-critical feature or design-around concern;
- contemplated jurisdictions;
- intended filing timing;
- known implementation variants.

If prior art has not been searched, do not pretend the broadest proposed claim architecture is novel or inventive.

## Step 1 — Lock the source disclosure

Create a source-state inventory:
- **disclosed** — directly stated/shown in source material;
- **derived** — logical/technical consequence of disclosed facts, clearly identified;
- **asserted** — inventor/client assertion not independently verified;
- **unsupported** — proposed idea not found in the source material.

Never move an `unsupported` feature into the claim strategy as if it were part of the invention.

## Step 2 — State the protection target

Write:
- technical problem;
- core mechanism;
- technical effect;
- commercial/product value;
- foreseeable design-around direction.

Then define the primary protection target in one sentence.

Bad target:
> "protect the whole platform."

Better target:
> "protect the feedback-control relationship that uses X-derived history to change Y within a bounded condition."

The target is a strategy abstraction, not claim language.

## Step 3 — Identify candidate claim subjects

Consider only technically meaningful subjects supported by the invention, such as:
- apparatus/device;
- system;
- method/process;
- manufactured product/composition;
- computer-implemented method;
- computer-readable recording medium or program-related form where appropriate under current Korean practice;
- component/subassembly where it independently captures useful scope.

Do not mechanically create every category.

For each candidate, record:
- who/what practices it;
- what evidence could reveal its practice;
- whether all essential steps/components are under one actor/control boundary;
- whether it protects the commercial risk that actually matters.

## Step 4 — Build the feature hierarchy

Classify features for **strategy purposes**:

### Core mechanism
Features/relationships without which the identified inventive mechanism changes materially.

### Broad-support features
Features not necessarily in the minimum independent architecture but useful to clarify boundaries or avoid over-abstraction.

### Fallback features
Narrowing or additional features that may become useful against prior art or during examination.

### Embodiment features
Implementation details useful in the description but not necessarily worth claiming initially.

### Unsupported proposals
Ideas not actually disclosed. Keep them out of the filing strategy unless the inventor confirms/supports them before filing.

This classification is a drafting heuristic, not a legal test of "essential elements."

## Step 5 — Draft independent-claim architectures, not prose

For each candidate independent claim, create an architecture table:

| Layer | Proposed limitation concept | Why present | Source basis | Prior-art question |
|---|---|---|---|---|
| subject | system / method / etc. | actor/category | ... | ... |
| core 1 | ... | captures mechanism | ... | ... |
| relationship | ... | distinguishes simple aggregation | ... | ... |
| result/condition | ... | boundary if needed | ... | ... |

Aim for the minimum architecture that still:
- captures the disclosed inventive mechanism;
- remains understandable and supported;
- does not rely only on a desired result;
- avoids unnecessary embodiment-specific narrowing unless strategically justified.

Do not label the architecture "broadest patentable claim."

## Step 6 — Build a fallback ladder

Create ordered fallback positions, for example:
1. core relationship;
2. additional control/data relationship;
3. narrower physical/logical arrangement;
4. parameter/range/condition;
5. specific embodiment or implementation alternative.

Each fallback must identify:
- exact disclosure basis;
- why it may distinguish prior art;
- scope cost;
- whether description expansion is needed before filing.

A fallback with no source basis is not a fallback.

## Step 7 — Claim-set / unity check

Before proposing multiple independent claims:
- identify the common inventive concept;
- identify the same or corresponding technical feature shared across claim subjects;
- check whether the candidate set appears technically interrelated.

Patent Act Article 45 and Enforcement Decree Article 6 govern whether a group of inventions may be in one application.

Output:
- `single-set candidate`;
- `possible unity issue — professional review`;
- `separate invention candidate`.

Do not make a definitive unity ruling from an incomplete prior-art record.

## Step 8 — Description-support plan

Before claim drafting, generate a "must support in description" list:
- every planned independent limitation;
- every fallback limitation;
- terminology definitions/relationships likely to matter;
- alternatives/equivalents of components or steps;
- operation/sequence needed for enablement;
- drawings/figures useful to explain relationships.

This step exists because later amendment is constrained by the originally filed disclosure.

## Step 9 — Strategy output

```markdown
# Claim Strategy — [working title]

## 1. Protection target
- Technical problem:
- Core mechanism:
- Technical effect:
- Commercial target:
- Design-around concern:

## 2. Source state
- Disclosed:
- Derived:
- Asserted:
- Unsupported:

## 3. Candidate claim subjects
[table]

## 4. Independent-claim architectures
[architecture tables]

## 5. Fallback ladder
[table]

## 6. Unity / application-structure check
- Common inventive concept:
- Shared technical feature:
- State:

## 7. Description-support plan
- ...

## 8. Open questions before claim drafting
- ...
```

## Escalation rules

Stop or flag instead of guessing when:
- the core mechanism is not technically clear;
- the proposed differentiating feature is only an inventor assertion;
- prior art is necessary to decide whether an architecture is sensible but no search was run;
- a candidate claim subject requires technology-specific Korean practice not yet checked;
- multiple concepts appear only commercially related, not technically interrelated;
- a planned limitation is unsupported.

## What this skill does not do

- It does not conclude patentability.
- It does not decide final unity.
- It does not draft final claim prose.
- It does not invent undisclosed fallback features.
- It does not force apparatus/method/system/media claim sets where they add no strategic value.
- It does not substitute a business goal for a technical claim limitation.

## Example

**Input:** A cooling apparatus has a chamber, a fluid supply, and a control sequence that triggers liquid-nitrogen supply based on a measured thermal condition. The inventor also mentions an optional pre-cooling step and a specific nozzle geometry.

**Expected behavior:**
- identify the controlled cryogenic-supply relationship as a possible core mechanism if supported;
- treat pre-cooling and nozzle geometry as candidate fallback/embodiment features unless the facts show they are central;
- consider apparatus and method subjects only if both meaningfully capture the invention;
- build the support plan before drafting;
- do not declare the architecture patentable.
