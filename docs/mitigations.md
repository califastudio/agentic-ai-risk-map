# Proposed Mitigations for Agentic AI Risks — v0.2 | May 2026

*Practical complement to the framework.* Focus on technical, architectural and governance mitigations to make agentic systems safer and more governable.

## General Mitigation Principles

- *Defense in Depth* — Multiple layers of control — no single layer is sufficient on its own.
- *Least Agency* — Grant agents only the autonomy and permissions strictly necessary for the task.
- *Runtime Governance* — Continuous monitoring and control during operation — not only pre-deployment.
- *Auditability by Design* — Everything must be traceable and reconstructable after the fact.
- *Human-in-the-Loop Gradual* — Mandatory human oversight for high-impact actions, with configurable thresholds.

## Mitigations by Risk Category

| Risk Category                          | Proposed Mitigations                                                                 | Type                     | Difficulty |
|----------------------------------------|--------------------------------------------------------------------------------------|-------------------------|------------|
| *Agent Sprawl & Shadow AI* | - Centralized agent registry + TTL<br>- Mandatory Agent Registration policy<br>- Periodic scanning for unauthorized agents<br>- Auto-expiration of inactive agents | Technical + Governance | Medium |
| *Blast Radius & Cascading Failures* | - Strong sandboxing (isolated containers)<br>- Circuit breakers and rate limiting<br>- Chaos engineering with agents<br>- Clear environment separation | Architecture           | High |
| *Runtime Governance* | - Configurable approval gates<br>- Kill Switch / Global Pause<br>- Full observability (tool call tracing)<br>- Real-time anomaly alerts | Governance + Technical | High |
| *Least Agency & Privilege Escalation* | - Dynamic Least Privilege (just-in-time)<br>- Ephemeral credentials<br>- Agent hierarchy<br>- Automated permission review | Technical               | Medium |
| *Memory Poisoning* | - Memory attestation + cryptographic checksums<br>- Periodic memory scrubbing<br>- Short/long-term memory separation<br>- Versioning and rollback | Technical               | High |
| *Auditability & Traceability* | - Immutable logging + cryptographic signatures<br>- Standardized Agent Decision Records<br>- Central audit dashboard | Technical + Legal       | Medium |
| *Financial & Autonomous Transactions* | - Dual/multi-signature for high amounts<br>- Per-agent limits<br>- Whitelist of destinations<br>- Agentic anti-fraud monitoring | Governance + Legal      | Medium |
| *Multi-Agent Coordination* | - Supervisor orchestrator<br>- Validated inter-agent protocols<br>- Detection of emergent behaviors | Architecture           | High |
| *Agent Supply Chain Risk* | - Version pinning of tools/plugins<br>- Sandbox per external tool<br>- Periodic dependency auditing | Technical               | Medium |
| *Identity & Authentication* | - Unique Agent IDs<br>- Human vs agent verification<br>- Role-segregated credentials | Technical + Legal       | High |

## Lifecycle & Continuous Compliance

Given the evolutionary nature of agents, mitigation is not a one-time event but a continuous oversight cycle:

* **Continuous Agent Auditing**: Implementation of real-time monitoring to detect *Agent Drift* (deviation from objectives) or unforeseen behaviors outside the initial ethical framework.
* **Recertification Protocols**: Quarterly review cycles of mitigation frameworks to align them with new model capabilities and evolving global regulations (e.g., AI Act, sector-specific resolutions).
* **Incident Learning Loop**: Immutable logging of minor failures or "near-misses" to preventively strengthen *Kill Switches* and refine human approval thresholds.
* **Automated Policy Enforcement**: Deployment of supervisor agents dedicated exclusively to auditing the fleet's compliance with the governance policies defined in this framework.

## Architectural Recommendations

- *Orchestration*: LangGraph, CrewAI or custom with strong supervision
- *Observability*: LangSmith + OpenTelemetry + custom dashboards
- *Security*: OAuth2 + short-lived tokens + mTLS + sandboxing
- *Identity*: Internal Agent IDs + DID (optional)
- *Continuous Evaluation*: Automated red teaming + agent safety benchmarks

---

This framework is living and must evolve alongside the technology. Contributions welcome.


