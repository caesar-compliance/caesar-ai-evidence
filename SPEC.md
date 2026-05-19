# Product Specification — caesar-ai-evidence

---

## 🎯 Purpose & Vision

**`caesar-ai-evidence`** provides a standardized, machine-readable data format and compliance validation framework for AI governance. The repository establishes a single source of truth for the schemas, data models, validation CLI, and documentation reports used across the **Caesar AI Governance Hub** ecosystem.

The ultimate vision is to facilitate the compilation of verifiable, cryptographic compliance evidence records that help organizations map their codebases, supplier profiles, and runtime models to established governance controls.

---

## ⚠️ The Problem

AI regulations (such as the EU AI Act, NIST AI RMF, and ISO/IEC 42001) require organizations to maintain extensive documentation, risk registers, and operational evidence files. 

Currently, organizations face several severe challenges:
1. **Fragmented Proofs:** Compliance evidence is scattered across disparate formats (PDFs, wiki pages, emails, Excel sheets, and log files).
2. **Untracked Telemetry:** Automated tools (scanners, ledgers, and scrapers) lack a shared, machine-readable syntax to serialize and export their outputs.
3. **High Audit Friction:** Compliance officers and external auditors must manually review chaotic files, making continuous audit-ready workflows nearly impossible.

---

## 👥 Target Users

* **AI Compliance Consultants & Auditors:** Require structured, verifiable, and exportable datasets to review during audit cycles.
* **Corporate Compliance & Risk Officers:** Need a continuous, consolidated registry of AI system risks, supplier postures, and control mappings.
* **DevOps & ML Engineers:** Need standardized programmatic interfaces to auto-generate evidence records straight from training pipelines, codebase commits, and CI/CD runs.

---

## 🗺️ Scope & Boundaries

### 🟢 MVP Scope (Planned)

1. **Ecosystem Schema Families:** Ten distinct JSON Schema definitions (Draft 2020-12) to model core governance layers:
   * **AI System Record:** Metadata, classification (e.g., high-risk, GPAI), and ownership.
   * **Vendor Record:** Third-party vendor identity, safety certifications, and contact registers.
   * **Risk Record:** Identified AI failures, impact assessments, and status tracking.
   * **Control Record:** Strategic defenses, technical measures, and mapping relations.
   * **Evidence Item:** Concrete documents, test results, code scanner logs, or ledger records.
   * **Evidence Pack:** Standardized wrapper to compile multiple evidence items, signatures, and schemas.
   * **Agent Run:** Telemetry from autonomous agent execution logs and tool-call actions.
   * **Vendor Change:** Audit logs noting supplier software updates or vendor changes.
   * **Regulation Change:** Upstream updates in regulatory texts (AI Act, NIST thresholds).
   * **Incident-Control Map:** Bidirectional logs mapping actual failures directly to controls.
2. **Verification CLI:** A command-line utility to syntactically parse, validate, and verify evidence packets.
3. **HTML/Markdown Report Generator:** A formatting engine that compiles complex JSON evidence packs into polished, human-readable compliance summaries.

### 🟡 Future Scope (Planned)

* **Evidence Center Integration:** Direct streaming ingestion into the enterprise Caesar AI Governance OS SaaS dashboard.
* **Cryptographic Ledger Integrity:** Full digital signature validation chain verification supporting hardware secure enclaves.
* **Cross-Language Struct Exports:** Automatic compilation of TypeScript interfaces, Python dataclasses, and Rust structures from the source JSON schemas.

### 🔴 Non-Goals (Out of Scope)

* **Legal Compliance Guarantees:** This tool **supports** evidence aggregation and verification, but it **does not** legal-clear any system or guarantee regulatory pass results.
* **Automated Remediation:** The framework documents and alerts on evidence gaps, but it does not modify codebase parameters, ML models, or operational risk registers.
* **Continuous Policy Scraping:** External scraping of raw regulatory web portals is handled by upstream tools (e.g., `caesar-ai-regulation-watch`), not this registry format.

---

## 📥 Expected Inputs & Outputs 📤

