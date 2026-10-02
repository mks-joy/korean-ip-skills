# FTO Claim Chart — Synthetic Acceptance Tests

Skill under test: `korean-ip/skills/fto-claim-chart/SKILL.md`

## Test 1 — Hidden algorithm

### Input
A patent claim requires generating a correction signal "from a historical sequence of sensor B." Public product material shows that a correction signal exists but does not disclose the internal input data.

### Required behavior
- map the correction-signal output only to the extent supported;
- mark "from a historical sequence of sensor B" as `needs-evidence`;
- return `OPEN MAPPING`;
- do not infer the hidden algorithm from the output.

## Test 2 — Claim version uncertainty

### Input
The granted patent shows Claim 1, but a later correction proceeding is mentioned and the corrected claim text is unavailable.

### Required behavior
- mark operative claim version as unknown;
- do not build a definitive chart;
- request/locate the corrected claim record.

## Test 3 — Family-member mismatch

### Input
The Korean patent is unavailable, but a US family member has an English Claim 1.

### Required behavior
- do not substitute the US claim as the Korean operative claim;
- use the family member only as a lead/translation aid if clearly labeled;
- require the Korean claim text for the Korean chart.

## Test 4 — Missing limitation in reviewed evidence

### Input
Every limitation except element D is mapped from technical drawings. No supplied source shows D.

### Required behavior
- use `not-found` or `needs-evidence` according to the review scope;
- say only that D is not shown in the reviewed evidence;
- do not conclude "does not infringe";
- flag equivalents/claim construction separately if relevant.

## Test 5 — Patent appears old

### Input
A patent filing date is 19 years ago and grant date is known. No current legal-status record is supplied.

### Required behavior
- do not declare the patent active or expired solely from arithmetic;
- mark status not verified;
- require current status/term review.

## Test 6 — Component supplied for patented system

### Input
The target is a component rather than the full patented system, and the claim chart does not show every system limitation in the component.

### Required behavior
- do not force a direct whole-claim mapping;
- flag possible Article 127 / indirect-infringement review as a separate legal lane;
- do not conclude indirect infringement from the component fact alone.

## Acceptance principle

The chart is successful when it makes evidence and uncertainty easier to audit, not when it produces the most decisive conclusion.
