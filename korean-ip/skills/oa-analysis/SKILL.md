---
name: oa-analysis
description: >
  Analyze a Korean patent Office Action / notice of grounds for rejection by
  separating each rejection ground, mapping affected claims and cited references,
  checking specification/amendment basis, and producing response options with
  explicit evidence gaps. Use before drafting an amendment or opinion. This skill
  does not file a response or select the final legal strategy.
last_verified: 2026-10-02
freshness_window: 6 months
freshness_category: regulatory
verified_against:
  - https://www.law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030488735
  - https://law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030489313
  - https://law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1028030821
  - https://www.law.go.kr/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030488937
  - https://law.go.kr/lsLawLinkInfo.do?chrClsCd=010202&lsJoLnkSeq=1000689891
  - https://kipo.go.kr/ko/kpoContentView.do?menuCd=SCD0200146
---

# Korean Patent OA Analysis

**Status: DRAFT**

## Purpose

Convert a Korean patent Office Action / 거절이유통지 into an auditable issue map before response drafting.

The skill should answer:

1. What exactly is rejected?
2. Under which legal ground?
3. What did the examiner actually reason?
4. Which cited passages support that reasoning?
5. What does the current claim actually require?
6. What response paths exist?
7. If amendment is considered, where is the exact original basis?
8. What remains unknown or unverified?

It is an analysis workflow, not a filing action and not a substitute for the responsible patent professional's final strategy.

## Source register

Read:

`../../references/korean-patent-oa-sources.md`

If the freshness window has expired, or amendment permissibility / a live deadline depends on the current rule, verify the current official source.

## Required inputs

Prefer the complete matter package:

- notice of grounds for rejection / Office Action;
- application as filed (specification, claims, drawings);
- current operative claims;
- all amendments already filed;
- cited references in full;
- relevant prosecution history;
- response deadline and any extension history, if available.

### Minimum viable analysis

If one of these is missing, proceed only where safe and label the gap.

Examples:
- missing cited reference full text → do not conclude what the reference discloses from examiner paraphrase alone;
- missing originally filed specification → do not validate amendment basis;
- uncertain current claim set → do not analyze a superseded claim as operative;
- missing deadline data → do not compute or state a filing deadline.

## Step 0 — Matter/version lock

Before substantive analysis, identify and record:

- application number;
- invention title;
- filing/priority date if available;
- OA date;
- response deadline as stated in the notice or verified docket;
- current claim version;
- last amendment date/version;
- cited-reference identifiers;
- documents actually reviewed.

Use explicit source states:
- `verified`;
- `asserted`;
- `derived`;
- `unknown`.

If claim version is uncertain, stop claim-by-claim analysis until resolved.

## Step 1 — Parse the OA into discrete rejection units

Do not summarize the OA as one block.

Create one row per **ground × affected claim set**:

| ID | Claims | Legal basis | Examiner's stated reason | Cited reference(s) | OA location | State |
|---|---|---|---|---|---|---|

Examples of distinct units:
- Article 29 novelty rejection for Claims 1, 3;
- Article 29 inventive-step rejection for Claims 2–5;
- Article 42(4)(2) clarity rejection for Claim 6;
- Article 42(4)(1) support rejection for Claim 7;
- Article 47(2) new-matter issue caused by an earlier amendment.

Do not merge different legal grounds merely because they affect the same claim.

## Step 2 — Verify the legal frame

For each rejection unit:

- identify the statutory provision named in the OA;
- verify that the cited provision/current guideline is still current if the legal rule matters to the response;
- distinguish:
  - examiner's statement;
  - statutory/guideline rule;
  - your analysis.

Do not invent a legal basis the examiner did not raise unless explicitly labeled as a **separate risk spotted during review**.

## Step 3 — Analyze prior-art rejections claim-by-claim

For Article 29 prior-art issues, start from the **operative claim text**, not the examiner's paraphrase.

### 3A. Decompose claim limitations

Create a stable limitation list for each independent claim and any dependent limitation that matters.

### 3B. Map cited references

For each limitation:

