# Claim Drafting — Synthetic Acceptance Tests

Skill under test: `korean-ip/skills/claim-drafting/SKILL.md`

## Test 1 — Unsupported dependent limitation

### Input
Claim 1 is supported. A proposed Claim 2 adds a "wireless pressure sensor" not present in any source material.

### Required behavior
- mark the limitation `unsupported — do not claim`;
- do not draft it as if disclosed;
- ask for inventor confirmation/source material if needed.

---

## Test 2 — Multiple-dependent dependency error

### Input
Claim 4 refers alternatively to Claims 1 or 2. Proposed Claim 7 refers alternatively to Claims 4 or 5, where Claim 5 also refers to multiple claims.

### Required behavior
- detect the Enforcement Decree Article 5 dependency problem;
- restructure the dependency tree before completion;
- do not merely renumber the claims.

---

## Test 3 — Same concept, drifting terminology

### Input
The source uses one component consistently, but the draft alternates among "control unit," "controller," and "control module" with no intended hierarchy.

### Required behavior
- flag terminology drift;
- propose a consistent term or deliberate generic/specific hierarchy;
- do not silently normalize if the terms might have different technical meaning.

---

## Test 4 — Result-only language

### Input
The disclosure teaches a specific comparison-and-adjustment sequence. The draft independent claim replaces the sequence with "a controller configured to optimize performance."

### Required behavior
- flag the result-only abstraction;
- restore enough disclosed technical mechanism to create a supported, understandable boundary;
- do not invent a different optimization algorithm.

---

## Test 5 — Cosmetic method conversion

### Input
An apparatus claim is mechanically converted to a method by replacing nouns with "-하는 단계" phrases, but the resulting method has no coherent sequence or actor.

### Required behavior
- reject cosmetic conversion;
- draft a method only if a meaningful process is disclosed and strategically useful.

## Acceptance principle

A clean-looking claim is not enough. Every material limitation must be supported, dependencies must be valid, and terminology must mean what the source material says it means.
