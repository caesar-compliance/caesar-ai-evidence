# Caesar AI Evidence Schema Overview (v0.2 Draft)

This document provides a technical overview of the ten draft JSON Schemas implemented inside the `schemas/` directory. All schemas conform strictly to the **JSON Schema Draft 2020-12** standard.

---

## 📂 The Schema Catalog

| Schema File Name | Conceptual Entity | Primary Purpose |
| :--- | :--- | :--- |
| **`ai-system.schema.json`** | **AI System** | Tracks root metadata, risk classification, model parameters, and lifecycle states of individual systems. |
| **`vendor.schema.json`** | **Vendor / Supplier** | Records third-party supplier profiles, data privacy parameters, and certification statuses (e.g. ISO 27001). |
| **`risk.schema.json`** | **Risk Assessment** | Identifies potential AI operational threat levels, severity/likelihood indices, and mitigation states. |
| **`control.schema.json`** | **Defensive Control** | Details administrative policies or technical guardrails implemented to mitigate risks. |
| **`evidence-item.schema.json`** | **Evidence Proof** | Captures concrete telemetry, static codebase scan results, manual audit checklist logs, or test cases. |
| **`evidence-pack.schema.json`** | **Evidence Pack** | Serves as the master aggregated portfolio, binding systems, risks, controls, evidence, and event trails together. |
| **`agent-run.schema.json`** | **Agent Runtime Log** | Logs telemetry traces, tool invocations, logic decisions, and token expenses of autonomous agent cycles. |
| **`vendor-change.schema.json`** | **Supplier Shift Log** | Tracks changes in vendor privacy agreements, API deprecations, or security postures. |
| **`regulation-change.schema.json`** | **Policy Shift Log** | Notes modifications or enforcement updates in upstream guidelines (e.g. EU AI Act clauses). |
| **`incident-mapping.schema.json`** | **Failure Mode Log** | Documents active system incidents or vulnerabilities mapped directly to failed control IDs. |

---

## 🔄 Schema Connectivity Model

The schemas form an audit trail enabling complete relational tracing. The `evidence-pack` operates as a root aggregator containing collections of all other schema entities:

```
                          ┌───────────────────────────┐
                          │    evidence-pack (Root)   │
                          └─────────────┬─────────────┘
                                        │
             ┌──────────────────────────┼──────────────────────────┐
             ▼                          ▼                          ▼
 ┌──────────────────────┐   ┌──────────────────────┐   ┌───────────────────────┐
 │      ai-system       │   │        vendor        │   │   regulation-change   │
 └───────────┬──────────┘   └───────────┬──────────┘   └───────────┬───────────┘
             │ (1:N)                    │ (1:N)                    │ (1:N)
 ┌───────────▼──────────┐   ┌───────────▼──────────┐   ┌───────────▼───────────┐
 │         risk         │   │    vendor-change     │   │   affected_controls   │
 └───────────┬──────────┘   └──────────────────────┘   └───────────────────────┘
             │ (M:N)
 ┌───────────▼──────────┐
 │       control        │◄─────── [incident-mapping] (bypassed controls link)
 └───────────┬──────────┘
             │ (1:N)
 ┌───────────▼──────────┐
 │    evidence-item     ◄──────── [agent-run] (validating runtime logs)
 └──────────────────────┘
```

---

## 🛠️ How Future Tools Will Utilize Schemas

1. **Continuous Auditing & CI/CD Scanners (`caesar-ai-scan`):** Emits `evidence-item` logs containing code scans, file analyses, and dependencies list. These items validate linked `control` nodes.
2. **Third-Party Monitors (`caesar-ai-vendor-watch`):** Regularly checks SaaS vendors, emitting `vendor-change` notifications when privacy policies or endpoints update.
3. **Autonomous Agents (`caesar-ai-agent-ledger`):** Programmatically posts `agent-run` telemetry detailing runtime actions and token counts into active `evidence-item` logs.
4. **Validation CLI (`caesar-evidence`):** Validates raw files or compiled portfolios against these schemas during delivery gates to block invalid or incomplete audit books.
5. **Dashboard Ingestion (`caesar-ai-governance-os`):** Consumes `evidence-pack` files to parse system statuses, risk mitigation rates, and supplier postures cleanly.
