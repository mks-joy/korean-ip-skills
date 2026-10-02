---
name: source-verification
description: >
  Keep legal, patent, technical, and factual analysis grounded in identifiable
  sources. Use when reviewing source documents, patents, prior art, official
  records, legal rules, or evidence where unsupported supplementation would be risky.
---

# Source Verification

## Goal

Never turn an inference, memory, missing field, or model guess into a sourced fact.

## Source states

For each material proposition, track one of:
- **verified** — directly supported by an identified source;
- **derived** — computed or logically derived from verified facts; show the basis;
- **asserted** — supplied by the user or another party but not independently verified;
- **inferred** — analytical inference; label it;
- **unknown** — evidence is missing or insufficient.

## Rules

1. Do not fabricate patent numbers, dates, citations, claim language, prosecution history, legal provisions, fees, deadlines, classifications, or product features.
2. Do not silently fill missing facts from general model knowledge.
3. If a source is unavailable, say what could not be verified.
4. Distinguish the text of a claim/reference from the analysis of that text.
5. When comparing documents, cite or identify the exact source for each mapped proposition.
6. Current legal/administrative facts that can change require freshness checking before reliance.
7. Conflicting sources remain conflicting until resolved; do not pick one silently.
8. "Not found" means not found in the searched scope, not that the fact does not exist.

## Legal/IP-specific checks

When relevant, verify separately:
- jurisdiction;
- application/publication/registration number;
- priority, filing, publication, grant, and expiration/status dates;
- operative claim version;
- family/member relationship;
- official status and fee/deadline source;
- exact cited passage or evidence location.

## Output discipline

Where a conclusion matters, include the strongest supporting source and the principal unresolved gap. If the gap could change the conclusion, say so explicitly.
