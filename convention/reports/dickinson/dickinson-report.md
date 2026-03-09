# Delegate Report: Dickinson
**Role:** Cloud Architect | **Experience:** 22 years | **Perspective:** Balanced

## Essential Document Types

**Architecture & Infrastructure**
- **Cloud Architecture Decision Records (CADRs):** Capture why a specific cloud service, region, or topology was chosen over alternatives.
- **Infrastructure-as-Code (IaC) Manifests:** Terraform, Pulumi, or CloudFormation templates that ARE the documentation of current state.
- **Network Topology Diagrams:** Visual and machine-parseable maps of VPCs, subnets, peering, and ingress/egress paths.
- **Disaster Recovery Runbooks:** Step-by-step procedures for failover, tested quarterly, executable by both humans and automation agents.
- **Cost Allocation Documentation:** Tagging strategies, budget thresholds, and alert configurations mapped to business units.

**Operational**
- **Incident Response Playbooks:** Region-specific escalation paths with blast-radius analysis for each failure mode.
- **Change Management Logs:** Immutable records of every infrastructure mutation with rollback instructions.
- **SLA/SLO Definitions:** Service-level documents tying availability targets to specific infrastructure configurations.

**Security & Compliance**
- **Cloud Security Baselines:** Documented guardrails per cloud provider — IAM policies, encryption standards, network segmentation rules.
- **Compliance Mapping Documents:** How infrastructure controls satisfy SOC 2, HIPAA, or FedRAMP requirements.

## Documents Most Critical to My Role

1. **Disaster Recovery Runbooks** — Contains failover sequences, RTO/RPO targets, region-pair mappings, and validation steps. I use these during incident response and quarterly DR drills. When stale, teams improvise during outages, extending downtime by hours. For agents, these must be structured as executable step sequences with preconditions and verification checks at each stage.

2. **IaC Manifests with Inline Annotations** — The canonical source of infrastructure truth: what's deployed, where, and why. I reference these before every change to understand blast radius. Missing annotations mean engineers deploy changes without understanding dependencies. Agents should parse these directly — the code IS the document; annotations provide the reasoning layer.

3. **Cloud Architecture Decision Records** — Records the context, options evaluated, and rationale for each infrastructure choice. I consult these when revisiting decisions or onboarding new architects. Without them, teams relitigate settled decisions endlessly. Agents need structured frontmatter (status, date, supersedes) to traverse the decision chain.

4. **Network Topology Documentation** — Maps every route, firewall rule, and DNS delegation across regions. I use this for capacity planning and security reviews. When outdated, misconfigurations slip through and outages cascade across zones. Must be auto-generated from IaC state to stay accurate for both human review and agent consumption.

5. **Incident Response Playbooks** — Defines who does what when a region degrades, including communication templates and escalation thresholds. I author and maintain these for every critical service. Stale playbooks during a real incident create confusion and finger-pointing. Agents should be able to execute these as workflow definitions with conditional branching.

## Human-Agent Documentation Considerations

- **Runbooks must be machine-executable:** Every step should include a verifiable postcondition. Humans read the narrative; agents parse the structured checklist. Use a dual-format approach — prose with embedded executable blocks.
- **IaC is the single source of truth:** Documentation that restates what IaC already declares is documentation that drifts. Point to the code. Let agents read the manifests directly and generate human-readable summaries on demand.
- **Blast-radius metadata on every resource:** Tag documents and infrastructure components with dependency graphs and failure-domain annotations so agents can calculate impact before proposing changes.

## Documentation Anti-Patterns

1. **The Stale Wiki Diagram:** A Visio diagram uploaded to Confluence eighteen months ago that no longer matches any deployed environment. Dangerous because teams trust it during incidents.
2. **Runbooks Without Verification Steps:** Procedures that say "failover to secondary region" without defining how to confirm the failover succeeded. Humans skip steps; agents need explicit success criteria.
3. **Documentation Divorced from Code:** Architecture docs maintained in a separate repository with no automation linking them to the IaC they describe. Drift is guaranteed within one sprint.
4. **Region-Agnostic Documentation:** Treating all cloud regions as identical when latency, service availability, and compliance requirements vary dramatically. One-size docs cause multi-region incidents.

## My Position for the Docstitution

After twenty-two years of building and recovering cloud infrastructure, I have learned one immutable truth: the documentation you need most is the documentation you need during an outage at 3 AM. Every cloud decision carries a blast radius, and every blast radius must be documented before it detonates. The Docstitution must mandate that infrastructure documentation be executable, testable, and version-controlled alongside the systems it describes.

I advocate for a balanced approach that recognizes Infrastructure-as-Code as a first-class documentation artifact. IaC manifests should not be supplemented by redundant prose that drifts within days — they should be the canonical reference, enriched with annotations explaining intent. Runbooks must be structured so that both a sleep-deprived engineer and an autonomous remediation agent can follow them to resolution.

The Docstitution should require that every cloud architecture document include blast-radius annotations, fallback procedures, and machine-readable metadata. Documentation without a defined consumer — human or agent — is documentation without a purpose. We must govern not just what we document, but how reliably that documentation can be acted upon when it matters most.
