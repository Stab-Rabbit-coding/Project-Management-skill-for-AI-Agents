# AGENTS.md

Authoritative instructions for AI agents working in this repository.

<!-- workspace-rule: component-sourcing-openness 2026-10-17 -->
## Component Sourcing and Openness (workspace rule, 2026-10-17)

Owner rule (S. Griffing, 2026-10-17), applied to every repository in this workspace. It gates
every part selection before a part enters a schematic, BOM or design document. A part that fails
either rule **shall not** be designed in; existing parts that fail are replaced and tracked in the
repository's work plan.

- **No restricted-country silicon.** No integrated circuit, discrete semiconductor or
  semiconductor-bearing module shall be used whose manufacturer (the design owner / brand of
  record) is:
    - domiciled in a restricted country: the People's Republic of China (including Hong Kong and
      Macau), the Russian Federation, the Islamic Republic of Iran, the Democratic People's
      Republic of Korea, or any country later designated a "foreign country of concern"
      [REF-LAW-003];
    - owned by, controlled by, or subject to the direction of the government or ruling party of a
      restricted country, or a subsidiary or affiliate of such an entity [REF-LAW-002
      §1822(1)(D)-(E)]; or
    - a named or determined covered entity [REF-LAW-001 §5949(j)(3)] [REF-LAW-002 §1822(1)].

  **Scope.** The test is manufacturer domicile and control (owner decision 2026-10-17); wafer-fab
  and assembly/test sites are recorded where the vendor publishes them but do not disqualify a
  part. The rule is stricter than the statutes, which bind U.S. federal procurement; for
  uncrewed aircraft the statute reaches "the components that control the unmanned aircraft" and
  its "communication links" [REF-LAW-002 §1823(a)]. A generic part number sold by many
  manufacturers (e.g. SMAJ33CA) complies only once a compliant manufacturer is named in its
  MPN / BOM entry. Known non-compliant manufacturer: Nexperia (owned by PRC-domiciled Wingtech
  Technology).
- **Open, NDA-free documentation only.** Every IC and module shall have a datasheet, and any
  design information its circuit depends on, that is publicly available and shareable without a
  non-disclosure agreement, a confidentiality marking (e.g. "CONFIDENTIAL: Development Partners
  Only"), or redistribution terms that would stop the repository from citing and archiving it,
  as OSHWA certification requires ("third-party components such as chips must have fully
  accessible and shareable datasheets") [REF-LIC-001]. A free registration wall is acceptable only
  if the documents carry no confidentiality terms; record the access route in `REFERENCES.md`.
- Record every candidate that fails either rule as rejected, with the reason, in the design
  document that considered it, so it is not proposed again.
