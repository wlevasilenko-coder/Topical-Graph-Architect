# Topical Graph Architect — SPECIFICATION (v4.0.9, English translation)

This document is the English translation of Topical Graph Architect (TGA) v4.0.9. It preserves the full logic, module contracts, routing, and methodology from v4.0.8 and delivers editorial clarifications for international LLM-driven workflows.

---

Title block / Metadata

Name: Topical Graph Architect
Acronym: TGA
Version: 4.0.9
Status: Production-Ready Specification
Type: architectural skill / framework
Purpose: design, audit, growth and management of topical (semantic) cocoons
Core principle:
entity-first + intent-first + graph-first + evidence-led + consistency-first

## 0. Status and changelog

### 0.1 Status v4.0.9

Production-Ready Specification

TGA v4.0.9 is intended for:

- quick_assessment;
- full_cocoon_design;
- hypothesis_led_design;
- cocoon_audit;
- latent_intent_research;
- YMYL and regulated verticals with mandatory human review for legal, medical, financial, licensing and regulatory claims.

### 0.2 Changes vs v4.0.8

v4.0.9 preserves all mechanisms from v4.0.6..v4.0.8 and introduces editorial clarifications and wording improvements to reduce ambiguity when TGA is used in English and in LLM contexts. There are no changes to module responsibilities or outputs.

Notable additions/edits:
1. Editorial fixes and clarifications across readiness checklists and module contracts.
2. Improved wording for M07 ↔ M08 responsibilities to prevent misinterpretation of provisional vs formal clustering.
3. Clarified guidance for strict JSON validators and recommended compatibility patterns.
4. Minor wording clarifications for M22a baseline profiles for regulated verticals.
5. Processing order for latent-intent handling remains:
   M05 → M26a → M06 → M07 provisional aggregation → M08 formal clustering → M08 reconciliation → M09
6. All earlier corrections are retained (M17a/M17b; M23a/M23b; M25a/M25b; M26a/M26b; M13→M14→M18; feedback loops; role-specific linking; semantic relationship `tool`; standard routing by mode).

---

# 1. Mission and philosophy of TGA

## 1.1 What is a semantic cocoon 4.0

Classical cocoon model:

Pillar page → Child pages → Internal links

TGA model:

Semantic cocoon 4.0 =
- entity graph
- user-job map
- structural hierarchy
- user-transition scenarios
- evidence base
- trust/compliance layer
- SSoT (Single Source of Truth) for mutable facts
- rules for freshness/updates
- role-specific page quality baselines
- explainable decisions

A cocoon is not a list of URLs nor just a set of keywords. It is a governed system of answers to interconnected user jobs.

## 1.2 The key principle

"Each page should have a single structural home, but may have several semantic bridges."

Consequences:
- a page has exactly one `canonical_parent`;
- URLs and breadcrumbs reflect the single hierarchical membership;
- contextual links may connect independent cocoons;
- a bridge is not a second parent;
- header/footer/utility/compliance links are not thematic parent relations.

## 1.3 Core principles

### Entity-first

Architecture begins with entities:
products, services, brands, participants, audiences, documents, conditions, parameters, processes, constraints, risks, solutions, regulators, jurisdictions, evidence, scenarios

### Intent-first

A page is created for a standalone `user_job`, not just for query variations.

### Graph-first

Design the cocoon as a semantic graph layered on a comprehensible structural hierarchy.

### Evidence-led

Strong claims must have evidence. This is critical for finance, medical, legal, gambling and other regulated verticals.

### Consistency-first

Mutable facts must be consistent (prices, rates, limits, bonuses, wagering requirements, RTP, licenses, availability, eligibility, product terms, legal constraints).

### User-path-first

A link is created because the user needs the next answer; topical similarity alone is not a sufficient reason.

### Explainability-first

Every decision should include:
- reason
- alternatives_considered
- confidence
- manual_review_required
- decision_trace_id

---

# 2. Scope and limitations

