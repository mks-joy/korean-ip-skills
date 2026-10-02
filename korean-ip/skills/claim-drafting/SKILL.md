---
name: claim-drafting
description: >
  Draft Korean patent claims from a supported claim strategy and invention
  disclosure. Use to draft independent and dependent claims, build a claim set,
  verify dependency form, maintain a limitation-to-source support matrix, and
  audit terminology/support/clarity. This skill must not invent undisclosed
  technical features or conclude patentability.
last_verified: 2026-10-02
freshness_window: 6 months
freshness_category: regulatory
verified_against:
  - https://www.law.go.kr/lsLawLinkInfo.do?chrClsCd=010202&lsJoLnkSeq=1000690062
  - https://law.go.kr/lsLinkCommonInfo.do?chrClsCd=010202&lspttninfSeq=121414
  - https://law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lspttninfSeq=121419
  - https://kipo.go.kr/ko/kpoContentView.do?menuCd=SCD0200146
---

# Korean Patent Claim Drafting

**Status: DRAFT**

## Purpose

Turn a supported claim strategy into auditable Korean claim language.

The drafting sequence is:
1. verify inputs;
2. draft independent claim(s);
3. draft dependent claims as meaningful additional limitations/features;
4. create additional claim categories only where technically justified;
5. validate legal form, support, terminology, and dependency.

## Source register

Read:
`../../references/korean-patent-drafting-sources.md`

## Minimum inputs

Prefer:
- invention disclosure / technical materials;
- claim-strategy output;
- prior-art results if available;
- drawings/architecture;
- terminology list if one exists.

If the user asks for claims directly without a claim strategy, create a lightweight strategy first rather than silently choosing the protection target.

## Step 1 — Source and terminology lock

Build:
- approved source documents;
- known prior art reviewed;
- glossary of core terms;
- feature-to-source map.

For every drafted limitation, require one of:
- `supported`;
- `derived — review`;
- `unsupported — do not claim`.

Do not transform common technical knowledge into a source basis.

## Step 2 — Draft the independent claim first

For each independent claim:

1. identify the claim subject;
2. state the components/steps necessary to capture the chosen inventive architecture;
3. state the relationships or processing logic that give those elements technical meaning;
4. avoid adding an embodiment-specific feature merely because it is easy to write;
5. avoid result-only language where the disclosure does not teach the technical means;
6. preserve enough technical boundary for clarity and support.

After drafting, create:

| Limitation | Source basis | Why included | Scope concern | Clarity concern |
|---|---|---|---|---|

Do not proceed to dependent claims until unsupported independent limitations are resolved or removed.

## Step 3 — Draft dependent claims

A dependent claim should add a **meaningful fallback position** by limiting or adding features.

Useful dependent-claim categories may include:
- additional component;
- further relationship;
- narrower process/control condition;
- parameter/range;
- alternative implementation;
- feature tied to a technical effect;
- specific embodiment with strategic value.

Avoid dependent claims that merely:
- restate the parent;
- add marketing language;
- add an immaterial adjective;
- introduce an unsupported implementation;
- narrow scope without a reason.

For each dependent claim, record:
- parent claim;
- added limitation;
- exact support;
- fallback purpose.

## Step 4 — Apply Korean dependency-form rules

Check Enforcement Decree Article 5 mechanically:

- at least one independent claim exists;
- dependent claims properly refer to an earlier claim;
- referenced claim numbers are stated;
- multiple references are alternative, not cumulative unless rewritten as a permitted structure;
- no prohibited multiple-dependent-to-multiple-dependent structure;
- referenced claims appear before referring claims;
- claims are sequentially numbered.

Do not rely on natural-language appearance alone; inspect the dependency tree.

## Step 5 — Additional claim subjects / set generation

Where technically meaningful, consider another independent category such as method or system.

For each additional independent claim:
- map it back to the same core inventive concept;
- identify who/what practices it;
- confirm description support;
- check whether the claim set raises a unity concern.

Do not mechanically convert nouns to verbs to create a method claim or duplicate the same claim with cosmetic wording.

## Step 6 — Clarity and consistency audit

Check every claim for:

### Terminology
- same concept uses a stable term;
- same term is not used for different concepts;
- deliberate generic/specific hierarchy is distinguishable.

### Reference/relationship
- each introduced component/step has a clear relationship where needed;
- antecedent/reference language is coherent;
- dependent additions actually depend on the parent scope.

### Functional language
- the function has disclosed technical means/context;
- the function does not hide an unsupported desired result.

### Boundary
- avoid undefined relative expressions where they make scope materially uncertain;
- if a relative/functional term is intentional, flag whether the description must define or illustrate it.

## Step 7 — Claim-to-description support matrix

Before completion:

| Claim | Limitation | Source location | Description support needed | State |
|---|---|---|---|---|
| 1 | ... | ... | ... | supported / needs-description / unsupported |

A claim can be syntactically good and still fail the support workflow.

## Step 8 — Output

```markdown
# Draft Claims — [title]

## Claims
【Claim 1】
...

【Claim 2】
...

## Dependency tree
...

## Support matrix
[table]

## Terminology audit
- ...

## Scope / clarity issues
- ...

## Missing disclosure
- ...
```

## Completion gate

Do not mark the claim set ready for specification drafting if:
- any independent limitation is unsupported;
- dependency form is invalid;
- claim terminology has unresolved material ambiguity;
- a claimed relationship cannot be explained from the source material;
- the claim set appears to contain unrelated invention concepts without review.

## What this skill does not do

- It does not conclude the claims are novel, inventive, valid, or enforceable.
- It does not invent technical details.
- It does not add a limitation solely because it "sounds patent-like."
- It does not mechanically generate every possible claim category.
- It does not delete disclosed alternatives merely because they are not in the current claims.
- It does not treat claim count optimization as more important than preserving a coherent fallback strategy.

## Example

If Claim 1 recites A, B, and a relationship R between them, a useful dependent claim might add a disclosed control condition C that narrows R. A weak dependent claim merely says that A is "efficient" without a disclosed technical boundary.

The skill should draft C only if its support is traceable.
