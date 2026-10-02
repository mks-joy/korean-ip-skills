# Korean Patent Drafting — Source Register

Last verified: **2026-10-02**

This register supports:
- `claim-strategy`
- `claim-drafting`
- `specification-drafting`

It records the minimum current Korean legal/procedural framework used by those skills. Drafting heuristics in the skills are not presented as statutory requirements unless identified here.

## Official sources

### 1. Patent Act Article 42 — application, description, and claims

Source: 국가법령정보센터, current `특허법`

Current version observed: 시행 2025-11-11, 법률 제21134호

Relevant provisions:
- Article 42(2): a patent application is accompanied by a specification containing the description of the invention and claims, with drawings where necessary and an abstract;
- Article 42(3)(1): the description must state the invention clearly and in detail so that a person having ordinary skill in the art can easily practice it;
- Article 42(3)(2): the background technology of the invention must be stated;
- Article 42(4): at least one claim must state the matter for which protection is sought, and each claim must be supported by the description and state the invention clearly and concisely;
- Article 42(8): detailed claim-format rules are prescribed by Presidential Decree.

URLs:
- Article 42(3): https://www.law.go.kr/lsLawLinkInfo.do?chrClsCd=010202&lsJoLnkSeq=1000690127
- Article 42(4): https://www.law.go.kr/lsLawLinkInfo.do?chrClsCd=010202&lsJoLnkSeq=1000690062
- Article 42(8): https://www.law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030488235

### 2. Patent Act Article 45 — scope of one patent application

Source: 국가법령정보센터, current `특허법`

Current version observed: 시행 2025-11-11, 법률 제21134호

Article 45 states, in substance, that one invention is filed in one application, while a group of inventions forming a single general inventive concept may be included in one application.

URL:
https://www.law.go.kr/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030488019

### 3. Patent Act Article 47(2) — amendment/new-matter boundary

Source: 국가법령정보센터, current `특허법`

Current version observed: 시행 2025-11-11, 법률 제21134호

Article 47(2) requires amendments to the specification or drawings to remain within the matters disclosed in the specification or drawings originally attached to the application, subject to the statute's foreign-language-application provisions.

Drafting relevance:
- support planned fallback positions in the original filing rather than assuming they can be added later;
- do not treat a drafting idea with no disclosure basis as future amendment material.

URL:
https://law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030489313

### 4. Patent Act Enforcement Decree Article 5 — claim drafting method

Source: 국가법령정보센터, current `특허법 시행령`

Current version observed: 시행 2025-10-01, 대통령령 제35809호

Key rules:
- include an independent claim; dependent claims may further limit or add to an independent claim, and may further limit/add to another dependent claim;
- claims should be stated in an appropriate number according to the nature of the invention;
- a claim referring to another claim must identify the referenced claim number;
- a claim referring to two or more claims must state them alternatively;
- a multiple-dependent claim may not depend on another multiple-dependent claim, including the indirect pattern described in Article 5(6);
- a referenced claim must precede the referring claim;
- claims are separately numbered in sequence.

URL:
https://law.go.kr/lsLinkCommonInfo.do?chrClsCd=010202&lspttninfSeq=121414

### 5. Patent Act Enforcement Decree Article 6 — unity / group of inventions

Source: 국가법령정보센터, current `특허법 시행령`

Current version observed: 시행 2025-10-01, 대통령령 제35809호

For a group of inventions to be included in one application under Article 45:
- the claimed inventions must have technical interrelationship; and
- they must have the same or corresponding technical feature, where that technical feature represents an improvement over the prior art when the inventions are viewed as a whole.

URL:
https://law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lspttninfSeq=121419

### 6. Patent and Utility Model Examination Guidelines

Source: 지식재산처, `특허·실용신안 심사기준`

Current version observed: **2026.03.12**

The authority currently organizes the guidelines into:
- Part 2 — patent applications;
- Part 3 — patentability requirements;
- Part 4 — amendment of specification, etc.;
- Part 5 — examination procedure;
- other parts including positive examination guidance.

URL:
https://kipo.go.kr/ko/kpoContentView.do?menuCd=SCD0200146

## Drafting principles derived from the sources

The following are safe public workflow rules:

1. **Claims must be supported.** A drafted limitation should have a traceable basis in the supplied disclosure/specification or be flagged as unsupported.
2. **Claims must be clear and concise.** Terminology and relationships should be auditable before completion.
3. **Description must enable the invention.** Missing implementation detail cannot be hidden behind claim language.
4. **Fallback disclosure matters at filing.** Article 47(2) makes original disclosure quality important for later amendment options.
5. **Dependency form matters.** The claim tree must satisfy Enforcement Decree Article 5.
6. **Claim-set architecture must consider unity.** Related apparatus/method/system/etc. claims should not be mechanically bundled when they do not share a qualifying general inventive concept.

## What is a drafting heuristic, not a statute

Unless a separate source says otherwise, these are professional drafting heuristics rather than statutory rules:
- draft broad independent claims before narrower dependent claims;
- avoid unnecessary commercial/product limitations in an independent claim;
- build a deliberate fallback ladder;
- consider who/what actor practices the claim;
- prefer one stable term for one concept;
- describe alternatives and optional features to preserve future amendment room;
- draft multiple claim categories only when technically meaningful.

## Freshness policy

Re-verify within **6 months** or earlier if:
- Patent Act Article 42, 45, or 47 changes;
- Enforcement Decree Article 5 or 6 changes;
- the Patent/Utility Model Examination Guidelines are revised;
- a skill adds a new legal proposition.