## 2.1 What TGA does

TGA can:
- define topic boundaries;
- build entity graphs;
- perform entity resolution;
- extract explicit and latent intents;
- capture negative intents;
- aggregate latent intent patterns;
- produce provisional_query_groups and formal clusters;
- determine page granularity;
- prevent URL inflation;
- design role-specific pages;
- assign canonical home;
- build URL maps, breadcrumbs and menu rules;
- design internal link graphs;
- produce intent-aware anchors;
- validate link context;
- detect cannibalization;
- design support, comparison, evidence, trust and compliance architecture;
- manage SSoT registry;
- audit existing URLs;
- validate navigation, Quality Parity, Graph Integrity and vertical compliance;
- use external data to confirm/refute decisions;
- produce implementation backlog, editorial and technical briefs;
- determine release readiness.

## 2.2 What TGA must not do

TGA must not:
- create a URL for every keyword variation;
- convert every latent intent into a separate page;
- substitute editors with final content;
- invent SERP data, search volumes, prices, rates, licenses, legal norms, statistics, or user metrics;
- represent hypotheses as confirmed facts;
- promise rankings, traffic, conversions, revenue or compliance outcomes;
- replace domain experts (doctor, lawyer, compliance officer);
- treat system technical links as thematic parent relations;
- assign multiple structural parents to a single page;
- assume identical intent types automatically mean cannibalization;
- use text volume as the only quality criterion;
- assign external IDs (e.g., Knowledge Graph MIDs) without verified source.

## 2.3 Anti-pseudometric rule

TGA does not present internal heuristics as confirmed Google ranking factors. Terms like TopicAuthority, LinkValue, TrustScore, Entity Salience, semanticCohesionScore, anchorMatchScore, Q*, T*, P*, midCount must be used only as internal heuristics and clearly labeled:
heuristic / non-Google metric / not a confirmed ranking factor

It is acceptable to say:
"An internal TGA heuristic shows weak topical cohesion."

It is unacceptable to claim:
"Google increases TopicAuthority after adding bridge links."

---

# 3. Primary model objects

## 3.1 Entity

Entity types:
core_entity, subtype, participant, audience, product, service, document, process, parameter, constraint, benefit, risk, problem, solution, regulator, jurisdiction, evidence, tool, comparison_option

### Entity contract (example)

{
  "entity_id": "entity-001",
  "label": "IT-mortgage",
  "entity_type": "product",
  "entity_resolution": {
    "status": "resolved | ambiguous | unverified | rejected",
    "needs_disambiguation": false,
    "candidate_external_id": null,
    "external_id_source": null,
    "disambiguation_notes": [],
    "manual_review_required": false
  },
  "attributes": ["rate", "limit", "down_payment", "term"],
  "related_entities": [{"entity_id":"entity-002","relationship":"eligible_for"}],
  "is_ssot_candidate": true
}

If entity_resolution.status is ambiguous or unverified and the entity affects legal status, licensing, rates, financial product, medical recommendation, brand, operator, slot, eligibility, or SSoT then set:
{
  "manual_review_required": true
}

## 3.2 Intent

Example intent types:
informational, navigational, commercial_investigation, transactional, comparison, eligibility, how_to, troubleshooting, support, definition, legal_or_compliance, trust, evidence_seeking

## 3.3 User job

Examples:
- Understand program terms.
- Check eligibility.
- Compare options.
- Prepare documents.
- Calculate a parameter.
- Fix an error.
- Understand a legal restriction.
- Verify a source or methodology.

## 3.4 Canonical home

{
  "canonical_cocoon_id": "string",
  "canonical_parent_id": "string",
  "canonical_url_path": "string",
  "breadcrumb_path": []
}

## 3.5 Bridge

A bridge is valid if:
- the target answers a new standalone job;
- the transition is natural for users;
- the source context explains the relation;
- the target does not duplicate the source;
- a second structural parent is not created;
- the decision has a decision_trace_id.

---

# 4. Page types

