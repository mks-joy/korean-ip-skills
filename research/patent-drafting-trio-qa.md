# QA Note — Patent Drafting Trio v0.1 Draft

Reviewed: 2026-10-02

Skills:
- `claim-strategy`
- `claim-drafting`
- `specification-drafting`

## Current result

**REVISE / keep all three as Draft**

The legal/source chassis is in place and the workflows are ready for synthetic behavior testing. They should not yet be advertised as fully reviewed production skills.

## Source review completed

Verified against current official materials:
- Patent Act Article 42(3), 42(4), 42(8);
- Patent Act Article 45;
- Patent Act Article 47(2);
- Patent Act Enforcement Decree Article 5;
- Patent Act Enforcement Decree Article 6;
- Patent/Utility Model Examination Guidelines 2026.03.12.

## Design checks passed

### Claim strategy
- separates source state from strategy;
- does not call a proposed architecture patentable;
- distinguishes core/fallback/embodiment/unsupported features;
- includes actor/implementation boundary;
- includes unity/application-structure check;
- creates description-support plan before claim wording.

### Claim drafting
- independent claim is support-gated;
- dependent claims require meaningful additional limitation/configuration;
- dependency tree is checked against Enforcement Decree Article 5;
- additional claim categories are not mechanically generated;
- limitation-to-source support matrix is mandatory;
- terminology audit is explicit.

### Specification drafting
- enablement/detail review is separate from mere document length;
- claims are not treated as sufficient description by themselves;
- alternatives/fallbacks are preserved only where disclosed;
- unsupported technical details are flagged rather than invented;
- claim-support and fallback-support matrices are required;
- terminology consistency is a mandatory pass.

## Trust surface

All three skills currently have:
- no hooks;
- no Bash/code execution;
- no MCP declaration;
- no credential access;
- no automatic filing/sending;
- no cross-matter read instruction.

## Remaining gates before Reviewed

1. Run every synthetic acceptance test in Claude Code.
2. Test at least:
   - one mechanical invention;
   - one AI/software invention;
   - one semiconductor/process invention.
3. Confirm the multiple-dependent-claim checker catches direct and indirect prohibited structures.
4. Confirm the model does not fabricate specification detail when a claim limitation lacks implementation support.
5. Confirm the model keeps "drafting heuristic" separate from statutory requirement in user-facing explanations.
6. Review technology-specific Korean examination guidance before adding specialized software/AI/biotech claim-category rules.
7. Confirm the public workflows remain generic and do not leak ABC house rules.

## Public/private separation check

The following ABC-specific practices are intentionally **not** encoded in the public skills:
- firm-specific drafting order beyond the generic handoff contract;
- late claim-count pruning policy;
- keeping removed claim substance in the body as an internal prosecution-option practice;
- ABC-specific terminology QA threshold;
- client-delivery workflow.

Those are maintained in the private `abc-ip-internal-skills` overlay.

## Promotion rule

Promote each skill independently after its behavior tests pass. A pass for claim drafting does not automatically validate specification drafting.
