# Korean Patent Invention Intake — Source Register

Last verified: **2026-10-02**

This register supports the public `invention-intake` skill. It is not a substitute for checking the current law/guidance when a live filing decision depends on it.

## Primary / official sources

### 1. Patent Act — current statute

- Source: 국가법령정보센터, `특허법`
- Current version observed: 시행 2025-11-11, 법률 제21134호
- URL: https://www.law.go.kr/lsSc.do?menuId=1&query=%ED%8A%B9%ED%97%88%EB%B2%95&subMenuId=15&tabMenuId=81
- Intake relevance:
  - Article 2(1): definition of "invention";
  - Article 29: industrial applicability, novelty, inventive step and earlier-filed disclosure issues;
  - Article 30: certain disclosures may be treated as not destroying novelty/inventive step if statutory conditions are met;
  - Article 36: first-to-file rule for identical inventions.

### 2. Patent and Utility Model Examination Guidelines

- Source: 지식재산처, 특허·실용신안 심사기준
- Version observed: **2026.03.12**
- URL: https://kipo.go.kr/ko/kpoContentView.do?menuCd=SCD0200146
- Intake relevance:
  - Part 3 patentability requirements;
  - examination framework for novelty/inventive step and other patentability issues;
  - use as the default examination-practice reference before embedding detailed doctrinal tests.

### 3. Technology-field Examination Practice Guide

- Source: 지식재산처, 기술분야별 심사실무가이드
- Version observed: **2026.03**
- URL: https://www.kipo.go.kr/ko/kpoContentView.do?menuCd=SCD0200147
- Covered areas shown by the authority include AI, IoT services, biotech, plants, pharmaceuticals, intelligent robots, autonomous driving, 3D printing, compounds, cosmetics, digital healthcare, and semiconductors.
- Intake relevance:
  - route technology-specific eligibility/description issues to the appropriate guide;
  - avoid importing US software/AI eligibility tests into Korean practice.

## Verified legal points used by the skill

### Patent Act Article 29

The current statute states that an industrially applicable invention may be patented except where it falls within the listed prior-art conditions, and Article 29(2) bars an invention that a person having ordinary knowledge in the technical field could easily make from Article 29(1) prior art.

### Patent Act Article 30

The current statute provides a 12-month window for certain disclosures made by, or against the intent of, the person entitled to the patent, subject to the statutory conditions. The skill treats this only as an **urgent review trigger**, not as permission to disclose before filing.

The statute also contains procedural requirements for claiming the exception. A live filing should verify the current procedural requirements and evidence rather than relying on the skill's memory.

### Patent Act Article 36

For identical inventions filed on different days, the earlier applicant is the one who can obtain the patent, subject to the statute's detailed rules. The intake therefore treats unnecessary filing delay as a strategy risk.

## Freshness policy

Re-verify this register within **6 months** or sooner if:
- the Patent Act changes;
- the authority publishes revised Patent/Utility Model Examination Guidelines;
- the relevant technology-field guide is revised;
- a skill change adds a new legal proposition.

The skill should prefer a live official-source check over this bundled summary whenever the current rule controls a live deadline or filing decision.
