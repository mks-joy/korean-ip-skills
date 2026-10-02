# Anthropic `claude-for-legal` — Adaptation Decisions for Korean IP

Reviewed: 2026-10-02

Source repository: `anthropics/claude-for-legal` (Apache License 2.0)

## Executive decision

Do **not** install or import the source repository wholesale.

The six highest-value source skills all contain useful workflow design, but every one of them is embedded in assumptions about Anthropic's plugin architecture, US legal practice, in-house/private-practice roles, or US litigation/prosecution doctrine. The Korean IP project will therefore **adapt design patterns, not adopt source skills unchanged**.

| Source skill | Decision | Reuse level |
|---|---|---:|
| `ip-legal/matter-workspace` | ADAPT | High |
| `litigation-legal/claim-chart` | ADAPT | High |
| `corporate-legal/tabular-review` | ADAPT | High |
| `legal-builder-hub/skills-qa` | ADAPT | High |
| `ip-legal/fto-triage` | ADAPT HEAVILY | Medium-High |
| `ip-legal/invention-intake` | ADAPT HEAVILY | Medium-High |

No reviewed source skill is suitable for unchanged adoption.

---

## 1. `ip-legal/matter-workspace`

### Decision: ADAPT

### Keep

- one active matter at a time;
- explicit matter switch rather than ambient cross-client context;
- separate `matter.md`, `history.md`, `notes.md`, and outputs;
- archive rather than delete on close;
- cross-matter access off by default;
- matter-specific overrides;
- confidentiality level as matter metadata.

### Change

- do not assume Anthropic's `~/.claude/plugins/config/...` path as the canonical storage model;
- support agent-neutral matter identifiers so Claude, Codex, or another agent can use the same isolation concept;
- do not treat the skill repository itself as the place for live client matter files;
- separate *matter metadata required for context selection* from *substantive confidential documents* held in the firm's document system.

### Korean-source requirement

None for the isolation mechanism itself. Any legal confidentiality/privilege language should be separately sourced if later added.

---

## 2. `litigation-legal/claim-chart`

### Decision: ADAPT

### Keep

- parse the operative claim into discrete limitations;
- map every limitation separately;
- exact source/evidence location for each mapping;
- explicit states rather than blanks;
- a dedicated `needs-evidence` / gap list;
- claim construction uncertainty must remain visible;
- "missing evidence" must not be silently filled;
- output should make human verification auditable;
- spreadsheet/CSV formula-injection neutralization is a useful implementation safeguard.

### Change

- remove US civil-litigation branches, jury-instruction logic, discovery/MSJ framing, Rule 11 framing, and §112(f)-specific assumptions from the generic Korean patent chart;
- do not copy US doctrine-of-equivalents rules into Korean analysis;
- define Korean claim interpretation, equivalents, indirect infringement, and validity treatment only after Korean-source review;
- preserve the chart as a factual/technical mapping chassis even when legal characterization is unresolved.

### Korean-source requirement

Before a Korean infringement/FTO skill moves beyond technical mapping, separately verify:
- Korean claim interpretation framework;
- doctrine of equivalents;
- indirect/joint infringement issues where applicable;
- enforceability/status rules relevant to the use case.

---

## 3. `corporate-legal/tabular-review`

### Decision: ADAPT

### Keep

- typed schema before running a large batch;
- 3–5 document sample before fan-out;
- one row per document/patent and stable columns;
- each interpreted value paired with exact source text and location;
- explicit `not_present`, `unclear`, and `needs_review` states;
- normalization pass after parallel extraction;
- spot-check exact quotations against the source;
- a human-verification field.

This is highly reusable for:
- patent portfolio analysis;
- prior-art comparison;
- prosecution-history extraction;
- patent-family/status review;
- FTO candidate triage.

### Change

- remove M&A-specific column types and contract assumptions;
- define patent/IP schemas separately;
- do not attach privilege labels by default;
- do not require a spreadsheet output when the task is small.

### Korean-source requirement

None for the generic extraction chassis. Patent status/legal conclusions must use official or otherwise appropriate current sources.

---

## 4. `legal-builder-hub/skills-qa`

### Decision: ADAPT

### Keep

The following are directly useful for this project:

- audience and work-shape review;
- delegation threshold;
- minimum input requirements;
- version/ownership;
- uncertainty/confidence handling;
- characteristic failure modes;
- scope boundaries;
- escalation logic;
- trust surface;
- freshness;
- schema/structure;
- conflicts with already-installed skills;
- prompt-injection heuristics;
- human approval for security-surface changes.

