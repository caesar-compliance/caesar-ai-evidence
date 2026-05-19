# Caesar AI Evidence (`caesar-ai-evidence`)

> Core repository for the shared, verifiable AI compliance evidence format within the [Caesar AI Governance Hub](https://github.com/caesar-compliance/caesar-ai-governance-hub) ecosystem.

---

## 📖 Overview

**`caesar-ai-evidence`** defines the standardized schemas, data formats, and structural models that secure, validate, and report compliance telemetry across the Caesar ecosystem. Designed for modern machine learning lifecycles and software auditing processes, it enables legal, engineering, and security stakeholders to map their AI operational states directly to verification logs.

By establishing a unified evidence format, this library supports the ingestion and processing pipelines of all other tools in the ecosystem at [caesar.no](https://caesar.no).

### 🚦 Project Status
> [!NOTE]
> This repository is currently in its **planning and foundation stage**. It contains initial specifications, architectural diagrams, and roadmap documentation. Active schema implementation and tool-building are slated for future development phases.

---

## 👥 Who It Is For

* **AI Compliance Consultants & Auditors:** To compile structured and standardized audits that can be read, mapped, and parsed electronically.
* **Compliance & Legal Operations Teams:** To establish a clear, structured system of record tracking risk registers, vendor postures, and control mappings.
* **AI Developers & ML Engineers:** To programmatically export automated evidence telemetry directly from model training pipelines and continuous integration (CI) workflows.
* **SMEs & Suppliers:** To provide transparent, schema-validated vendor safety metrics to enterprise procurers.

---

## 🛠️ How It Is Used

1. **Defining Governance Schemas:** Implements rigid JSON schemas for AI system records, vendor details, risks, control maps, and runtime execution telemetry.
2. **Aggregating Evidence Packs:** Provides a framework to compile multiple evidence records, cryptographic signatures, and scanner logs into a unified, portable archive ("Evidence Pack").
3. **Validating Telemetry:** Empowers teams to validate compliance telemetry against ecosystem schemas via a planned command-line interface (CLI) tool.
4. **Generating Human-Readable Reports:** Compiles complex JSON evidence archives directly into highly readable Markdown and HTML summary reports for management and external auditors.

---

## 🔗 Ecosystem Connection

`caesar-ai-evidence` serves as the foundational data contract of the **Caesar AI Governance Hub** ecosystem:

* **Inbound Telemetry:** Code scanners (`caesar-ai-scan`), suppliers watchers (`caesar-ai-vendor-watch`), and runtime agent monitors (`caesar-ai-agent-ledger`) produce logs conforming directly to the schemas established in this repository.
* **Outbound Processing:** The enterprise SaaS dashboard (`caesar-ai-governance-os`) consumes these schemas to ingest, parse, and visualizes evidence packets safely.

```
┌────────────────────────────────────────────────────────┐
│               Caesar AI Governance Hub                 │
└──────────────────────────┬─────────────────────────────┘
                           ▼
 ┌──────────────────────────────────────────────────────┐
 │             caesar-ai-evidence (Schemas)             │
 └─────────────────────────┬────────────────────────────┘
         ▲                 ▲                 ▲
         │                 │                 │
┌────────┴───────┐ ┌───────┴───────┐ ┌───────┴──────────┐
│ caesar-ai-scan │ │  vendor-watch │ │  agent-ledger    │
└────────────────┘ └───────────────┘ └──────────────────┘
```

## 📐 Current Schema Draft (v0.2)

This repository includes the initial draft JSON Schemas conforming to JSON Schema Draft 2020-12:

*   **[schemas/](schemas/)** — Directory containing the 10 core JSON Schema files.
*   **[docs/SCHEMA_OVERVIEW.md](docs/SCHEMA_OVERVIEW.md)** — Architectural reference and connectivity map explaining each schema and relational dependencies.

---

## ⚖️ Important Disclaimer

> [!IMPORTANT]
> **No Compliance Guarantees:** `caesar-ai-evidence` is a technical tool that supports capturing, structuring, validating, and reporting AI system configurations, risk mappings, and evidence telemetry. It **does not guarantee regulatory compliance**, legal clearance, or audit approvals. Regulatory compliance remains a holistic legal, operational, and organizational state determined by accredited auditors, legal experts, and competent authorities.

---

## 📂 Repository Directory

* **[SPEC.md](SPEC.md)** — Architectural, schema, and command-line specifications.
* **[ARCHITECTURE.md](ARCHITECTURE.md)** — Core data flow, validation layer, and folder organization rules.
* **[ROADMAP.md](ROADMAP.md)** — Project development roadmap and backlogs.
* **[CHANGELOG.md](CHANGELOG.md)** — Chronological release history.
* **[REPO_INVENTORY.md](REPO_INVENTORY.md)** — Structural file index of this codebase.
* **[docs/SCHEMA_OVERVIEW.md](docs/SCHEMA_OVERVIEW.md)** — Architectural reference and connectivity map explaining the v0.2 schemas.
* **[docs/RESEARCH_CONTEXT.md](docs/RESEARCH_CONTEXT.md)** — Functional domain research and background metadata.
