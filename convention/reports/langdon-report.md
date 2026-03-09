# Delegate Report: Langdon
**Role:** Cloud Engineer | **Experience:** 13 years | **Perspective:** Balanced

## Essential Document Types

**Service Catalogs:** Registries of every cloud service with ownership, purpose, cost center, and dependencies.
**Cost Allocation Documentation:** Cloud spending breakdowns by team, service, environment, and project.
**Cloud Security Documentation:** Continuously updated records of IAM policies, network boundaries, and compliance postures.
**Multi-Cloud Architecture Docs:** Workload placement rationale, cross-cloud dependencies, and provider constraints.
**Resource Tagging Standards:** Required tags, naming conventions, and enforcement mechanisms.
**DR Architecture Docs:** Cloud-specific disaster recovery covering region failover and data replication.

## Documents Most Critical to My Role

**1. Service Catalogs**
Every service with owner, cost center, dependencies, SLA tier, and decommission criteria. Consulted daily for resource management and incident response. Unregistered resources cost money with zero accountability. My rule: undocumented cloud resources get deleted. Agents auto-discover from APIs; humans provide business context.

**2. Cost Allocation Documentation**
Per-service, per-team breakdowns with anomaly flags and optimization recommendations. Without it, bills grow unchecked and "what does this cost?" is unanswerable. Agents generate from billing APIs; humans interpret business implications.

**3. Cloud Security Documentation**
IAM inventories, security group rules, encryption configs, compliance results. Undocumented security creates invisible attack surfaces. Agents scan against baselines generating drift reports; humans define policies and review exceptions.

**4. Resource Tagging Standards**
Tag taxonomy, validation rules, enforcement, remediation. Without standards, cost allocation breaks and ownership is untraceable. Must be machine-readable so agents validate at provisioning time.

**5. Multi-Cloud Architecture Documentation**
Placement rationale, provider mappings, data residency constraints, exit strategies. Undocumented multi-cloud becomes accidental lock-in with duplicated costs. Agents map resources across providers; humans document strategic rationale.

## Human-Agent Documentation Considerations

- Service catalogs must be continuously synced with cloud resources through agent discovery. Unregistered resources trigger automated workflows with human ownership assignment.
- Cost docs should be agent-generated from billing APIs; humans annotate only business context about expected vs. anomalous spending.
- Security docs must support real-time agent validation comparing baselines against actual configs faster than manual audits.

## Documentation Anti-Patterns

1. **The Invisible Resource:** Cloud resources without catalog registration — costing money, nobody accountable.
2. **The Surprise Bill:** No cost documentation until finance escalates month-end overages.
3. **The Point-in-Time Security Doc:** Written once, never updated as configs drift. Compliance theater.
4. **The Single-Cloud Assumption:** Documenting as if one provider exists, ignoring multi-cloud reality.

## My Position for the Docstitution

My first question about every cloud resource: "what does this cost?" The Docstitution must ensure that is always answerable. Cloud provisioning is frictionless but costs compound silently. Every resource must be in a service catalog with ownership and justification. Undocumented cloud resources get deleted.

Cloud security docs cannot be point-in-time artifacts. Configs drift daily. The Docstitution must require continuous documentation validated by agents against actual state. A security doc accurate last quarter is dangerous fiction this quarter.

Service catalogs are the foundational cloud document. Cost, security, and DR docs all reference catalog entries. Without the catalog, every other cloud doc is incomplete. With agents maintaining freshness from APIs, the Docstitution ensures cloud docs reflect reality — not the wiki from six months ago.