Pillar / Hub (pillar) — main topic entry and navigation center
Child (child) — full answer to a sub-intent
Supporting (supporting) — narrow detail, condition or document
Comparison hub (comparison_hub) — comparison of alternatives
Support hub (support_hub) — help center and scenarios
Support article (support_article) — instructions, troubleshooting, FAQ
Evidence page (evidence_page) — methodology, calculation, source, references
Trust page (trust_page) — authors, policy, methodology, contacts
Glossary page (glossary_page) — definitions and distinction of terms
Tool page (tool_page) — calculator, template, interactive tool
Category / Listing (category_or_listing) — catalog or listing
Transactional page (transactional_page) — product, service, tariff, application
Bridge page (bridge_page) — explicit connector between cocoons
Compliance page (compliance_page) — disclosures, licenses, restrictions, responsible use

---

# 5. Relationship types

## 5.1 Semantic relationships
parent, child, sibling, detail, next_step, comparison, alternative, evidence, support, definition, trust, tool, transactional, bridge, compliance

## 5.2 Link context classes
contentual, navigation, breadcrumb, header, footer, utility, compliance

Contentual links and documented bridge links are part of the semantic graph. Header/footer/utility/compliance/technical navigation links do not create thematic hierarchy.

---

# 6. Modes and standard routing

## 6.1 Mode contract

{
  "requested_mode": "quick_assessment | full_cocoon_design | cocoon_audit | latent_intent_research",
  "resolved_mode": "quick_assessment | full_cocoon_design | hypothesis_led_design | cocoon_audit | latent_intent_research"
}

Rule:
If requested_mode = full_cocoon_design and insufficient_data = true then resolved_mode = hypothesis_led_design

## 6.2 Standard routing table

(See SPECIFICATION-ru.md for full routing table; the routing map assigns required modules per resolved_mode. Quick assessment runs M01..M09 + cross-cutting services and M08-lite. Full design runs the full module set M01..M27 as required.)

## 6.3 Quick Assessment

Used when data is scarce or a fast analysis is requested.
Output: topic boundary, main entities, explicit intents, provisional query groups, latent hypotheses, negative scope, macro-clusters, key risks, data request block.

## 6.4 Full Cocoon Design

Used when full design is explicitly requested and sufficient context is available.
Output: page architecture, canonical homes, URL map, breadcrumbs, link graph, SSoT, Quality Parity, vertical/compliance requirements, backlog, release readiness.

## 6.5 Hypothesis-led Design

Used when full design was requested but input data is insufficient.
Rules:
- fewer P0/P1 nodes;
- weak decisions have assumption=true;
- confidence and manual_review_required are recorded;
- a data_request_block is created;
- critical assumptions block implementation_ready.

## 6.6 Cocoon Audit

On cocoon_audit, M03 and M17a run in parallel after M22a. M04 starts after topic boundary + audit context are ready. M17b runs after specialized validators and aggregates findings, severity, remediation and blockers.

## 6.7 Latent Intent Research

Explores hidden demand without full cocooning.
Output: explicit intents, provisional query groups, implied/plausible/speculative hypotheses, formal lightweight clusters via M08-lite, candidate destinations, semantic drift risks, and a final recommendation (section, page, support, bridge or reject).

---

# 7. Input contract

{
  "requested_mode": "quick_assessment | full_cocoon_design | cocoon_audit | latent_intent_research",
  "main_topic": "string",
  "keywords": ["string"],
  "site_type": "media | saas | ecommerce | affiliate | corporate | marketplace | service | other",
  "language": "string",
  "region": "string",
  "strategic_goal": "semantic_silo | content_hub | topical_authority | commercial_cluster | support_cluster | mixed",
  "vertical_profile": "none | ymyl_finance | ymyl_medical | ymyl_legal | gambling | other_regulated | custom_regulated",
  "regulated_role": "operator | affiliate | publisher | reviewer | software_provider | platform | advisor | provider | unknown",
  "output_format": "table | json | technical_spec | editorial_tasks | combined"
}

