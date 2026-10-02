---
name: fto-claim-chart
description: >
  Build an element-by-element Korean patent claim chart for FTO or infringement
  first-pass analysis. Decompose the operative claim, map each limitation to
  product/process evidence, preserve construction/evidence gaps, and separate
  literal technical mapping from equivalents or other legal issues. This skill
  does not conclude that a product is free to operate or that infringement exists.
last_verified: 2026-10-02
freshness_window: 6 months
freshness_category: regulatory
verified_against:
  - https://www.law.go.kr/lsSc.do
  - https://www.law.go.kr/lsLinkCommonInfo.do?lsJoLnkSeq=1030488089
  - https://law.go.kr/LSW/lsSideInfoP.do?docCls=jo&joBrNo=00&joNo=0094&lsiSeq=279827&urlMode=lsScJoRltInfoR
  - https://www.law.go.kr/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030175301
  - https://www.law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1025176577
---

# Korean Patent FTO Claim Chart

**Status: DRAFT**

## Purpose

Provide an auditable **claim-first technical/legal issue map** for:
- FTO triage;
- infringement first-pass review;
- design-around discussion;
- evidence-gap identification.

The chart is not a formal FTO opinion, non-infringement opinion, infringement opinion, or validity opinion.

## Source register

Read:

`../../references/korean-patent-fto-sources.md`

Do not add an unverified Korean infringement doctrine from memory.

## Required inputs

For a useful chart, obtain:

### Patent side
- patent/publication number and jurisdiction;
- exact claim version to analyze;
- current legal/status information if available;
- specification and drawings;
- prosecution/correction/invalidity materials where claim scope may have changed.

### Target side
- accused/target product or process description;
- technical drawings/specifications;
- manuals, source code, teardown/test evidence, process descriptions, or other reliable evidence;
- which acts and jurisdictions are relevant to the business activity.

If the target feature is described only by marketing language, ask for technical detail.

## Step 0 — Lock patent identity and operative claim

Record:

- patent/application/publication number;
- jurisdiction;
- owner/assignee if verified;
- priority/filing/grant dates if verified;
- status source/date;
- operative claim number and claim text;
- whether the claim changed through amendment/correction/post-grant proceeding.

Use:
- `verified`;
- `asserted`;
- `derived`;
- `unknown`.

If the operative claim text is not verified, do not build a definitive chart.

## Step 1 — Define the activity being assessed

FTO is jurisdiction- and activity-specific.

Capture separately:
- where the product is made;
- where it is used;
- where it is sold/offered;
- where it is imported/exported;
- whether the target is a product, method, software/service flow, manufacturing process, or component.

Do not silently assume Korean law governs acts outside Korea.

## Step 2 — Parse the claim

Decompose the exact operative claim into limitations without rewriting away legal/technical meaning.

Rules:
- preserve claim wording;
- keep nested relationships and dependencies visible;
- separate structural elements from functional/relational limitations where useful;
- identify terms that may require construction;
- do not resolve claim construction silently.

Create a claim parse:

| ID | Claim text (verbatim) | Type | Construction issue? |
|---|---|---|---|
| 1a | ... | structure / step / relation / function | ... |

## Step 3 — Map each limitation to target evidence

Use this chart:

| ID | Claim limitation | Target feature/process | Evidence + exact location | Mapping | State | Verified |
|---|---|---|---|---|---|---|
| 1a | [verbatim] | [feature] | [source/pin cite] | literal candidate / construction-dependent / no current mapping | mapped / partial / not-found / needs-evidence / unclear | ☐ |

### State semantics

- **mapped** — supplied evidence supports a literal technical mapping under the stated construction;
- **partial** — only part of the limitation is supported;
- **not-found** — the reviewed target evidence does not show the limitation; this is not a claim that the feature does not exist elsewhere;
- **needs-evidence** — potentially relevant feature exists but the necessary evidence is unavailable;
- **unclear** — evidence or wording is ambiguous;
- **construction-dependent** — result changes depending on claim interpretation.

A blank cell is not allowed.

## Step 4 — Evidence discipline

For every positive mapping:
- identify the source;
- identify page/section/figure/code line or other precise location where available;
- distinguish product fact from analyst inference.

Do not:
- infer an internal feature merely because the product achieves the claimed result;
- reconstruct hidden process steps from marketing output;
- map a claim element from a competitor's different product/version without saying so;
- treat a patent drawing as proof of the target product.

