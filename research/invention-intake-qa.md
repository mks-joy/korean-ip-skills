# QA Note — `invention-intake` v0.1 Draft

Reviewed: 2026-10-02

## Current result

**REVISE / keep as Draft**

The skill is suitable for repository testing but should not yet be presented as a fully reviewed Korean patent-practice skill.

## Strengths

- clear task boundary: intake before prior-art search/claim drafting;
- no patentability conclusion;
- batch intake with missing-fact handling;
- explicit source-fact / assertion / inference / unknown separation;
- public-disclosure urgency handled without assuming Article 30 automatically applies;
- foreign-jurisdiction rules kept separate;
- detectability and patent-vs-trade-secret discussion separated from patentability;
- multiple candidate invention concepts can be surfaced without a premature unity conclusion;
- official-source register and freshness metadata are present;
- no hooks, Bash, MCP wildcard, external action, or credential access;
- synthetic acceptance tests cover key failure modes.

## Remaining review items before `Reviewed`

1. **Behavior test in Claude Code.** Run the five synthetic cases and confirm the model obeys state separation and does not over-conclude.
2. **Technology-field branching.** Check AI/software and at least one physical/semiconductor example against the 2026 technology-field examination practice guide at a more detailed level.
3. **Article 30 procedure wording.** The skill intentionally avoids hard-coding all procedural details; confirm the wording still prompts enough urgency without implying the exception applies.
4. **Industrial applicability.** Decide whether a dedicated Article 29 industrial-applicability screen adds value or creates unnecessary doctrinal complexity at intake.
5. **Inventorship/ownership boundary.** Confirm the skill asks enough to identify an issue without drifting into a legal inventorship determination.
6. **Source display.** Confirm outputs that mention Article 30/36 visibly identify the legal source/verification date as instructed.

## Trust-surface check

- Hooks: none.
- Bash/code execution: none.
- MCP: none.
- Automatic sending/filing: none.
- Writes outside output scope: none declared.
- Credential access: none.
- Cross-matter access: none.
- Hidden instructions: none observed.

## Conflict check

- `source-verification`: complementary; no conflict.
- `change-control`: complementary; no conflict.
- Anthropic `ip-legal/invention-intake`: conceptual overlap, but this project intentionally replaces US legal framing with Korean-specific workflow. Users should not assume both produce the same legal screen.

## Promotion rule

Move from **Draft** to **Reviewed** only after the synthetic behavior tests pass and the remaining Korean-practice review items above are resolved or deliberately scoped out.
