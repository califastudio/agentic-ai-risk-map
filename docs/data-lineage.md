# Data Lineage in Agentic AI Systems

## Introduction

*Data lineage* — the ability to reconstruct where a piece of data came from, how it was transformed, and how it was used — is one of the most overlooked risks in agentic AI environments. Most governance discussions focus on **action traceability** (what did the agent do?) while assuming that **data provenance** (what did the agent know, and where did that knowledge come from?) is a solved problem. It is not.

## The Core Problem

Correct permissions and a complete action log tell you **what** an agent did. They do not tell you **whether the data it acted on was trustworthy, current, or even legitimate**. An agent can have perfectly scoped access controls and a fully auditable decision trail, and still make a critical decision based on stale, fabricated, or maliciously injected data — with no way to trace that back afterward.

This is why data lineage is treated here as a distinct sub-risk under **Auditability & Traceability**, not a subset of action logging.

## Maturity Levels

Data lineage in agentic systems is not a binary problem — it is a spectrum of maturity, and each layer degrades further than the last:

| Level | What it covers | Current state |
|---|---|---|
| **Classic data lineage** | Origin, transformations, and destination of data (ETL pipelines, BI) | 🟢 Mature |
| **AI / inference lineage** | Input data + retrieved context (RAG) + model used + output decision | 🟡 Emerging |
| **Agent action lineage** | All of the above, plus tool calls, persistent memory, and executed actions | 🔴 Very incomplete |
| **Multi-agent provenance** | Full provenance chain when multiple agents interact and pass context to each other | 🔴 Nearly non-existent |

Classic data lineage is a mature, well-tooled discipline in data engineering. But as soon as an LLM-based agent enters the picture, provenance tracking falls apart — and it falls apart fastest exactly where autonomy is highest.

## Why This Matters

- **Auditability collapses silently.** A system can look fully compliant (permissions, logs, approvals) while being un-auditable at the data layer. See [Emerging Risks — Auditability & Traceability](./emerging-risks.md).
- **Memory poisoning becomes harder to detect.** Without lineage, there is no baseline to distinguish legitimate context from injected or fabricated content. See [Emerging Risks — Memory Poisoning](./emerging-risks.md).
- **Cascading failures become harder to contain.** When a bad decision propagates across connected systems, root-causing it requires reconstructing where the triggering data originated at every hop. See [Emerging Risks — Blast Radius & Cascading Failures](./emerging-risks.md).
- **GDPR obligations become harder to meet.** Article 30 requires an up-to-date Record of Processing Activities; without lineage, an organization cannot reliably state what personal data an agent used or where it came from. See [Privacy & Data Protection](./privacy-gdpr.md).

## Mitigations

- **Provenance tagging** — attach source metadata to every external document, retrieved chunk, or tool output before it enters the agent's context.
- **Dataset and knowledge-source versioning** — hash and version any data source an agent can query, so a decision can be tied back to a specific snapshot.
- **Immutable retrieval logs** — log not just *that* retrieval happened, but *which* source, version, and confidence score fed into it.
- **Lineage-aware memory design** — separate short-term and long-term memory stores so provenance metadata isn't silently dropped during summarization or compaction.

See [Mitigations](./mitigations.md) for the full framework-wide mitigation catalog.

## Status

**Maturity of this risk category:** Newly identified — not yet explicitly covered by NIST AI RMF, the EU AI Act, ISO/IEC 42001, or the OWASP Top 10 for Agentic Applications (2026). Related but distinct from action-level auditability, which those frameworks partially address.


**Last updated:** September 2026 (framework v0.4).
