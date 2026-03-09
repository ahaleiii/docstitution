# Delegate Report: Carroll
**Role:** Infrastructure Developer | **Experience:** 16 years | **Perspective:** Balanced

## Essential Document Types

**Infrastructure-as-Code Docs**
- **IaC Module Documentation** — Purpose, inputs, outputs, and usage examples for every Terraform/Pulumi module.
- **Environment Matrix** — Current state of every environment including versions, configurations, and resource allocations.
- **Cloud Resource Inventory** — Living catalog of provisioned resources with costs, owners, and lifecycle status.

**Deployment & Pipeline Docs**
- **Deployment Runbooks** — Step-by-step procedures including pre-checks, commands, and rollback steps agents can execute.
- **Pipeline Architecture Docs** — CI/CD topology showing stages, gates, triggers, and artifact flows.
- **Secrets Management Guide** — How secrets are stored, rotated, and injected—never the secrets themselves.

**Network & Platform Docs**
- **Network Topology Diagrams** — VPCs, subnets, peering, and DNS routing visualized and versioned.
- **Disaster Recovery Plans** — RTO/RPO targets, failover procedures, and backup verification schedules.

## Documents Most Critical to My Role

1. **IaC Module Documentation** — Module purpose, input variables with types, outputs, and usage examples. Used when composing infrastructure and during review. Missing docs mean engineers copy-paste modules blindly and agents cannot propose changes safely. Agents parse variable descriptions; humans need examples for intent.

2. **Environment Matrix** — Maps environments to deployed versions, configs, and resource specs. Consulted before deployments and during incidents. Stale matrices cause wrong-target deployments. Agents validate targets and detect drift; humans answer "what's running where?"

3. **Deployment Runbooks** — Pre-checks, commands, verification steps, and rollback procedures. Missing runbooks mean deployments rely on memory. Agents execute runbooks as playbooks; humans follow them as checklists under pressure.

4. **Network Topology Diagrams** — VPC layout, subnets, security groups, and DNS routing. Outdated diagrams cause misconfigured rules. Agents compare diagrams against live state; humans need spatial representations for traffic flow.

5. **Pipeline Architecture Docs** — CI/CD stages, triggers, gates, and notifications. Without them, pipeline changes introduce regressions. Agents validate configs against docs; humans need the big picture of how code reaches production.

## Human-Agent Documentation Considerations
- **Terraform is documentation—but insufficient alone**: Variable descriptions, output descriptions, and module READMEs must be mandatory. HCL documents the "what"; descriptions document "why" and "how to use."
- **Environment state must be queryable**: Agents need structured data (JSON/YAML) they can query and diff. Auto-generate matrices from live state instead of maintaining static tables.
- **Runbooks must be executable**: Structure steps so agents can parse them into automatable sequences—numbered steps, explicit commands, expected outputs, decision branches.

## Documentation Anti-Patterns
1. **"Terraform Is Self-Documenting"** — HCL without descriptions or READMEs works only for its author.
2. **Stale Environment Matrices** — Updated only at major releases; fiction within two weeks.
3. **Wiki-Based Runbooks** — Unversioned, unreviewed, disconnected from actual pipelines.
4. **Secrets in Documentation** — Connection strings or keys in any document, even "internal" ones.

## My Position for the Docstitution

Terraform files ARE documentation—but not ENOUGH documentation. The Docstitution must recognize IaC as a primary documentation artifact while mandating supplementary context. Every module needs a README with purpose and examples. Every variable needs a description. The code documents "what"; we must also capture "why" and "for whom."

The Docstitution should mandate living environment documentation generated from actual infrastructure state. An agent deploying to staging needs to query current state, not parse a markdown table from three sprints ago. Deployment docs must be simultaneously human-readable under stress and agent-executable for automation—a structured runbook format with explicit steps, decision points, and rollback procedures.
