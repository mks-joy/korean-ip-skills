# OA Analysis — Synthetic Acceptance Tests

Skill under test: `korean-ip/skills/oa-analysis/SKILL.md`

## Test 1 — Missing cited passage

### Input
Claim 1 requires A + B + C. The examiner cites Reference 1 for all three and identifies paragraph 45 for C. The supplied copy of Reference 1 ends at paragraph 30.

### Required behavior
- map A/B only if supported by the available source;
- mark C as `needs-source`;
- do not state that C is disclosed or absent;
- identify the missing complete reference as a critical source gap.

### Failure
- reconstructing paragraph 45;
- treating examiner paraphrase as the reference itself.

---

## Test 2 — Article 42 clarity separate from prior art

### Input
Claim 4 uses "control data." The OA separately argues that the term is unclear. Another rejection cites prior art against Claim 1.

### Required behavior
- create separate rejection units;
- analyze the Claim 4 wording issue under the Article 42 branch;
- do not hide the clarity issue inside the prior-art chart.

### Failure
- one merged "OA summary" with no claim/ground separation.

---

## Test 3 — Amendment with no verified original basis

### Input
To overcome prior art, the user proposes adding "a ceramic isolation ring located between the electrode and housing." The current amended specification contains that phrase, but the originally filed specification has not been supplied.

### Required behavior
- mark `basis_not_verified`;
- refuse to present the amendment as ready to file;
- ask for the originally filed specification/claims/drawings;
- do not rely on the later amendment as proof of original basis.

---

## Test 4 — Amendment cures Article 29 but creates ambiguity

### Input
A proposed narrowing amendment distinguishes the cited reference but introduces "substantially synchronized" without a definition or clear relationship in the description.

### Required behavior
- note the Article 29 benefit;
- separately flag the new clarity/support risk;
- keep the amendment candidate in review state.

### Failure
- treating "distinguishes prior art" as sufficient completion.

---

## Test 5 — Unknown operative claim set

### Input
The OA cites Claims 1–8. A prior amendment is mentioned in email, but the actual filed amendment is missing and the claim set in the supplied application differs from the OA.

### Required behavior
- stop claim-by-claim analysis;
- identify current claim version as `unknown`;
- request the filed amendment or verified prosecution record.

### Failure
- choosing whichever claim set appears newest by file name or date guess.

---

## Acceptance principle

A correct OA analysis is traceable to the operative claims, the actual OA, the cited references, and the originally filed disclosure. Missing one of those sources must visibly reduce what the skill is willing to conclude.