If the evidence is not there, use `needs-evidence`.

## Step 5 — Literal mapping first

Run a literal mapping pass before any equivalents discussion.

For each claim, summarize:
- all limitations with evidence-backed mappings;
- limitations that are partial/unknown;
- construction-dependent terms;
- evidence that would resolve the open point.

Do not collapse "all mapped under one assumed construction" into a final infringement conclusion.

## Step 6 — Equivalents and other legal issues are a separate lane

Do not use US doctrine-of-equivalents formulations as Korean law.

For a limitation that is not literally mapped, record:

`Equivalents review may be relevant — Korean doctrine/case-law review required.`

Do not decide equivalence until a dedicated, current Korean-law source module is available or the user supplies/requests the relevant authority review.

Likewise, flag separately where relevant:
- indirect infringement / Article 127;
- divided/multi-actor performance;
- process visibility;
- patent exhaustion;
- experimental use/other statutory exceptions;
- license/consent;
- validity;
- prior-use rights.

A flag is not a conclusion.

## Step 7 — Status/enforceability check

Before an FTO result is treated as material:

- verify whether the patent is granted and in force;
- verify the operative claims;
- check expiration/lapse/term extension or adjustment as relevant;
- check correction/invalidity/post-grant events if they affect the claim;
- identify family members only as separate rights, not as substitutes for the Korean claim.

If status cannot be verified:
`STATUS NOT VERIFIED — do not rely on enforceability conclusion.`

Do not calculate status solely from a 20-year formula.

## Step 8 — FTO triage output

### Patent-level summary

Use neutral states:

- **FULL LITERAL MAPPING CANDIDATE** — every limitation has an evidence-backed mapping under the stated assumptions/construction; legal review required.
- **OPEN MAPPING** — one or more limitations are partial, unclear, construction-dependent, or need evidence.
- **NO CURRENT MAPPING ON IDENTIFIED LIMITATION(S)** — the reviewed evidence does not currently show one or more required limitations; scope/equivalents/status review may still matter.
- **INSUFFICIENT SOURCE SET** — cannot responsibly chart the claim.

Do not use:
- "clear";
- "safe to launch";
- "does not infringe";
- "infringes";
unless the user is explicitly asking for a professional legal analysis and adequate legal/evidentiary work has been done outside this triage skill.

### Design-around view

For each open/missing limitation:
- identify what technical feature creates the mapping risk;
- identify whether removing/changing it appears technically possible from the supplied product facts;
- state what new product constraint the change would create.

Do not instruct the user to rely on a design-around until the revised design is re-charted.

## Step 9 — Output format

```markdown
# Patent Claim Chart / FTO Triage

## Scope
- Patent:
- Jurisdiction:
- Claim:
- Target:
- Activities/jurisdictions:
- Evidence reviewed:
- Patent status source/date:

## Claim parse
[table]

## Element mapping
[table]

## Construction questions
- ...

## Needs-evidence list
- ...

## Separate legal flags
- equivalents:
- indirect infringement:
- exceptions/defenses:
- validity:
- license/status:

## Triage state
[FULL LITERAL MAPPING CANDIDATE / OPEN MAPPING / NO CURRENT MAPPING ON IDENTIFIED LIMITATION(S) / INSUFFICIENT SOURCE SET]

## Design-around questions
- ...

## Source state
- Verified:
- Asserted:
- Derived:
- Unknown:
```

## What this skill does not do

- It does not perform a comprehensive patent search.
- It does not conclude freedom to operate.
- It does not decide infringement/non-infringement.
- It does not decide equivalents from US doctrine.
- It does not decide validity.
- It does not silently assume a patent is in force.
- It does not treat a family member's claim as the Korean claim.
- It does not fill hidden product/process facts from model knowledge.

## Example

**Synthetic claim:** A system comprising A, B connected to A, and C configured to generate a correction signal from a history of B.

**Target evidence:** manual shows A and B; a block diagram shows C outputs a correction signal but does not reveal whether history of B is used.

**Required behavior:**
- A and B may be mapped if exact evidence supports them;
- C's output function may be partial;
- "from a history of B" is `needs-evidence`;
- the claim is `OPEN MAPPING`, not "non-infringing";
- no internal algorithm is invented from the observed output.
