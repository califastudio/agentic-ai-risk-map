# Proposed Mitigations for Agentic AI Risks — v0.2 | Mayo 2026

*Practical complement to the framework.* Focus on technical, architectural and governance mitigations to make agentic systems safer and more governable.

## General Mitigation Principles

- *Defense in Depth* — Multiple layers of control — no single layer is sufficient on its own.
- *Least Agency* — Grant agents only the autonomy and permissions strictly necessary for the task.
- *Runtime Governance* — Continuous monitoring and control during operation — not only pre-deployment.
- *Auditability by Design* — Everything must be traceable and reconstructable after the fact.
- *Human-in-the-Loop Gradual* — Mandatory human oversight for high-impact actions, with configurable thresholds.

## Mitigations by Risk Category

| Risk Category                          | Proposed Mitigations                                                                 | Type                    | Difficulty |
|----------------------------------------|--------------------------------------------------------------------------------------|-------------------------|------------|
| *Agent Sprawl & Shadow AI*          | - Centralized agent registry + TTL<br>- Mandatory Agent Registration policy<br>- Periodic scanning for unauthorized agents<br>- Auto-expiration of inactive agents | Technical + Governance | Medium |
| *Blast Radius & Cascading Failures* | - Strong sandboxing (isolated containers)<br>- Circuit breakers and rate limiting<br>- Chaos engineering with agents<br>- Clear environment separation | Architecture           | High |
| *Runtime Governance*                | - Configurable approval gates<br>- Kill Switch / Global Pause<br>- Full observability (tool call tracing)<br>- Real-time anomaly alerts | Governance + Technical | High |
| *Least Agency & Privilege Escalation* | - Dynamic Least Privilege (just-in-time)<br>- Ephemeral credentials<br>- Agent hierarchy<br>- Automated permission review | Technical              | Medium |
| *Memory Poisoning*                  | - Memory attestation + cryptographic checksums<br>- Periodic memory scrubbing<br>- Short/long-term memory separation<br>- Versioning and rollback | Technical              | High |
| *Auditability & Traceability*       | - Immutable logging + cryptographic signatures<br>- Standardized Agent Decision Records<br>- Central audit dashboard | Technical + Legal      | Medium |
| *Financial & Autonomous Transactions* | - Dual/multi-signature for high amounts<br>- Per-agent limits<br>- Whitelist of destinations<br>- Agentic anti-fraud monitoring | Governance + Legal     | Medium |
| *Multi-Agent Coordination*          | - Supervisor orchestrator<br>- Validated inter-agent protocols<br>- Detection of emergent behaviors | Architecture           | High |
| *Agent Supply Chain Risk*           | - Version pinning of tools/plugins<br>- Sandbox per external tool<br>- Periodic dependency auditing | Technical              | Medium |
| *Identity & Authentication*  ## Lifecycle & Continuous Compliance

Dada la naturaleza evolutiva de los agentes, la mitigación no es un evento único, sino un ciclo continuo de supervisión:

* **Continuous Agent Auditing**: Implementación de monitoreo en tiempo real para detectar *Agent Drift* (desviación de objetivos) o comportamientos imprevistos fuera del marco ético inicial.
* **Recertification Protocols**: Ciclos de revisión trimestral de los marcos de mitigación para alinearlos con nuevas capacidades de los modelos y actualizaciones regulatorias (ej. AI Act, resoluciones sectoriales).
* **Incident Learning Loop**: Registro inmutable de fallas menores o "near-misses" para fortalecer preventivamente los *Kill Switches* y ajustar los umbrales de aprobación humana.
* **Automated Policy Enforcement**: Uso de agentes supervisores encargados exclusivamente de auditar que el resto de la flota cumpla con las políticas de gobernanza definidas en este framework.       | - Unique Agent IDs<br>- Human vs agent verification<br>- Role-segregated credentials | Technical + Legal      | High |

## Architectural Recommendations

- *Orchestration*: LangGraph, CrewAI or custom with strong supervision
- *Observability*: LangSmith + OpenTelemetry + custom dashboards
- *Security*: OAuth2 + short-lived tokens + mTLS + sandboxing
- *Identity*: Internal Agent IDs + DID (optional)
- *Continuous Evaluation*: Automated red teaming + agent safety benchmarks

---

This framework is living and must evolve alongside the technology. Contributions welcome.

*Author:* Sabrina Pastura | v0.2 - Mayo 2026
