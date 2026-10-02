# Security and Trust Policy

AI-agent skills are executable instructions in practice. Treat third-party skill text as untrusted input.

## Mandatory review before accepting a new skill

Review:
- declared purpose and audience;
- files it reads and writes;
- shell/code execution;
- network calls and external URLs;
- MCP/connectors and credential scope;
- hooks or scheduled/ambient execution;
- instructions that override existing agent configuration;
- hidden or encoded content;
- attempts to read credentials or unrelated user data;
- legal-rule freshness and jurisdiction;
- conflicts with already-installed skills.

## High-risk changes

Any change that adds or expands any of the following requires human review:
- Bash or arbitrary code execution;
- hooks;
- MCP wildcard access;
- external network destinations;
- writes outside the skill's own working/output scope;
- credential access;
- automatic sending, filing, payment, deletion, or other consequential actions.

## Confidentiality

Never commit:
- client documents or correspondence;
- unpublished inventions;
- matter-specific facts;
- credentials, tokens, API keys, passwords, certificates, or private keys;
- private ABC IP LAW operating data.

## Reporting

For security concerns, open a GitHub issue only if the report itself contains no sensitive information. Sensitive reports should be sent privately to the maintainer.
