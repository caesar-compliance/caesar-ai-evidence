# Changelog

All notable changes to the Caesar AI Evidence project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [0.2.1] - 19 May 2026

### Changed
- **Schema Wording & Refinements:** Cleaned schema wording and documentation before v0.3 examples, replacing absolute guarantees and sentient agent wording with operational event timelines, tool calls, and approvals.

## [0.2.0] - 19 May 2026

### Added
- **v0.2 Draft JSON Schemas:** Added ten core draft schemas conforming to JSON Schema Draft 2020-12 in `/schemas/`:
  - `ai-system.schema.json` (AI System Record)
  - `vendor.schema.json` (Vendor Record)
  - `risk.schema.json` (Risk Record)
  - `control.schema.json` (Control Record)
  - `evidence-item.schema.json` (Evidence Item)
  - `evidence-pack.schema.json` (Evidence Pack aggregator)
  - `agent-run.schema.json` (Agent Run Record)
  - `vendor-change.schema.json` (Vendor Change Record)
  - `regulation-change.schema.json` (Regulation Change Record)
  - `incident-mapping.schema.json` (Incident Mapping Record)
- **Schema Overview Documentation:** Added [docs/SCHEMA_OVERVIEW.md](docs/SCHEMA_OVERVIEW.md) mapping core entities, relational reference layouts, and planned utility bindings.
- **Architectural Updates:** Integrated v0.2 active status definitions in [README.md](README.md), [ARCHITECTURE.md](ARCHITECTURE.md), and [ROADMAP.md](ROADMAP.md).

## [0.1.0] - 19 May 2026

### Added
- **Ecosystem Core Foundation:** Initialized the `caesar-ai-evidence` repository structure and established key architectural planning documents.
- **Product Specification:** Created [SPEC.md](SPEC.md) detailing the MVP CLI validator command specs, planned reporting output formats, and raw inputs structure.
- **System Architecture Guide:** Added [ARCHITECTURE.md](ARCHITECTURE.md) documenting core data flows, folder layouts, and relational schema dependencies.
- **Development Roadmap:** Created [ROADMAP.md](ROADMAP.md) detailing the six core milestones transitioning the library to a stable release format.
- **Workspace Register:** Created [REPO_INVENTORY.md](REPO_INVENTORY.md) listing the functional roles of all files initialized in this directory.
