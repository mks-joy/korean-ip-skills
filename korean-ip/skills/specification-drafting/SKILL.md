---
name: specification-drafting
description: >
  Draft or expand a Korean patent specification from invention materials and a
  supported claim set. Use to create an enabling description, support every
  planned claim/fallback limitation, describe relationships/operation/
  alternatives, and audit terminology and claim-spec consistency. The skill
  must not fabricate technical facts to make the disclosure look complete.
last_verified: 2026-10-02
freshness_window: 6 months
freshness_category: regulatory
verified_against:
  - https://www.law.go.kr/lsLawLinkInfo.do?chrClsCd=010202&lsJoLnkSeq=1000690127
  - https://www.law.go.kr/lsLawLinkInfo.do?chrClsCd=010202&lsJoLnkSeq=1000690062
  - https://law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030489313
  - https://kipo.go.kr/ko/kpoContentView.do?menuCd=SCD0200146
---

# Korean Patent Specification Drafting

**Status: DRAFT**

## Purpose

Build a specification that:
- explains the invention so a person having ordinary skill in the art can practice it;
- supports the claims;
- preserves disclosed fallback positions;
- uses consistent terminology;
- makes the source/unknown boundary visible.

This is a drafting workflow, not permission to fill technical gaps with plausible inventions.

## Source register

Read:
`../../references/korean-patent-drafting-sources.md`

Patent Act Article 42(3) and (4), Article 47(2), and the current examination guidelines are the core legal anchors.

## Inputs

Prefer:
- invention-intake output;
- source technical documents;
- drawings/diagrams;
- claim-strategy output;
- current draft claims;
- inventor clarifications;
- prior-art notes if available.

If a claimed limitation cannot be explained from these materials, flag it before drafting around it.

## Step 1 — Build the disclosure map

For each technical concept, label:
- **source fact**;
- **approved inference/derivation**;
- **illustrative drafting language** that does not add a new technical fact;
- **unknown / inventor confirmation required**.

Do not write an unknown implementation as a completed embodiment.

## Step 2 — Establish the description skeleton

Use a structure appropriate to the invention. A typical structure may include:

- title;
- technical field;
- background technology;
- problem / objective;
- solution concept;
- advantageous effects;
- brief description of drawings;
- detailed description / embodiments;
- variations / alternatives;
- industrial applicability where useful;
- reference signs where drawings are used.

This is a practical drafting structure, not a statement that every heading is always legally mandatory.

## Step 3 — Explain the independent-claim architecture

For every independent claim limitation, the description should make clear:
- what the element/step is;
- how it relates to other elements/steps;
- what it does in the disclosed mechanism;
- any sequence/condition that matters;
- enough implementation detail to avoid a purely aspirational description.

Do not simply paste the claims into the description and call that support.

## Step 4 — Support the dependent/fallback layers

For every dependent or planned fallback limitation:
- describe the feature;
- describe how it combines with the parent architecture;
- identify alternatives where actually disclosed;
- state technical effect/rationale where supported;
- avoid presenting an optional feature as universally required.

Create:

| Fallback feature | Description location | Drawings | Alternative disclosed? | State |
|---|---|---|---|---|

Because later amendment is constrained by the original disclosure, missing useful fallback support should be surfaced before filing.

## Step 5 — Expand alternatives without hallucinating

Good expansion:
- disclosed material A may be replaced by disclosed material B;
- disclosed ordering may be reversed if the source says both are possible;
- optional module may be omitted where the source supports omission.

Bad expansion:
- inventing a sensor, algorithm, material, range, protocol, equation, or control step because it seems technically plausible.

If an alternative would be useful but is not disclosed:
`INVENTOR CONFIRMATION NEEDED — do not add as fact.`

## Step 6 — Drawings and reference consistency

Where drawings exist:
- every referenced component should map consistently between text and figure;
- no reference sign should silently change meaning;
- claimed relationships should be explainable from the figures or text where appropriate;
- figure descriptions should not introduce unsupported functionality.

If a drawing is needed to explain a spatial/sequence relationship and none is supplied, flag it.

## Step 7 — Enablement/detail review

Ask whether the current draft gives a skilled person enough information to practice the invention.

Flag:
- black-box component whose internal operation is necessary to the invention but unexplained;
- parameter/range with no disclosed basis;
- algorithm described only by desired output;
- process transition with missing condition/input;
- chemical/biotech example requiring specialist detail;
- AI model/training/data treatment requiring technology-field review.

Do not solve an enablement gap by inventing details.

## Step 8 — Claim support review

For each claim limitation, identify one or more description locations that support it.

| Claim | Limitation | Description support | Figure/support | State |
|---|---|---|---|---|
| 1 | ... | para ... | Fig. ... | supported / partial / missing |

If a claim limitation has no meaningful description support, revise the claim or obtain more disclosure; do not hide the gap.

## Step 9 — Terminology consistency audit

Check:
- one concept is not casually renamed;
- one term does not denote different components;
- generic/specific relationships are intentional;
- claim term and description term correspond;
- abbreviations are introduced consistently;
- direction/position/time relationships are stable;
- singular/plural references do not create ambiguity.

Produce a terminology-change list rather than silently normalizing terms.

## Step 10 — Final support-preservation audit

Before completion:
- confirm all current claim limitations are supported;
- confirm useful disclosed fallback features remain described even if not currently claimed;
- confirm optional features are not unintentionally described as mandatory;
- confirm no unsupported feature was added during drafting;
- confirm drawings/text/claims use consistent terminology;
- list open inventor questions.

## Output

```markdown
# Specification Draft — [title]

[specification text]

---

## Claim-support matrix
[table]

## Fallback-support matrix
[table]

## Terminology audit
- ...

## Missing technical facts / inventor questions
- ...

## Drafting-source state
- Source facts:
- Approved derivations:
- Illustrative language:
- Unknowns:
```

## What this skill does not do

- It does not fabricate embodiments.
- It does not treat claim repetition as sufficient disclosure.
- It does not assume every optional feature belongs in every embodiment.
- It does not silently delete useful disclosed fallback positions.
- It does not make technology-specific enablement judgments without the needed source/practice review.
- It does not certify compliance merely because the document is long.

## Example

If a claim requires a controller to change parameter P based on historical sensor data, the specification should explain the data source, the relevant history concept, how the controller uses it at a meaningful level, and how P is changed to the extent disclosed. If the source does not reveal the actual decision rule, the draft must flag that gap rather than invent a formula.
