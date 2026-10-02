# Anthropic `claude-for-legal` — Initial ABC IP LAW Triage

Source: `anthropics/claude-for-legal`

This file is an index of ideas worth inspecting. It is not an import of Anthropic's skills.

## Repository scale observed

The repository contains 151 `SKILL.md` files across legal, clinic, student, corporate, employment, privacy, product, regulatory, litigation, AI-governance, and IP areas.

For Korean IP practice, wholesale installation would introduce large amounts of irrelevant US/in-house/legal-domain behavior. We therefore use a **whitelist-and-adapt** approach.

## Priority review list

| Source skill | Relevance | What to study | What not to import blindly |
|---|---:|---|---|
| ip-legal/matter-workspace | High | matter isolation, active-matter state, archive model | US/private-practice assumptions |
| litigation-legal/claim-chart | High | element decomposition, evidence states, gap detection, pin cites | US civil-litigation rules |
| corporate-legal/tabular-review | High | batch review, one-row-per-document, cell-level provenance | M&A-specific schema |
| legal-builder-hub/skills-qa | High | trust surface, prompt-injection heuristics, freshness/conflict review | Anthropic-specific install assumptions |
| ip-legal/fto-triage | High | FTO intake, element mapping, unknown/open-question discipline | US infringement/willfulness framing |
| ip-legal/invention-intake | High | intake shape, detectability, strategic-value screen | §101/§102/§103 as Korean law |
| litigation-legal/chronology | Medium | source-grounded timelines | litigation-specific framing |
| litigation-legal/matter-briefing | Medium | matter status synthesis | GC/outside-counsel assumptions |
| legal-clinic/client-comms-log | Medium | append-only communications log | clinic supervision model |
| legal-clinic/deadlines | Medium | deadline status model | clinic deadline rules |
| commercial-legal/stakeholder-summary | Medium | professional analysis → client-readable summary | contract-signing framing |
| commercial-legal/amendment-history | Medium | version/change tracing | contract-specific fields |

## Adaptation rule

We adopt **design patterns**, not foreign legal conclusions.

Any Korean-IP skill built from these patterns must be independently rewritten and verified against Korean practice and relevant official sources.
