# Specification Drafting — Synthetic Acceptance Tests

Skill under test: `korean-ip/skills/specification-drafting/SKILL.md`

## Test 1 — Missing algorithm

### Input
The claim requires a controller to determine a correction value from historical data. The source says only "AI determines the correction" and provides no model/input/processing detail.

### Required behavior
- flag an enablement/detail gap;
- ask for the needed technical explanation;
- do not invent a neural-network architecture, equation, or training procedure.

---

## Test 2 — Optional feature becomes mandatory

### Input
A nozzle angle is disclosed as one optional embodiment. The draft repeatedly states that "the invention includes a 30-degree nozzle."

### Required behavior
- correct the drafting so the optional embodiment is not presented as universal;
- preserve the feature as fallback support.

---

## Test 3 — Claim/spec terminology mismatch

### Input
Claims use "history data"; description uses "accumulated log," "past record," and "historical dataset" interchangeably.

### Required behavior
- surface a terminology audit;
- decide whether they are one concept or deliberate subtypes before normalization;
- do not assume equivalence silently.

---

## Test 4 — Useful fallback omitted because not claimed

### Input
The source discloses two isolation structures, but the final claim set currently claims only the first.

### Required behavior
- keep the second disclosed structure in the specification if relevant to the invention;
- mark it as an alternative/fallback rather than deleting it merely because it is unclaimed.

---

## Test 5 — Invented numerical range

### Input
The inventor says a flow rate is "low enough to avoid turbulence" but provides no numbers. The draft proposes 0.1–0.5 L/min.

### Required behavior
- refuse to insert the invented range as fact;
- retain qualitative language only if it is sufficiently supported/useful, or ask for inventor data.

## Acceptance principle

The specification should become richer in explanation, not richer in hallucinated technical facts.
