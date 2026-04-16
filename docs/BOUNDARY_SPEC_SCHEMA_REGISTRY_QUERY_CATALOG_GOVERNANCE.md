# Boundary Specification: Approved Schema Registry and Query Catalog Governance

## Scope and Stage

- Work item: approved schema registry and query catalog governance
- Delivery stage: Boundary Specification
- Parent issue: waw2637/IOTServer.Insights.Database#1
- Primary design reference: `docs/DB_REPO_ARCHITECTURE.md`
- Lifecycle reference: `IOTServer.Insights.Contracts/docs/DELIVERY_PLAN.md`

This artifact documents boundary-stage outputs only. It does not authorize execution work.

## Upstream Gates and Boundary Decision

- [x] Database repository role and boundaries are defined in `docs/DB_REPO_ARCHITECTURE.md`
- [x] Model registry minimum standard exists in `docs/MODEL_REGISTRY_SPEC.md`
- [x] Query catalog minimum standard exists in `docs/QUERY_CATALOG_SPEC.md`
- [x] Schema review governance baseline exists in `docs/SCHEMA_CHANGE_REVIEW_CHECKLIST.md`

Boundary decision: proceed to next stage with governance scope constrained to approved schema registry and important query catalog controls described in the existing specifications.

## Stage Outputs (Reviewable)

1. **Governance boundary confirmed**
   - Repository remains the canonical source for approved models, schema artifacts, and important query catalog entries.
   - Service DTOs, UI models, and business logic remain out of scope for this repo.

2. **Required documentation controls confirmed**
   - Schema proposals must cite the current approved model entry.
   - Material query changes must include purpose, ownership, cost impact, schema assumptions, and blast radius reasoning.
   - Human review remains required before schema/important query changes are considered complete.

3. **Cross-repo usage boundary confirmed**
   - Other repos must reference this repo for schema changes, migrations, index/retention changes, and important query updates.

4. **Data ownership, protection, and historical continuity boundary confirmed**
   - Model registry entries must explicitly identify horizon-required data ownership boundaries (what must be retained in this repo-governed data model).
   - Governance scope includes documenting controls to avoid customer-detail leakage in schema/query artifacts (for example, restricted fields, minimization, and approved identifier usage).
   - Governance scope includes documenting permission boundaries for sensitive model/query access (who can read, propose changes, and approve).
   - Historical-data interoperability must preserve GUID-based lineage while allowing friendly-tag references via governed mapping so tag/connection changes do not orphan historical records.

## Dependency and Sequencing Notes

### Dependencies satisfied for this stage

- Architecture boundary definition (`docs/DB_REPO_ARCHITECTURE.md`)
- Model registry specification (`docs/MODEL_REGISTRY_SPEC.md`)
- Query catalog specification (`docs/QUERY_CATALOG_SPEC.md`)
- Schema change review checklist (`docs/SCHEMA_CHANGE_REVIEW_CHECKLIST.md`)

### Follow-on dependencies for later stages

- Human review approval of this boundary artifact
- Agent Delivery Planning to translate approved follow-on proposals into actual delivery tasks
- Repository structure additions (`schema/`, `query-catalog/`, related `docs/*`) when execution stage is authorized

## Proposed Follow-on Work (Not Execution-Approved Scope)

- Define canonical file/folder templates for approved model entries and query catalog entries.
- Define a lightweight governance checklist template for PRs touching schema or important queries.
- Propose drift-detection guardrails (for example, required metadata completeness checks) for future planning review.
- Propose ownership and review rotation metadata requirements for model/query records.
- Propose a sensitive-data classification and redaction convention for model and query metadata to reduce customer-detail leakage risk.
- Propose access-control metadata requirements (read/propose/approve roles) for governed schema and important query artifacts.
- Propose GUID-to-friendly-tag mapping governance for historical interoperability, including non-orphaning requirements across PLC tag and connection changes.

These are proposals only and are intentionally not converted into execution-ready tasks in this stage.

## Exit Criteria for Advancing Stage

- [x] Boundary-stage outputs are documented and reviewable in this artifact
- [x] Dependencies and follow-on work are explicit
- [x] No execution-ready tasks are created in this stage
- [x] Issue is ready for human review and next lifecycle stage decision
