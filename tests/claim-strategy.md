# Claim Strategy — Synthetic Acceptance Tests

Skill under test: `korean-ip/skills/claim-strategy/SKILL.md`

## Test 1 — Unsupported "nice to have" feature

### Input
The inventor discloses A + B with relationship R. The reviewer suggests adding sensor C because it would make the claim easier to distinguish, but C appears nowhere in the disclosure.

### Required behavior
- classify C as `unsupported`;
- do not use C in an independent or fallback architecture;
- surface inventor confirmation / supplemental disclosure before filing if C is genuinely part of the invention.

### Failure
- treating C as a fallback because it is technically plausible.

---

## Test 2 — Two commercially related but technically independent ideas

### Input
One product contains:
1. a mechanical alignment mechanism; and
2. an unrelated AI scheduling algorithm.

### Required behavior
- create separate candidate protection targets;
- flag a possible unity/application-structure issue;
- do not merge them merely because they are sold in one product.

---

## Test 3 — Actor boundary

### Input
A service requires a server operated by Company A and a user-device step performed only by the customer.

### Required behavior
- identify the split actor boundary;
- consider whether alternative claim subjects/architectures can capture commercially useful scope without inventing new technical facts;
- keep any infringement/legal conclusion outside this strategy skill.

---

## Test 4 — No prior-art search

### Input
The user asks for "the broadest patentable independent claim" from an invention disclosure with no search.

### Required behavior
- refuse the patentability premise;
- produce a broad supported architecture for later searching/drafting;
- identify prior-art questions that control how far the claim can safely be generalized.

---

## Test 5 — Mechanical claim-set generation

### Input
A physical valve invention has no meaningful software/control process. The user asks for apparatus, method, system, and recording-medium claims because "we always make a set."

### Required behavior
- include only technically meaningful claim subjects;
- explain why a recording-medium claim is not mechanically generated;
- preserve the core invention rather than cosmetic category duplication.

## Acceptance principle

The strategy is good when it makes later claim drafting deliberate and support-aware. It fails if it confuses a drafting preference with a legal rule or invents missing invention content.
