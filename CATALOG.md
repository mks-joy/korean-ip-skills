# Skill Catalog

This file is the public roadmap and review register.

## Review states

- **Planned** — concept only; not usable.
- **Draft** — implementation exists but has not passed review.
- **Reviewed** — passed source, scope, and workflow review.
- **Deprecated** — retained for history; do not use.

## Initial roadmap

| Skill | Area | Status | Intended use |
|---|---|---:|---|
| change-control | Core | Reviewed | Prevent an agent from changing anything outside the requested scope and require a post-change diff check |
| source-verification | Core | Reviewed | Prevent unsupported factual/legal supplementation and require provenance labeling |
| skill-auditor | Core | Draft | Review third-party or newly authored skills for trust surface, scope, freshness, conflicts, and hidden instructions |
| invention-intake | Patent | Draft | Structured Korean patent invention intake, disclosure/timing triage, candidate-concept separation, detectability, and prior-art-search handoff |
| prior-art-analysis | Patent | Planned | Source-grounded prior-art comparison and novelty/inventive-step issue spotting |
| claim-strategy | Patent | Planned | Identify protection targets and claim architecture before drafting |
| claim-drafting | Patent | Planned | Korean patent claim drafting with dependency/support consistency checks |
| specification-drafting | Patent | Planned | Specification drafting workflow with support and terminology checks |
| oa-analysis | Patent | Draft | Decompose Korean OA grounds by claim, map cited references, separate Article 42 issues, and verify amendment basis before response drafting |
| oa-response | Patent | Planned | Draft amendment/argument options with specification-basis verification |
| fto-claim-chart | Patent | Planned | Element-by-element FTO mapping with status and evidence tracking |
| trademark-clearance | Trademark | Planned | Korean trademark first-pass conflict analysis |
| designated-goods | Trademark | Planned | KIPO designated-goods workflow using verified official names |

## Publication rule

A legal-rule-bearing skill cannot move to **Reviewed** unless its material rules identify:
1. jurisdiction;
2. source or source class;
3. last-verified date where freshness matters;
4. any professional-review gate.

No skill may silently convert missing evidence into a positive finding.