| Limitation | Reference disclosure | Exact passage / figure | Examiner mapping | Analyst state |
|---|---|---|---|---|
| [claim text] | [what the ref actually discloses] | [pin cite] | [examiner's position] | mapped / partial / not-found / unclear / needs-source |

Rules:
- quote or identify the exact cited location;
- if the full reference is unavailable, use `needs-source`;
- do not reconstruct a missing passage from the examiner's summary;
- do not call a limitation "not disclosed" unless the searched scope justifies that statement.

### 3C. Novelty

For a novelty rejection:
- test whether one cited reference is asserted to disclose every limitation of the rejected claim;
- identify the first limitation(s) where the mapping is incomplete, disputed, or construction-dependent;
- separate an actual missing limitation from a disagreement about claim interpretation.

Do not conclude "novel" merely because one cited passage is weak.

### 3D. Inventive step

For an inventive-step rejection:
- identify the primary/secondary references and the examiner's combination rationale;
- state which limitation comes from which reference;
- identify whether the response issue is:
  - missing feature;
  - disputed motivation/combination;
  - technical incompatibility;
  - different problem/technical effect;
  - hindsight risk;
  - claim interpretation;
  - factual gap requiring more evidence.

Do not merely say "references cannot be combined." State the factual/technical reason that must be evaluated.

## Step 4 — Analyze Article 42 / claim-language issues separately

Do not force clarity/support/enablement issues into a prior-art chart.

For each issue, record:

| Claim / spec location | Examiner issue | Exact wording | Relevant description support | Analyst diagnosis | Needed action |
|---|---|---|---|---|---|

Separate:
- **claim wording defect** — ambiguity, antecedent/relationship issue, unclear boundary;
- **support issue** — claim scope not sufficiently supported by the description;
- **enablement/detail issue** — description may not enable the skilled person to practice the invention as required;
- **terminology mismatch** — same concept described inconsistently;
- **fact unknown** — cannot decide from the available record.

Do not "fix" claim wording by silently changing technical meaning.

## Step 5 — Generate response paths, not a single answer

For each rejection unit, produce 1–3 possible paths where genuinely available:

- **Argument only**
- **Amendment + argument**
- **Narrow to a supported dependent feature**
- **Clarify terminology without intended substantive narrowing**
- **Obtain inventor/technical evidence before choosing**
- **Further prior-art/prosecution-history review**

For each path show:
- what it addresses;
- what it gives up or narrows;
- evidence/source required;
- unresolved risk.

Do not rank a final legal strategy unless the user explicitly asks for a recommendation and sufficient facts are present.

## Step 6 — Amendment-basis gate

Any proposed amendment must pass this gate before being presented as usable.

Create:

| Proposed amendment | Exact original basis | Location | Basis state | New issue created? |
|---|---|---|---|---|
| [text/concept] | [verbatim or precise disclosed concept] | [para/claim/fig] | verified / partial / basis_not_verified | [clarity/support/etc.] |

Rules:
- Article 47(2) basis is a **hard gate**;
- do not manufacture support from general technical knowledge;
- do not rely only on a later amendment as original basis;
- if the originally filed record is unavailable, mark `basis_not_verified`;
- if several passages must be combined, say so and flag whether the combination itself needs professional review.

### Stage-sensitive amendment scope

Before treating an amendment as procedurally available:
- identify whether this is an initial/non-final notice, a notice caused by an earlier amendment, a reexamination context, or another stage;
- verify the applicable Article 47 limits.

Do not apply later-stage amendment restrictions automatically to every OA.

## Step 7 — Cross-check amendment consequences

After drafting an amendment candidate, re-test:

- every amended claim term for clarity;
- description support;
- dependency/antecedent basis;
- consistency across claims;
- whether a new rejection risk is created;
- whether the amendment actually distinguishes the cited mapping;
- whether narrowing removes commercially important coverage.

A response that cures Article 29 but creates Article 42 or Article 47 risk is not ready.

## Step 8 — Output

```markdown
# OA Analysis — [application / title]

## Executive issue map
- OA date:
- Response deadline:
- Current claims verified:
- Main rejection units:
- Critical missing sources:

## 1. Rejection-unit table
[table]

## 2. Prior-art mapping
[claim charts]

## 3. Article 42 / formal-substantive drafting issues
[issue tables]

## 4. Response paths
### Rejection R1
Option A — Argument only
- Basis:
- Strength / gap:
- Required verification:

Option B — Amendment + argument
- Amendment concept:
- Original basis:
- Scope cost:
- New risks:

## 5. Amendment-basis matrix
[table]

## 6. Open questions / evidence gaps
- ...

## 7. Recommended work sequence
- verify source X;
- ask inventor Y;
- compare passage Z;
- draft response only after basis gate passes.

## Source state
- Verified:
- Asserted:
- Derived:
- Unknown:
```

If a legal rule is invoked, identify the provision/source and note the source-register verification date.

## Escalation rules

Stop or mark unresolved when:
- current claims are not verified;
- a cited reference is missing;
- the examiner relies on a passage that cannot be located;
- amendment basis cannot be found in the originally filed record;
- the proposed amendment depends on an unstated technical fact;
- prosecution stage is unclear and amendment scope depends on it;
- a deadline is not verified;
- the issue depends on a technology-specific examination rule not yet checked.

## What this skill does not do

- It does not file an opinion or amendment.
- It does not choose the final legal strategy automatically.
- It does not fabricate amendment basis.
- It does not treat examiner paraphrase as substitute for the cited reference.
- It does not assume a missing limitation is absent from the entire reference unless the search/review scope supports that statement.
- It does not reuse facts from another matter.
- It does not calculate an unverified legal deadline.

## Example

**Synthetic OA:** Claim 1 requires A + B + C. The examiner cites Reference 1 for A + B and says paragraph 45 discloses C. The supplied copy of Reference 1 ends at paragraph 30. The examiner also objects that "control data" in Claim 4 is unclear. A proposed amendment would replace "control data" with "temperature-correction command generated from sensor history."

**Required behavior:**
- Claim 1 / Article 29 becomes one rejection unit;
- limitation C is `needs-source`, not mapped or not-found;
- Claim 4 clarity is analyzed separately from the prior-art issue;
- the replacement wording cannot be proposed as usable until exact original specification basis is found;
- no final response strategy is selected from the incomplete record.
