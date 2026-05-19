# Product Roadmap — caesar-ai-evidence

---

## 🚦 Roadmap Summary

The development of **`caesar-ai-evidence`** is split into six strategic phases to ensure that the core data schemas are robust, validated, and thoroughly tested before releasing the final stable evidence framework version.

```
  v0.1              v0.2             v0.3             v0.4             v0.5             v1.0
┌───────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│ Documentation │ │ JSON Schema  │ │ Example      │ │ CLI Validate │ │ Markdown/HTML│ │ Stable       │
│ & Model Plan  │ │ Draft        │ │ Packs        │ │ Prototype    │ │ Report Gen   │ │ Release      │
└───────┬───────┘ └──────┬───────┘ └──────┬───────┘ └──────┬───────┘ └──────┬───────┘ └──────┬───────┘
        ▼                ▼                ▼                ▼                ▼                ▼
     Active          Planned          Planned          Planned          Planned          Planned
```

---

## 🗺️ Phased Milestones

### 🟢 Phase v0.1 — Documentation & Evidence Model Planning (Active)
* **Goal:** Initialize repository guidelines, core specs, and architectural structures to map out relational schema models.
* **Deliverables:**
  * [x] Ecosystem integration mapping (`docs/RESEARCH_CONTEXT.md`).
  * [x] Basic repository documentation ([README.md](README.md), [REPO_INVENTORY.md](REPO_INVENTORY.md)).
  * [x] Product Specifications ([SPEC.md](SPEC.md)) defining MVP CLI scope.
  * [x] System Architecture map ([ARCHITECTURE.md](ARCHITECTURE.md)) outlining directory conventions.
* **Completion Date:** 19 May 2026

---

### 🟡 Phase v0.2 — JSON Schema Draft (Planned)
* **Goal:** Draft the core ten JSON Schema files under `/schemas/` conforming to JSON Schema Draft 2020-12 rules.
* **Deliverables:**
  * [ ] Draft initial `ai-system.schema.json` and `vendor.schema.json`.
  * [ ] Construct threat-model maps in `risk.schema.json` and `control.schema.json`.
  * [ ] Draft execution telemetry models for `evidence-item.schema.json` and `evidence-pack.schema.json`.
  * [ ] Define automated scraper schemas in `vendor-change.schema.json`, `regulation-change.schema.json`, `agent-run.schema.json`, and `incident-mapping.schema.json`.

---

### 🟡 Phase v0.3 — Example Evidence Packs (Planned)
* **Goal:** Construct fully populated example payloads in `/examples/` to verify that the draft schemas can successfully capture real-world ML engineering and vendor metadata.
* **Deliverables:**
  * [ ] Simple AI System registry payload with mapped risks and technical controls.
  * [ ] Supplier assessment and data governance profile logs.
  * [ ] Autonomous agent telemetry traces documenting decision thresholds.
  * [ ] Simulated regulation-change trigger illustrating upstream drift tracking.

---

### 🟡 Phase v0.4 — CLI Validation Prototype (Planned)
* **Goal:** Build a lightweight, zero-dependency command-line validation utility (`caesar-evidence validate`) utilizing standard Python `jsonschema` binding logic.
* **Deliverables:**
  * [ ] Set up modern package hooks inside `/src/`.
  * [ ] Implement `caesar-evidence validate` command to verify local files against the schemas.
  * [ ] Write unit tests asserting that schema validation throws correct structural violations.

---

### 🟡 Phase v0.5 — Markdown / HTML Report Generator (Planned)
* **Goal:** Implement the reporting compiler (`caesar-evidence report`) generating clean human-readable Markdown and static HTML documents.
* **Deliverables:**
  * [ ] Build Markdown templating scripts compiling risks and control registers into flat matrices.
  * [ ] Implement Jinja2 HTML report generator generating responsive, CSS-styled audit reports.
  * [ ] Integrate evidence verification hashes and verification signature visual cards in HTML documents.

---

### 🟡 Phase v1.0 — Stable Evidence Format (Planned)
* **Goal:** Finalize schemas, freeze CLI options, and ship stable v1.0.0 package binaries.
* **Deliverables:**
  * [ ] Finalize code cleanup, remove experimental schema features.
  * [ ] Lock schema definitions for enterprise production imports.
  * [ ] Publish library modules to official registers.