### Change

- replace Anthropic-specific installer paths and allowlist storage with repository-neutral policy;
- do not require every Korean IP skill to reproduce US concepts of attorney privilege;
- add Korean-IP-specific checks:
  - Korean/foreign law separation;
  - official-source preference;
  - legal-rule verification date;
  - patent/application/status identifier integrity;
  - no unsupported patentability, registrability, infringement, or validity conclusion.

### Korean-source requirement

The auditor itself needs no Korean legal doctrine beyond checking that a substantive skill declares and verifies its sources.

---

## 5. `ip-legal/fto-triage`

### Decision: ADAPT HEAVILY

### Keep

- ask what is made/used/sold/imported and in which jurisdictions;
- require technical detail rather than marketing description;
- report exactly what patent databases/sources were searched;
- select plausible candidates before deep claim mapping;
- chart each independent claim element-by-element;
- distinguish missing product evidence from a negative mapping;
- list open questions such as status, prosecution history, post-grant history, and licensing;
- never equate "nothing found in this search" with freedom to operate.

### Remove or replace

Do not import:
- 35 U.S.C. §271 framing;
- US willfulness/enhanced-damages language;
- US-specific claim-construction and equivalents rules;
- USPTO-specific maintenance/status assumptions as a Korean default;
- a fixed list of US litigation/NPE signals.

The source skill's warning language is intentionally US-centric and at points over-compressed. Korean FTO must be rebuilt from Korean infringement/status sources and target-jurisdiction rules.

### Korean-source requirement

A substantive Korean FTO skill needs independent source review for:
- acts constituting infringement under Korean patent law;
- claim interpretation and equivalents;
- indirect infringement;
- patent term/status;
- relevant defenses/exceptions;
- procedural posture when validity is disputed.

Until that review exists, the public Korean skill should remain a **technical claim-mapping / FTO triage** tool rather than a formal FTO opinion workflow.

---

## 6. `ip-legal/invention-intake`

### Decision: ADAPT HEAVILY

### Keep

- batch intake rather than serial questioning;
- technical problem → mechanism → difference from prior approaches;
- inventor and disclosure-date capture;
- prior-art search as a separate downstream step;
- detectability as a patent-vs-trade-secret consideration;
- strategic value as a separate business screen;
- do not say "patentable" from intake alone.

### Remove or replace

Do not import:
- US §101 / Alice-Mayo screening;
- US §102/§103 labels as if they were Korean law;
- US-only public-disclosure/bar framing;
- US prosecution-role assumptions.

### Korean replacement

The Korean intake should use:
- Patent Act Article 2 definition of invention as a background eligibility gate;
- Patent Act Article 29 for industrial applicability, novelty, and inventive step;
- Patent Act Article 30 for the Korean exception concerning certain disclosures, while warning that procedural requirements must be checked;
- Patent Act Article 36 as a reason to surface filing urgency for competing identical inventions;
- the current Patent/Utility Model Examination Guidelines;
- technology-field examination practice guides where the invention is AI, IoT, biotech, semiconductor, etc.

The intake should **not** decide the legal result. It should identify what facts and searches are required before a Korean patent professional decides.

---

## Shared design patterns approved for reuse

These patterns are approved for incorporation into Korean IP skills:

1. explicit state instead of blank/implicit certainty;
2. exact evidence + location paired with every interpreted value;
3. sample-before-scale for batch review;
4. matter isolation;
5. source scope disclosure;
6. gap lists as a primary output;
7. human-review gates for consequential legal action;
8. freshness metadata for legal-rule-bearing references;
9. no silent supplementation;
10. post-change diff verification.

## Patterns rejected as defaults

Do not use as generic defaults:

- US statutes/cases embedded into Korean workflows;
- blanket US privilege/work-product headers;
- US role distinctions as the universal user model;
- legal conclusions generated from incomplete source access;
- "green/yellow/red" verdicts that may be mistaken for legal opinions unless the state semantics are carefully defined.

## License / attribution note

The source repository is Apache-2.0 licensed. This project currently reuses workflow ideas and independently rewrites the implementation for Korean IP practice rather than copying the source skills wholesale.

If future contributions copy or adapt substantial source text, preserve the required Apache-2.0 notices and record the source path/commit in the relevant file or attribution record.
