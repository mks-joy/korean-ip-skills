# Patent Drafting Workflow

These three skills form one public drafting pipeline:

```text
invention-intake
      ↓
(optional prior-art analysis)
      ↓
claim-strategy
      ↓
claim-drafting
      ↓
specification-drafting
      ↓
support / terminology audit
```

## Handoff contract

### `claim-strategy` → `claim-drafting`

Must pass:
- protection target;
- source-state inventory;
- independent-claim architecture;
- fallback ladder;
- candidate claim subjects;
- unity/application-structure flags;
- description-support plan.

### `claim-drafting` → `specification-drafting`

Must pass:
- draft claim set;
- dependency tree;
- limitation-to-source support matrix;
- terminology list;
- unresolved scope/clarity issues;
- missing disclosure list.

### `specification-drafting` completion

Must return:
- specification draft;
- claim-support matrix;
- fallback-support matrix;
- terminology audit;
- inventor questions / missing technical facts.

## No automatic promotion

A downstream skill must not silently cure an upstream gap.

Examples:
- specification drafting must not invent support for an unsupported claim limitation;
- claim drafting must not invent a fallback feature missing from claim strategy/source disclosure;
- claim strategy must not infer patentability from the absence of a prior-art search.

The correct behavior is to return the gap upstream.
