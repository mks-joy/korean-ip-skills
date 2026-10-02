# Korean Patent Claim Chart / FTO — Source Register

Last verified: **2026-10-02**

This register supports the public `fto-claim-chart` skill. It does not attempt to encode the full Korean infringement doctrine.

## Official sources

### Patent Act Article 2 — definition of implementation

- Source: 국가법령정보센터, current `특허법`
- Current version observed: 시행 2025-11-11, 법률 제21134호
- URL: https://www.law.go.kr/lsSc.do?menuId=1&query=%ED%8A%B9%ED%97%88%EB%B2%95&subMenuId=15&tabMenuId=81
- Relevance: the acts constituting "implementation" differ by invention type and matter to FTO scope.

### Patent Act Article 88 — patent term

- Source: 국가법령정보센터, `특허법` 제88조
- Current version observed: 시행 2025-11-11, 법률 제21134호
- URL: https://www.law.go.kr/lsLinkCommonInfo.do?lsJoLnkSeq=1030488089
- Relevance: ordinary patent term runs from registration until 20 years after the filing date, subject to the statute and any applicable term adjustments/extensions or other status events.

### Patent Act Article 94 — effect of patent right

- Source: 국가법령정보센터, `특허법` 제94조
- Current version observed: 시행 2025-11-11, 법률 제21134호
- URL: https://law.go.kr/LSW/lsSideInfoP.do?docCls=jo&joBrNo=00&joNo=0094&lsiSeq=279827&urlMode=lsScJoRltInfoR
- Relevance: a patent owner has the exclusive right to commercially practice the patented invention, subject to statutory qualifications.

### Patent Act Article 97 — scope of patented invention

- Source: 국가법령정보센터, `특허법` 제97조
- Current version observed: 시행 2025-11-11, 법률 제21134호
- URL: https://www.law.go.kr/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1030175301
- Relevance: the scope of the patented invention is determined by the matters stated in the claims. This supports claim-first element mapping.

### Patent Act Article 127 — acts deemed infringement

- Source: 국가법령정보센터, `특허법` 제127조
- Current version observed: 시행 2025-11-11, 법률 제21134호
- URL: https://www.law.go.kr/LSW/lsLinkCommonInfo.do?chrClsCd=010202&lsJoLnkSeq=1025176577
- Relevance: certain commercial acts involving items used only for producing a patented product or practicing a patented method may be treated as infringement.

## Deliberate limitations

This source register does **not yet encode**:
- Supreme Court doctrine-of-equivalents tests;
- detailed claim-construction case law;
- exhaustion;
- prior-use rights;
- experimental-use and other Article 96 exceptions;
- patent invalidity defenses;
- provisional rights/compensation concerning published applications;
- license, estoppel, FRAND/SEP, or competition-law issues.

Those issues must remain separate review flags until dedicated source modules are added.

## Status rule

Do not infer that a Korean patent is enforceable merely because:
- a publication exists;
- a registration number is present;
- 20 years from filing have not elapsed.

Verify the current right/status, operative claims, any correction/invalidity/post-grant events, lapse/expiration, and relevant term adjustments/extensions from current authoritative records before relying on enforceability.

## Freshness policy

Re-verify within **6 months** or sooner if the Patent Act changes or a substantive infringement doctrine is added.