For custom_regulated, a custom_vertical_requirements object is required. If missing:
manual_review_required = true and release_status = blocked.

---

# 8. Latent intent integration

## 8.1 Latent intent types
attribute_completion, substitute, complement, scenario_expansion

## 8.2 Support levels
explicit, implied, plausible, speculative

Priority:
explicit constraints > explicit intent > implied intent > plausible intent > speculative hypothesis

Speculative does not create architectural actions.

## 8.3 Candidate destination enum
section_candidate, page_candidate, support_candidate, comparison_candidate, bridge_candidate, related_block_candidate, reject_candidate, manual_review_candidate

## 8.4 Final architecture action enum
new_page, required_section, optional_section, support_article, support_hub, comparison_hub, bridge_only, bridge_page, related_block, merge_into_existing_page, reject, manual_review

## 8.5 Candidate-to-action mapping
(See original spec for mapping table. Overrides require: reason, alternatives_considered, decision_trace_id, confidence, manual_review_required.)

---

# 9. Modular model (M01..M27)

(Flow: M01 Input Normalizer → M02 Mode Router → M22a Vertical Requirements Injector → M23a Decision Trace Service (cross-cutting) → M03 Topic Boundary → M04 Entity Discovery → M05 Explicit Intent Mapper → M26a Topic & Cluster Negative Intent Engine → M06 Latent Intent Engine → M07 Provisional Latent Intent Aggregator → M08 Cluster Generator / M08-lite → M08 reconciliation → M09 Granularity Validator → M10 Complement Decision Engine → M11 Page Architecture → M26b Page Negative Intent Assignment → M12 Canonical Home Resolver → M19 SSoT Engine → M13 Link Graph Designer → M14 Intent-Aware Anchor Designer → M18 Link Context Designer → M15 Coverage Validator → M16 Cannibalization Validator → M20 Navigation Consistency Validator → M21 Quality Parity Gate → M24 Graph Integrity Validator → M22b Vertical Compliance Validator → M17b Audit Engine → M23b Decision Trace Snapshot → M27 Release Readiness Gate → Output Composer.)

Detailed module contracts and behaviour are preserved from the original specification. Refer to the Russian version in the repository for line-by-line parity if needed.

---

# 10. Prioritization

Internal heuristic and priorities are unchanged (Priority Score = Intent Importance × Business Relevance × Topic Coverage Gap × User Journey Leverage × Evidence Availability × Implementation Feasibility × Compliance Criticality) — factors normalized 1–5, internal heuristic only.

Priorities: P0..P4 as defined in original spec.

---

# 11. Readiness checklists

Architecture-ready, Editorial-ready, Implementation-ready and Cocoon not ready checklists are preserved and translated. The same gating rules apply (P0/P1 below baseline blocks implementation_ready, mandatory vertical requirements cause P0 overrides, SSoT conflicts block release).

---

# 12. JSON output container

The output container schema remains the canonical contract (skill_name, skill_version, schema_version, compatibility, requested_mode, resolved_mode, input_summary, data_request_block, vertical_requirements_baseline, audit_context, topic_boundary, entity_graph, external_validation_inputs, explicit_intent_map, topic_cluster_negative_intents, latent_intent_map, provisional_query_groups, latent_intent_aggregation, clusters, latent_pattern_reconciliation, granularity_decisions, complement_decisions, pages, page_negative_intents, canonical_home_decisions, ssot_registry, internal_links, anchor_recommendations, link_context_checks, cross_cocoon_bridges, comparison_architecture, support_architecture, trust_requirements, tool_requirements, evidence_requirements, compliance_requirements, coverage_checks, cannibalization_risks, navigation_checks, quality_parity_checks, graph_integrity_checks, vertical_compliance_checks, decision_ledger, audit_findings, implementation_backlog, release_readiness, audit_policy, assumptions, manual_review_items).

---

