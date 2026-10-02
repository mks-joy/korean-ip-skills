---
name: invention-intake
description: >
  Structure and screen a Korean patent invention disclosure before prior-art
  searching or claim drafting. Use when an inventor, client, engineer, or patent
  professional provides an invention idea and needs the technical core,
  disclosure urgency, missing facts, possible multiple invention concepts,
  detectability, and next-step search questions organized. This skill does not
  conclude that an invention is patentable.
last_verified: 2026-10-02
freshness_window: 6 months
freshness_category: regulatory
verified_against:
  - https://www.law.go.kr/lsSc.do
  - https://kipo.go.kr/ko/kpoContentView.do
  - https://www.kipo.go.kr/ko/kpoContentView.do
---

# Korean Patent Invention Intake

**Status: DRAFT**

## Purpose

Turn an incomplete invention disclosure into a structured package that a Korean patent professional can use for:
- inventor follow-up;
- prior-art searching;
- filing-strategy discussion;
- claim-strategy preparation.

This skill is an **intake and issue-spotting workflow**, not a patentability opinion and not a prior-art search.

## Source register

Before relying on a legal-rule-bearing part of this workflow, read:

`../../references/korean-patent-invention-intake-sources.md`

If the freshness window has expired, or a current filing/deadline decision depends on the rule, verify the current official source before using the rule.

## Inputs

If the user supplies a disclosure document, extract what is already present and ask only for missing material facts.

Otherwise ask in one batch:

1. **Problem.** What technical or operational problem is being solved?
2. **Core mechanism.** What actually causes the improvement? Describe components, data flow, control flow, physical relationship, or processing sequence.
3. **Prior approach.** What was done before, and what limitation does this approach overcome?
4. **Difference.** Which features or relationships are believed to be new or non-routine?
5. **Alternatives.** What substitutions, variations, optional components, parameter ranges, or fallback implementations exist?
6. **Inventors.** Who contributed to the inventive concepts, and what did each contribute?
7. **Disclosure history.** Has any part been published, presented, sold, offered, demonstrated, released, posted online, supplied to a customer, included in an RFP/proposal, or otherwise disclosed outside the organization? Give dates and confidentiality conditions.
8. **Product status.** Paper concept, prototype, pilot, shipping product, internal process, or customer deployment?
9. **Business scope.** Which part is core differentiation, and where is protection actually valuable?
10. **Target jurisdictions/timing.** Korea only or foreign filing expected? Any imminent release, paper, exhibition, funding/demo, or customer delivery?

Do not force the user to retype information already in the supplied material.

## Workflow

### Step 1 — Build the invention model

Produce:

- one-sentence technical problem;
- one-sentence core inventive concept;
- key components/steps and their relationships;
- asserted technical effect/advantage;
- alternatives and optional features;
- facts that are missing.

Separate:
- **source fact** — stated in the disclosure;
- **inventor assertion** — e.g. "competitors do not do this";
- **analysis/inference** — your interpretation;
- **unknown** — not supported yet.

Never turn an inventor assertion into a verified prior-art fact.

### Step 2 — Identify candidate invention concepts

Ask whether the disclosure contains one core concept or several independently protectable concepts.

Do not make a final legal unity-of-invention determination here.

Create a candidate-concept table:

| Candidate | Technical problem | Core mechanism | Can stand independently? | Shared core with others | Follow-up needed |
|---|---|---|---|---|---|

Split concepts when, for example:
- they solve materially different technical problems;
- one can be removed without changing the other's inventive mechanism;
- separate products/actors practice them;
- different prior art is likely to control the analysis.

Keep them linked when they are merely embodiments, parameter choices, implementation alternatives, or downstream effects of the same core mechanism.

### Step 3 — Korean patentability issue screen

This is a **screen for what must be investigated**, not a conclusion.

#### A. Statutory invention / technology-specific issue

Check whether the disclosure describes a concrete technical creation rather than only a desired result, rule, or abstract business objective.

For AI/software, biotech, semiconductor, digital-health, robotics, and other covered fields, route close questions to the current technology-field examination practice guide. Do not substitute US §101/Alice terminology for Korean practice.

State:
- `no obvious intake issue`;
- `needs technology-specific review`; or
- `insufficient technical detail`.

#### B. Novelty signals

Without searching prior art, ask:
- what exact feature or relationship is said to be new?
- is the novelty merely a new use/domain for a known technique?
- does the disclosure itself identify an existing product/paper/patent doing the same thing?
- is the asserted difference actually an implementation detail or parameter choice?

Output only:
- `clear enough to search`;
- `self-identified prior-art concern`;
- `insufficient differentiation facts`.

Never output "novel" from intake alone.

#### C. Inventive-step signals

