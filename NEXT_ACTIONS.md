# Next Actions — caesar-ai-evidence

This document prioritizes upcoming development tasks and establishes execution boundaries for autonomous agents in the `caesar-ai-evidence` repository.

---

## 🚦 Execution Boundaries

### 1. Prioritized Next Steps
*   **v0.3 Example Evidence Packs:** Generate JSON/JSONL sample evidence packages conforming to the Draft 2020-12 schemas.

### 2. Safe Autonomous Tasks
*   Adding comprehensive markdown comments and documentation to existing JSON schemas.
*   Improving code formatting and compliance with the `standards/` style guides.
*   Scaffolding basic unit tests or validation scripts for schemas.

### 3. Tasks Requiring Control Tower (Artem / ChatGPT) Approval
*   Modifying any core JSON schema fields, constraints, or relational references in `schemas/`.
*   Adding third-party schema validators or dependency libraries.
*   Changing public-facing API signatures.

### 4. Blocked Tasks
*   None currently.

### 5. Cross-Repository Coordination Notes
*   Any changes made to schemas in `caesar-ai-evidence` must be immediately propagated to the dependent child repositories (`caesar-ai-scan`, `caesar-ai-agent-ledger`, etc.) and verified against the Central Hub.
