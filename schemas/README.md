# Schemas README

This folder contains permissive, base JSON schemas for Topical Graph Architect (TGA).

Purpose
- Provide an interoperable top-level contract for LLM-driven workflows.
- Validate the input envelope (requested_mode, main_topic, language, site_type, vertical_profile, etc.).

Limitations
- These schemas do NOT exhaustively validate every nested module contract (entity_resolution, page_architecture, decision_ledger, SSoT records). They are intentionally permissive to avoid frequent breaking changes when the spec evolves.

Recommended next steps
- Provide `*.strict.json` schemas for automated CI validation if your consumers require strong guarantees.
- Adopt `additionalProperties: false` only in strict schemas and use migration adapters for backward compatibility.

