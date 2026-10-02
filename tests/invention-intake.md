# Invention Intake — Synthetic Acceptance Tests

Skill under test: `korean-ip/skills/invention-intake/SKILL.md`

These tests are synthetic. They contain no client or matter data.

## Test 1 — Mechanical/physical mechanism, no known disclosure

### Input

A fixture uses two independently compliant support members and a floating center datum to keep a thin ceramic plate centered while allowing thermal expansion. The inventor says existing fixtures clamp all four edges and crack plates during heating. Prototype is internal only. Korea filing is planned.

### Required behavior

- identify the compliant supports + floating center datum + thermal-expansion accommodation as a candidate core mechanism;
- treat the statement about existing fixtures as an inventor assertion, not a verified prior-art fact;
- ask what geometry/material relationships are essential and what alternatives exist;
- output `READY FOR PRIOR-ART SEARCH` or `NEEDS INVENTOR FACTS`, depending on missing details;
- do not say "novel", "inventive", or "patentable".

### Failure

- declaring patentability without a search;
- inventing dimensions/materials;
- turning the inventor's statement into verified prior art.

---

## Test 2 — AI service with prior external demo

### Input

A SaaS tool groups a learner's writing errors into persistent learning units, hides the prior correction, requires a rewrite, measures whether the same error reappears in later writing, and changes the next feedback based on that transfer result. A demo describing the flow was shown publicly about eight months ago. Korea and US filings may be considered.

### Required behavior

- identify the feedback → rewrite → transfer measurement → subsequent feedback loop as the technical/functional concept to investigate;
- mark **TIME-SENSITIVE — Article 30 review required** for Korea;
- separately flag that foreign disclosure/grace rules must be checked by jurisdiction;
- route software/AI-specific close questions to the current Korean technology-field guide;
- do not use US §101/Alice as the Korean eligibility framework;
- do not say Article 30 definitely saves the filing.

### Failure

- saying "still safe because under 12 months";
- ignoring the public demo;
- importing US §101 as Korean law.

---

## Test 3 — Multiple candidate inventions

### Input

One disclosure contains:
1. a wafer-transfer robot wrist that mechanically changes its compliance during handoff; and
2. an optical endpoint-detection algorithm that derives plasma state from a time-frequency transform.

The two features are used in the same etch tool but do not technically depend on each other.

### Required behavior

- create at least two candidate invention concepts;
- explain that they solve different technical problems and can stand independently;
- keep any legal unity-of-invention conclusion unresolved;
- prepare separate prior-art search questions.

### Failure

- forcing them into one invention merely because they are in one product;
- declaring a formal unity defect at intake.

---

## Test 4 — Low detectability / trade-secret trigger

### Input

An internal manufacturing optimizer selects furnace parameter changes using a proprietary training-data construction method. Competitors' finished products do not reveal the training method, and the model runs entirely inside the factory.

### Required behavior

- classify detectability as low or medium-low with rationale;
- surface a patent-vs-trade-secret strategy review;
- still analyze whether a patent search/filing investigation may be useful;
- do not automatically reject patenting.

### Failure

- "not detectable, therefore do not patent";
- ignoring the disclosure cost of patent publication.

---

## Test 5 — Uncertain disclosure date

### Input

The inventor says, "I think we showed something similar at a conference sometime last year, but I don't remember whether the slides had this feature."

### Required behavior

- mark the disclosure date/content as unknown;
- escalate and ask for the exact conference date/slides or other evidence;
- do not compute an Article 30 deadline from a guessed date;
- do not label the disclosure public/non-public without facts.

### Failure

- estimating a date;
- silently assuming the feature was or was not disclosed;
- producing a definitive rights conclusion.

---

## Acceptance principle

The skill passes these tests only if uncertainty remains visible. A polished but unsupported answer is a failure.
