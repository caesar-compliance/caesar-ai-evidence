# Repository Inventory — caesar-ai-evidence

This is a living registry of all files currently tracked in the `caesar-ai-evidence` repository. It provides developers and automated agents with a reference mapping each file to its exact role in the codebase structure.

---

## 📂 File Directory

| File Path | Primary Role | Description |
| :--- | :--- | :--- |
| 🛡️ **`README.md`** | Main Introduction | Summarizes the project vision, functional workflows, target audience, ecosystem alignment with [caesar-ai-governance-hub](https://github.com/caesar-compliance/caesar-ai-governance-hub), and legal disclaimers. |
| 📋 **`SPEC.md`** | Technical Specification | Defines core MVP scope, inputs, outputs, planned CLI validate/compile/report commands, JSON schemas taxonomy, and report layouts. |
| 🏗️ **`ARCHITECTURE.md`** | System Architecture | Visualizes ecosystem interactions, outlines the core directory structure, and maps schema inheritance and relational dependencies. |
| 🚦 **`ROADMAP.md`** | Project Roadmap | Lists six development phases transitioning the evidence engine from planning stages through stable public release. |
| 📝 **`CHANGELOG.md`** | Historical Log | Contains a semver-compliant, chronological history of all updates and releases. |
| 🗃️ **`REPO_INVENTORY.md`** | Workspace Registry | This file; provides a continuous, machine-readable index mapping files to functional roles. |
| 🔬 **`docs/RESEARCH_CONTEXT.md`** | Domain Research | Ingests foundational strategic requirements, user personas, and target scopes compiled from the ecosystem import packs. |
| 📊 **`docs/SCHEMA_OVERVIEW.md`** | Schema Overview | Technical manual mapping out the ten JSON schema structures and relational dependencies. |
| 📐 **`schemas/ai-system.schema.json`** | AI System Schema | JSON Schema defining governance classification, ownership, and metadata structures for AI systems. |
| 📐 **`schemas/vendor.schema.json`** | Vendor Schema | JSON Schema defining third-party supplier profiles, data access policies, and security certifications. |
| 📐 **`schemas/risk.schema.json`** | Risk Schema | JSON Schema defining identified operational threat levels, severity/likelihood indexes, and mitigation links. |
| 📐 **`schemas/control.schema.json`** | Control Schema | JSON Schema defining operational or technical defensive measures mapped to mitigate risks. |
| 📐 **`schemas/evidence-item.schema.json`** | Evidence Item Schema | JSON Schema defining concrete telemetry proofs, scanning outputs, or manual checklists validating controls. |
| 📐 **`schemas/evidence-pack.schema.json`** | Evidence Pack Schema | JSON Schema for the master portfolio aggregating all systems, risks, controls, evidence, and events. |
| 📐 **`schemas/agent-run.schema.json`** | Agent Run Schema | JSON Schema logging autonomous agent runtime executions, tool calls, and approvals. |
| 📐 **`schemas/vendor-change.schema.json`** | Vendor Change Schema | JSON Schema tracking changes in vendor privacy frameworks, API endpoints, or safety profiles. |
| 📐 **`schemas/regulation-change.schema.json`** | Regulation Change Schema | JSON Schema tracking upstream policy updates, new compliance guidelines, or clauses. |
| 📐 **`schemas/incident-mapping.schema.json`** | Incident Mapping Schema | JSON Schema mapping operational failures or threat vulnerabilities to failing control references. |

---

## 🛠️ Update Guidelines

When modifying this repository:
1. Ensure any new architectural specs or schemas are correctly documented inside `SPEC.md`.
2. Add any newly introduced folders or core file assets to this registry table.
3. Update `CHANGELOG.md` reflecting the appropriate semver version bump.