Without a prior-art search, flag facts relevant to Patent Act Article 29(2), such as:
- predictable combination of known components;
- routine optimization or parameter tuning;
- unexpected technical effect;
- prior approach teaching away from the proposed mechanism;
- a long-standing technical problem with a non-routine mechanism.

Output only what should be tested in the prior-art search. Do not conclude "inventive" or "obvious."

### Step 4 — Disclosure urgency

Treat disclosure facts as high priority.

If there has been any external disclosure:
1. capture the exact date;
2. capture what information was disclosed;
3. capture audience/access;
4. capture whether confidentiality obligations existed;
5. flag whether foreign filing is contemplated.

For Korea, Patent Act Article 30 contains an exception for certain disclosures within 12 months, subject to statutory conditions and procedural requirements.

Therefore:
- do **not** say a disclosure is harmless;
- do **not** advise intentional pre-filing disclosure;
- if a potentially relevant disclosure occurred, mark **TIME-SENSITIVE — Article 30 review required**;
- verify the current statute/procedure for a live filing.

If foreign filing is contemplated, state separately that foreign novelty/grace-period treatment must be checked by jurisdiction.

### Step 5 — Filing-delay / first-to-file signal

Patent Act Article 36 is a reason to surface unnecessary delay where identical competing inventions could be filed.

Do not speculate that a competitor has filed.

If the technology is fast-moving, already customer-facing, or known to competitors, add:
`Filing timing should be reviewed promptly; no competitor filing check was performed.`

### Step 6 — Detectability and enforcement value

Ask: if a competitor practiced the claimed concept, could the patentee realistically detect evidence of the practice?

Classify:
- **high detectability** — visible product structure, public protocol/API behavior, externally observable process/result strongly tied to the mechanism;
- **medium** — requires teardown, testing, reverse engineering, or discovery;
- **low** — secret server-side processing, internal manufacturing details, training-data/training-process details, inaccessible back-office logic.

Low detectability is a **strategy-review trigger**, not a reason to reject patenting automatically. Surface a patent-vs-trade-secret discussion.

### Step 7 — Search handoff

Do not conduct a prior-art search unless the user separately asks for one or invokes the search skill.

Prepare the search handoff:
- candidate invention concepts;
- essential features;
- optional features;
- synonyms and technical terms;
- known products/papers/patents named by the user;
- likely search directions;
- questions the search must answer.

### Step 8 — Output

Use this structure:

```markdown
# Invention Intake — [working title]

## Intake status
[READY FOR PRIOR-ART SEARCH / NEEDS INVENTOR FACTS / TIME-SENSITIVE DISCLOSURE REVIEW / STRATEGY REVIEW]

## 1. Technical core
- Problem:
- Core mechanism:
- Technical effect:
- Key relationships:
- Alternatives:

## 2. Candidate invention concepts
[table]

## 3. Patentability issues to investigate
- Statutory/technology-specific:
- Novelty search question:
- Inventive-step search question:

## 4. Disclosure and timing
- Disclosure events:
- Article 30 review:
- Foreign filing issue:
- First-to-file timing signal:

## 5. Detectability / patent-vs-trade-secret
- Detectability:
- Why:
- Strategy question:

## 6. Missing facts
- [fact]
- [fact]

## 7. Prior-art search handoff
- Essential concepts:
- Search terms:
- Known references:
- Questions to resolve:

## Source state
- Verified source facts:
- User/inventor assertions:
- Inferences:
- Unknowns:
```

## Escalation rules

Stop and surface the issue rather than guessing when:
- the disclosure date is uncertain but potentially rights-affecting;
- inventorship contributions are disputed or unclear;
- the invention spans a field requiring specialist examination practice;
- the technical mechanism is too vague to distinguish from a desired result;
- the user asks for a definitive patentability conclusion without a prior-art search;
- current law/procedure cannot be verified.

## What this skill does not do

- It does not conclude that an invention is patentable or unpatentable.
- It does not perform a prior-art search.
- It does not draft claims or a specification.
- It does not decide inventorship disputes.
- It does not decide whether Article 30 ultimately applies to a particular disclosure.
- It does not assume Korean rules apply to foreign filings.
- It does not choose patent protection over trade-secret protection for the user.

## Example

**Input:** A factory camera system detects a recurring defect, links the defect pattern to the immediately preceding tool-state sequence, and automatically changes only the suspected process parameter within a bounded range. The inventor says conventional systems detect defects but require a human to trace the cause. A pilot was shown to one customer under an NDA last month.

**Expected intake behavior:**
- identify the closed-loop defect → tool-state correlation → bounded parameter adjustment as the candidate core mechanism;
- treat "conventional systems require a human" as an inventor assertion until searched;
- ask what correlation method and adjustment logic are essential;
- record the customer demonstration and NDA facts rather than calling it public or non-public categorically;
- produce a prior-art search handoff;
- assess detectability separately;
- do not say the invention is patentable.
