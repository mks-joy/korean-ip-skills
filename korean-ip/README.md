# Korean IP Practice Plugin

This directory contains the installable Claude Code plugin.

## Design principles

1. **No silent supplementation.** Missing evidence remains missing.
2. **Scope control.** Change only what the user asked to change.
3. **Source visibility.** Material legal/factual propositions should be traceable.
4. **Jurisdiction awareness.** Korean-law workflows must not silently import US/EU rules.
5. **Freshness awareness.** Deadlines, fees, examination standards, and official classifications must be verified when current accuracy matters.
6. **Human judgment stays human.** Consequential filing, assertion, abandonment, waiver, or rights-loss decisions require professional review.
7. **Matter isolation.** A skill must not borrow facts from another client or matter unless explicitly authorized.

## Current skills

- `change-control` — reviewed
- `source-verification` — reviewed
- `skill-auditor` — draft
- `invention-intake` — draft (official Korean source register added; test/review still pending)
- `oa-analysis` — draft (Article 42/47/62/63 source register added; behavior review pending)
- `fto-claim-chart` — draft (Articles 88/94/97/127 source register added; Korean equivalents/case-law module still intentionally deferred)
- `claim-strategy` — draft (Article 42/45/47 + Enforcement Decree 5/6 framework; behavior review pending)
- `claim-drafting` — draft (support/dependency/terminology gates; behavior review pending)
- `specification-drafting` — draft (enablement/support/fallback-preservation workflow; behavior review pending)

Substantive Korean patent/trademark workflows move to reviewed status only after source and behavior review.


## Patent drafting pipeline

See `PATENT-DRAFTING-WORKFLOW.md` for the handoff contract between claim strategy, claim drafting, and specification drafting.