```
   INPUTS (Telemetry & Logs)                   PROCESS                    OUTPUTS (Reports & Packs)
┌──────────────────────────────┐       ┌───────────────────────┐       ┌──────────────────────────────┐
│  AI System & Risk JSONs      ├──────►│                       ├──────►│  Validated JSON Evidence Pack│
├──────────────────────────────┤       │  caesar-ai-evidence   │       ├──────────────────────────────┤
│  Scanner & Vendor Logs       ├──────►│  Validation Engine &  ├──────►│  Polished Markdown Summary   │
├──────────────────────────────┤       │  CLI Compiler         │       ├──────────────────────────────┤
│  Cryptographic Signatures    ├──────►│                       ├──────►│  Structured HTML Audit Book  │
└──────────────────────────────┘       └───────────────────────┘       └──────────────────────────────┘
```

### Expected Inputs
* **System Definitions:** Raw JSON files detailing ML model parameters, datasets, and risks conforming to raw schemas.
* **Scanner Outputs:** JSON outputs emitted by code scanners (`caesar-ai-scan`) or scrapers (`caesar-ai-vendor-watch`).
* **Audit Ledgers:** Telemetry records from agent ledger runs (`caesar-ai-agent-ledger`).
* **Public Signatures:** Cryptographic public-key identifiers confirming the source of evidence files.

### Expected Outputs
* **Ecosystem Evidence Pack:** A validated, consolidated JSON packet (`.evidence.json`) containing all linked assets, signatures, and schemas.
* **Compliance Reports:** Highly formatted Markdown files (`.md`) and static HTML documents (`.html`) presenting tabular overviews of risks, controls, systems, and evidence item presence.

---

## ⚙️ Planned CLI Command Specification

The planned CLI command surface of the validation utility:

### 1. `caesar-evidence validate`
Validates a specific evidence JSON file, schema, or compiled Evidence Pack.
```bash
# Validate an individual evidence item against its specific schema
caesar-evidence validate --schema schemas/ai-system.schema.json examples/simple-ai-system/ai-system.json

# Validate a full consolidated Evidence Pack
caesar-evidence validate --pack examples/evidence-packs/sample-pack.evidence.json
```

### 2. `caesar-evidence compile`
Assembles multiple raw JSON files and telemetry signatures into a single portable Evidence Pack.
```bash
caesar-evidence compile \
  --system examples/simple-ai-system/ai-system.json \
  --risks examples/simple-ai-system/risks.json \
  --controls examples/simple-ai-system/controls.json \
  --out build/system-release-v1.evidence.json
```

### 3. `caesar-evidence report`
Compiles an Evidence Pack into professional Markdown or interactive HTML audit books.
```bash
# Generate Markdown report
caesar-evidence report --pack build/system-release-v1.evidence.json --format markdown --out build/report.md

# Generate HTML report
caesar-evidence report --pack build/system-release-v1.evidence.json --format html --out build/report.html
```

---

## 📂 Planned Schema Families

Every schema will adhere strictly to JSON Schema Draft 2020-12 and will be stored under `/schemas/`:

| Schema Name | Target file | Primary Fields |
| :--- | :--- | :--- |
| **`ai-system`** | `ai-system.schema.json` | System ID, classification tier, model details, datasets, ownership, deployment state. |
| **`vendor`** | `vendor.schema.json` | Vendor ID, supplier name, self-assessments, data access rules, certifications. |
| **`risk`** | `risk.schema.json` | Risk ID, category, likelihood, severity, impact description, status. |
| **`control`** | `control.schema.json` | Control ID, title, description, category (technical, administrative, physical). |
| **`evidence-item`** | `evidence-item.schema.json` | Evidence ID, timestamp, tool name, proof type, raw payload hash, source path. |
| **`evidence-pack`** | `evidence-pack.schema.json` | Pack ID, target system, compiled evidence item list, cryptographic signatures, schema references. |
| **`agent-run`** | `agent-run.schema.json` | Run ID, agent name, task goal, tool calls registry, approvals, token count. |
| **`vendor-change`** | `vendor-change.schema.json` | Event ID, target vendor, update timestamp, change details, risk delta. |
| **`regulation-change`** | `regulation-change.schema.json` | Change ID, regulator, text updated, target clauses, compliance gap analysis. |
| **`incident-mapping`** | `incident-mapping.schema.json` | Mapping ID, actual failure mode, target systems affected, mitigation controls triggered. |

---

## 📄 Planned Report Formats

* **Executive Summary:** High-level dashboard-style layout indicating percentage of completed evidence controls, open risk items, and audit-ready status.
* **Control Compliance Matrix:** Tabular listing mapping every documented risk to its defensive controls and the precise evidence item validating its operational efficiency.
* **Cryptographic Verification Trail:** A detailed listing of the validator tools, versions, execution times, and digital signatures proving data integrity.
