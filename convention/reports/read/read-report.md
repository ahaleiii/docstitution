# Delegate Report: Read
**Role:** Security Engineer | **Experience:** 15 years | **Perspective:** Balanced

## Essential Document Types

**Threat & Risk**
- **Threat Models** — Structured analysis of attack surfaces, threat actors, attack vectors, and mitigations per component.
- **Security Architecture Docs** — Trust boundaries, authentication flows, encryption schemes, and segmentation decisions.
- **Risk Assessment Reports** — Evaluated risks with likelihood, impact, residual risk, and compensating controls.
- **Vulnerability Management Docs** — Tracking and remediation lifecycle for discovered vulnerabilities with severity and SLAs.

**Standards & Guidance**
- **Secure Coding Guidelines** — Language-specific rules for preventing common vulnerability classes.
- **Security Review Checklists** — Standardized criteria applied at design reviews, code reviews, and deployment gates.
- **Compliance Mapping Docs** — Maps controls to regulatory frameworks (SOC 2, GDPR, HIPAA) with evidence references.
- **Secrets Management Guide** — Procedures for storing, rotating, and accessing credentials and API keys.

**Operational Security**
- **Incident Response Playbooks** — Step-by-step security incident procedures with escalation paths.
- **Access Control Policies** — Role definitions, permission models, and provisioning procedures.
- **Security Exception Register** — Documented deviations from policy with justification and expiration dates.

## Documents Most Critical to My Role

**1. Threat Models**
Contains system scope, trust boundaries, threats (STRIDE), risk ratings, and mitigations. When missing, teams ship without understanding their attack surface. Agents must reference threat models but details must be access-controlled to prevent leaking sensitive architecture.

**2. Secure Coding Guidelines**
Contains vulnerability class, code examples (vulnerable and fixed), and detection rules. When stale, known vulnerability patterns repeat. Agents must apply these as structured constraints enabling automated enforcement.

**3. Security Review Checklists**
Contains review criteria by change type, required evidence, and escalation triggers. When absent, reviews depend on who reviews. Agents should consume these as structured rule sets for consistent flagging.

**4. Incident Response Playbooks**
Contains incident categories, severity classification, response steps, and evidence preservation. When missing, responders improvise and miss critical steps. Agents need structured procedures but playbooks must control what agents can share.

**5. Compliance Mapping Docs**
Contains control frameworks, implementation details, evidence locations, and gap analysis. When outdated, audit prep becomes a scramble. Agents can automate evidence collection if mappings link controls to artifacts programmatically.

## Human-Agent Documentation Considerations

1. **Security docs need access tiers** — threat models and vulnerability details require classification levels preventing agents from exposing sensitive details.
2. **Secure coding guidelines must be agent-enforceable** — express rules as structured specs with detection patterns so agents apply them as hard constraints.
3. **Every document must pass a secrets review** — automated scanning for credentials and internal URLs before publication or agent access.

## Documentation Anti-Patterns

1. **Security through obscurity** — no security docs because "writing it down is a risk." The answer is access control, not absence.
2. **Threat model as archaeology** — created during initial design, never updated as the system evolved.
3. **Secrets in documentation** — API keys, connection strings, or internal hostnames embedded in docs, especially dangerous with agent access.
4. **Compliance theater** — docs describing aspirational controls rather than implemented ones.

## My Position for the Docstitution

Security documentation exists in unique tension: it must exist to be effective, yet can become a weapon if exposed carelessly. The Docstitution must mandate threat models, secure coding guidelines, and review checklists — while establishing access classification controlling which documents agents and humans can access.

In the agentic era, every document becomes potential AI input. Agents must consume secure coding guidelines as enforceable rules but must not access vulnerability details without authorization. The Docstitution must establish tiered access. Security is not a section — it is a lens through which all documentation must be reviewed.
