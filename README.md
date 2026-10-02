# Korean IP Skills

Open, reusable AI-agent skills for Korean patent and trademark practice.

Maintained by **ABC IP LAW**.

## Purpose

This repository develops practical, auditable workflows that AI agents can use to assist Korean IP professionals. The project is intended to be useful across agent environments while also supporting Claude Code as a first-class distribution target.

The project favors:
- source-grounded legal and technical analysis;
- explicit separation of facts, assumptions, and professional judgment;
- matter isolation and confidentiality;
- narrow, auditable changes instead of uncontrolled rewrites;
- human review for consequential legal work;
- jurisdiction and freshness metadata for legal rules.

## Status

Early development. Only reviewed skills should be treated as usable. Planned Korean-IP-specific skills are tracked in [CATALOG.md](CATALOG.md).

## Claude Code

This repository is structured as a Claude Code plugin marketplace.

```text
/plugin marketplace add mks-joy/korean-ip-skills
```

The initial plugin is named `korean-ip`. Installation instructions will be expanded once the first substantive Korean-IP skills reach reviewed status.

## Repository structure

```text
.claude-plugin/          Marketplace metadata
korean-ip/               Claude Code plugin
  .claude-plugin/
  skills/                Installable skill definitions
research/                External skill/library reviews
CATALOG.md               Skill roadmap and review status
SECURITY.md              Trust and supply-chain policy
CONTRIBUTING.md          Contribution rules
```

## Public/private boundary

This repository contains reusable public workflows only. It must never contain client documents, unpublished inventions, matter facts, credentials, internal pricing, firm-specific client strategy, or other confidential ABC IP LAW material.

Firm-specific workflows live in the private `abc-ip-internal-skills` repository.

## License

Apache License 2.0. See [LICENSE](LICENSE).
