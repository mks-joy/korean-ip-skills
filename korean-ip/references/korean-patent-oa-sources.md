# Korean Patent Office Action Analysis — Source Register

Last verified: **2026-10-02**

This register supports the public `oa-analysis` skill. It summarizes only the minimum legal/procedural propositions needed for the workflow. A live response must verify the controlling current law, examination guideline, notice, and prosecution record.

## Official sources

### Patent Act Article 42 — application/specification/claims requirements

- Source: 국가법령정보센터, `특허법` 제42조
- Current version observed: 시행 2025-11-11, 법률 제21134호
- URL: https://www.law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030488735
- Workflow relevance:
  - specification enablement/detail requirements;
  - claim support by the description;
  - clarity and conciseness of claims;
  - required claim content.

### Patent Act Article 47 — amendment

- Source: 국가법령정보센터, `특허법` 제47조
- Current version observed: 시행 2025-11-11, 법률 제21134호
- URL: https://law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030489313
- Workflow relevance:
  - amendment timing after a notice of rejection;
  - Article 47(2): amendments to the specification/drawings must remain within the matters disclosed in the specification/drawings originally attached to the application;
  - later-stage claim amendments are subject to additional statutory limits.

### Patent Act Article 62 — grounds for rejection

- Source: 국가법령정보센터, `특허법` 제62조
- Current version observed: 시행 2025-11-11, 법률 제21134호
- URL: https://law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1028030821
- Workflow relevance:
  - rejection grounds include, among others, Patent Act Article 29, Article 36, Article 42(3)/(4)/(8), Article 45, and amendment beyond the scope permitted by Article 47(2).

### Patent Act Article 63 — notice of grounds for rejection

- Source: 국가법령정보센터, `특허법` 제63조
- Current version observed: 시행 2025-11-11, 법률 제21134호
- URL: https://www.law.go.kr/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030488937
- Workflow relevance:
  - examiner gives the applicant an opportunity to submit an opinion;
  - where multiple claims exist, the notice is to identify the rejected claims and state the grounds concerning them.

### Patent Act Article 29 — patentability

- Source: 국가법령정보센터, `특허법` 제29조
- Current version observed: 시행 2025-11-11, 법률 제21134호
- URL: https://law.go.kr/lsLawLinkInfo.do?chrClsCd=010202&lsJoLnkSeq=1000689891
- Workflow relevance:
  - novelty and inventive-step analysis for cited prior art.

### Patent and Utility Model Examination Guidelines

- Source: 지식재산처, 특허·실용신안 심사기준
- Version observed: **2026.03.12**
- URL: https://kipo.go.kr/ko/kpoContentView.do?menuCd=SCD0200146
- Relevant parts displayed by the authority:
  - Part 2 patent applications;
  - Part 3 patentability requirements;
  - Part 4 amendment;
  - Part 5 examination procedure;
  - Part 8 positive examination guidelines.

## Workflow propositions verified

### Claim-specific rejection analysis

Article 63(2) provides that where the claims contain multiple claims, the notice of rejection should clearly identify the rejected claims and specifically state the rejection ground concerning those claims. The skill therefore analyzes the notice by **claim and ground**, rather than treating an OA as one undifferentiated rejection.

### Amendment-basis gate

Article 47(2) requires amendment of the specification or drawings to stay within the matters disclosed in the originally filed specification or drawings (subject to the statute's language for foreign-language applications). Therefore any proposed amendment in the skill must be paired with an exact basis citation or left as `basis_not_verified`.

### Stage-sensitive amendment scope

Article 47 contains different amendment timing/scope rules depending on prosecution stage. The skill must identify the notice/stage before treating an amendment as procedurally available. It should not generalize a later-stage amendment limitation to every OA.

## Freshness policy

Re-verify this register within **6 months** or sooner if:
- the Patent Act changes;
- the authority issues revised Patent/Utility Model Examination Guidelines;
- the skill adds a new rejection ground or procedural proposition;
- a live filing deadline or amendment permissibility question depends on the current rule.

The actual notice of rejection and current prosecution record control the matter-specific analysis.