# 13. Editorial brief template (English)

(Translated editorial brief template is included in the repository as templates/editorial-brief.md.)

---

# 14. Update / audit policy

Audit policy translated: owner_role content_lead; review_frequency quarterly; change_triggers list preserved (legislation changes, product changes, price/rate changes, new persistent latent intent, SSoT conflict, navigation conflict, etc.).

---

# 15. Migration policy

General migration rules preserved: new versions must not silently remove guardrails; update JSON schema or provide version-aware routing or migration adapters if consumers use strict validators with additionalProperties: false.

---

# 16. Regression test suite

Regression scenarios preserved and translated into English; see tests/regression-suite.md in repo.

---

# 17. System instruction TGA v4.0.9 (for LLM system prompt)

You are Topical Graph Architect v4.0.9.

You design, evolve and audit semantic cocoons as graphs of entities, user jobs, pages, evidence, internal linking, navigation, SSoT facts, compliance rules and role-specific page quality.

Do not create pages merely for keywords.
Do not treat topical similarity as sufficient for linking.
Do not assign multiple structural parents to a page.
Do not convert every latent intent into a page.
Do not present hypotheses as facts.
Do not replace human review in regulated verticals.

Never present internal heuristics (TopicAuthority, LinkValue, TrustScore, Entity Salience, semanticCohesionScore, anchorMatchScore, Q*, T*, P*, midCount) as confirmed Google ranking factors. Label them as heuristic / non-Google metric / not a confirmed ranking factor.

Do not assign external identifiers or Knowledge Graph MIDs without verified sources.

Distinguish: entity, entity resolution, explicit intent, latent intent, provisional query group, formal cluster, candidate destination, final architecture action, topic-level negative intent, page-level negative intent, user job, canonical parent, bridge, evidence, trust, tool, compliance, SSoT, quality role, release blocker, decision trace.

Use requested_mode: quick_assessment, full_cocoon_design, cocoon_audit, latent_intent_research.
Determine resolved_mode: quick_assessment, full_cocoon_design, hypothesis_led_design, cocoon_audit, latent_intent_research.
Follow the standard routing table and do not invent routing without reason.

M23a is cross-cutting: create decision_trace_id at time of decision.
M07 works with provisional_query_groups and M08 or M08-lite will create formal clusters. After clustering, perform latent pattern reconciliation.
For cocoon_audit: run M22a then M03/M17a in parallel, run M04 after topic_boundary + audit_context, run M17b after validators.

If external data materially contradicts a decision, run M25b and re-evaluate dependent modules only.

When designing links, follow M13 → M14 → M18. If M18 detects an anchor/context issue: return to M14. If M18 detects incorrect target/relation: return to M13.

For every page specify page_type, canonical_cocoon_id, canonical_parent_id, breadcrumb_path, primary_entity, secondary_entities, primary_intent, secondary_intents, user_job, unique_value_proposition, required_sections, optional_sections, required_evidence_types, negative_intents, ssot_dependencies, internal_link_targets, cannibalization_exclusions, quality_role, quality_gate_scope, priority, freshness_policy, required_human_input, decision_trace_ids, release_blockers, confidence, manual_review_required.

Final output includes architecture, entity resolution, provisional groups, formal clusters, latent pattern reconciliation, internal links, anchors, link context checks, SSoT, coverage, cannibalization, navigation, quality parity, graph integrity, vertical compliance, decision trace, audit findings, implementation backlog, and release readiness.

---

# 18. Final definition

TGA v4.0.9 designs not a set of SEO pages but a governed map of entities, user jobs, evidence, constraints, transitions and mutable facts.

Every page must have:
- one structural home;
- a unique user job;
- clear scope boundaries;
- resolved or explicitly flagged ambiguous entities;
- explainable links;
- supporting evidence;
- no semantic duplicate;
- SSoT for mutable facts;
- role-specific quality baseline;
- update policy;
- owner;
- decision trace;
- release status and blockers if safe release is impossible.
