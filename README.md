# Topical Graph Architect (TGA) v4.0.9

> Current stable version: v4.0.9
>
> - Russian specification: [SPECIFICATION.md](./SPECIFICATION.md)
> - English specification: [SPECIFICATION-en.md](./SPECIFICATION-en.md)
> - English copy (convenience name): [Topical-Graph-Architect-v-4-0-9.md](./Topical-Graph-Architect-v-4-0-9.md)
> - Changelog: [CHANGELOG.md](./CHANGELOG.md)

**Topical Graph Architect** — an architectural framework for SEO, content and product teams. It helps design not just a set of URLs, but a governed map of entities, user jobs, evidence and navigation flows.

```text
entity-first + intent-first + graph-first + evidence-led + consistency-first
```

## Quick start

1. Read the canonical specification: Russian: `SPECIFICATION.md`, English: `SPECIFICATION-en.md`.
2. Choose a mode: `quick_assessment`, `full_cocoon_design`, `cocoon_audit` or `latent_intent_research`.
3. Copy a matching example from `examples/` and adapt it.
4. Supply the example to your LLM or agent, together with the relevant system prompt from `spec/prompts/`.
5. Review `assumptions`, `manual_review_items`, and `release_readiness` in the produced output.

## Documentation

| Document | Description |
| --- | --- |
| [SPECIFICATION.md](./SPECIFICATION.md) | Canonical (Russian) TGA specification (v4.0.8 original) |
| [SPECIFICATION-en.md](./SPECIFICATION-en.md) | English edition (v4.0.9, editorial translation) |
| [Topical-Graph-Architect-v-4-0-9.md](./Topical-Graph-Architect-v-4-0-9.md) | Convenience filename copy of the English spec |
| [examples/](./examples) | Example input payloads by mode |
| [schemas/](./schemas) | Interoperability schemas (permissive base schemas; see `schemas/README.md`) |
| [templates/](./templates) | Editorial and technical templates |
| [tests/regression-suite.md](./tests/regression-suite.md) | Regression scenarios to validate behaviour |
| [CHANGELOG.md](./CHANGELOG.md) | Version history |

## Notes about schemas

Current schemas are intentionally permissive. They validate the top-level envelope and are suitable for interoperability with LLM-driven systems. They do not (yet) enforce every nested module contract (entity_resolution, detailed page schema, decision ledger etc.). See `schemas/README.md` for details and recommended next steps if you need strict validation.

## License

MIT — see [LICENSE](./LICENSE)

## Contributing

Please open issues or PRs for editorial updates, schema improvements, or test additions. For release discipline, follow semantic versioning and update `CHANGELOG.md` when making behaviour changes.

---

(If you prefer to keep `v4.0.8` as the canonical release and treat the English edition as a translation-only artifact, tell me and I will adjust headings to `v4.0.8 (English translation)`).
