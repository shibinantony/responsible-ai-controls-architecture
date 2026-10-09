# Enterprise Client Discovery Checklist: Responsible AI Controls

> **Navigation:** [🏠 Overview](../README.md) | [📰 01. Thought Leadership](01-thought-leadership-article.md) | [📄 02. Consulting POV](02-one-page-consulting-pov.md) | [📊 03. Mini Deck](03-five-slide-mini-deck.md) | **📋 04. Discovery Checklist**

---

## Purpose & Interview Discipline

A reusable diagnostic interview checklist for assessing Responsible AI control maturity without drifting into broad governance theory or philosophical debates.

> [!IMPORTANT]
> **Interview Discipline:**  
> Structure discovery using the core progression:  
> **`Risk Classification → Execution Boundary → Control Design → Evidence Capture → Day 2 Monitoring`**  
> Focus on actual runtime workflows, decision rights, technical guardrails, audit logging, and Day 2 operational routines.

![Responsible AI Controls Architecture](../assets/5-layer-controls-architecture.svg)

---

## 1. Use-Case Scope & Portfolio Inventory

- [ ] **AI System Modalities:** Which AI types are active in the portfolio?
  - Traditional ML (tabular, predictive scoring)
  - Generative AI (LLMs, SLMs, multi-modal models)
  - Enterprise Copilots (M365 Copilot, GitHub Copilot)
  - Retrieval-Augmented Generation (RAG systems)
  - Autonomous Agentic Workflows (multi-agent, tool-calling agents)
  - Third-party SaaS / Vendor AI integrations
- [ ] **Business Domain Priority:** Which business units have highest strategic priority?
  - Customer Service / Conversational AI
  - Claims Adjudication & Processing
  - Underwriting, Risk Modeling & Credit Decisioning
  - Regulated Advisory & Wealth Management
  - Internal Employee Knowledge & Operations
- [ ] **Deployment Status:** What is the lifecycle breakdown of identified use cases?
  - In Production / Live: `____`
  - In Active Pilot / PoC: `____`
  - Awaiting Governance / Risk Approval: `____`

---

## 2. Risk Classification & Impact Tiering

- [ ] Does the organization maintain an explicit AI risk-tiering methodology?
- [ ] Are systems classified by **consequence of error** (customer harm, financial loss, regulatory sanction, brand reputation) rather than technology stack?
- [ ] Are use cases segregated by customer-facing vs. internal employee usage?
- [ ] Which use cases handle sensitive data (PII, financial transactions, health records)?

---

## 3. Execution Boundaries & Decision Rights

- [ ] What is the explicit authorization level for each AI system?
  - **Draft only:** Produces content requiring 100% human review before dispatch.
  - **Recommend:** Recommends action; human decides whether to execute.
  - **Execute with Exception:** Automates low-risk actions; pauses on anomaly for human intervention.
  - **Autonomous:** Fully automated within deterministic parameter guardrails.
- [ ] Are human review thresholds documented and enforced technically, or left to employee discretion?
- [ ] What are the formal escalation pathways and override procedures when an employee disagrees with model output?

---

## 4. Control Design & Runtime Guardrails

- [ ] What runtime guardrails are active at the API or application gateway layer?
  - Input prompt injection & jailbreak prevention
  - Sensitive data / PII redaction and tokenization
  - Knowledge grounding verification (hallucination scoring against retrieval sources)
  - Toxicity, brand safety, and regulatory compliance filters
  - Deterministic JSON schema output validation
- [ ] Are controls enforced **at runtime** (blocking API calls), at pre-release review, or merely in static policy documentation?
- [ ] How are third-party vendor AI models audited and validated before enterprise data ingestion?

---

## 5. Evidence Capture & Auditability

- [ ] What telemetry is captured for every production inference?
  - User ID & Timestamp
  - Full input prompt and retrieved context references
  - Foundation model version and temperature settings
  - System output and confidence metrics
  - Guardrail evaluations and policy filter results
  - Human review approval, rejection, or edit record
- [ ] Can an AI-assisted customer outcome or financial transaction be cryptographically reconstructed 12 months later for a regulatory audit?
- [ ] Who holds ownership of the evidence repository, and what is the data retention schedule?

---

## 6. Day 2 Monitoring & Telemetry

- [ ] What automated alerts trigger operational review after deployment?
  - Retrieval context drift & semantic degradation
  - Guardrail bypass attempts & adversarial probe spikes
  - Output quality and user feedback downvotes
  - Upstream foundation model version updates or silent provider deprecations
- [ ] Who owns operational incident triage when an AI system produces a hallucinations or compliance breach?
- [ ] How do post-incident findings feed back into Policy-as-Code updates?

---

## 7. Success Definition & Proof of Concept

- [ ] For a focused 4–6 week advisory sprint, what defines enterprise success?
- [ ] Which 1 or 2 high-impact use cases will serve as the pilot for the controls architecture?
- [ ] Which governance bodies (Risk Committee, CISO, Architecture Board, Legal Counsel) must sign off on the operating model?

---

## Output Template: AI Use-Case Controls Matrix

Capture client discovery findings directly into this structured template:

| Use Case Name | Consequence Tier (Low / Mod / High) | Execution Boundary (Draft / Rec / Exec) | Required Controls (Guardrails / HITL) | Evidence Captured (Logs / Signoffs / Replay) | Monitoring & Day 2 Owner |
|---|---|---|---|---|---|
| *Sample: Claims Triage* | High | Recommend (Human Approves) | Grounding check, PII filter, HITL approval gate | Full prompt, retrieved policy, adjuster signoff | Claims Operations & RAI Lead |
| *Sample: Internal Search* | Low | Draft (Employee Uses) | Privacy filter, basic safety, source citations | Query log, click telemetry | Enterprise Search Team |
| *Use Case 1:* | | | | | |
| *Use Case 2:* | | | | | |
| *Use Case 3:* | | | | | |

---

## Next Steps & Reading Path

* **Previous Document:** [03. Executive 5-Slide Mini Deck](03-five-slide-mini-deck.md)
* **Consulting Point of View:** [02. One-Page Consulting POV](02-one-page-consulting-pov.md)
* **Thought Leadership Article:** [01. Thought Leadership Article](01-thought-leadership-article.md)
* **Return to Main Overview:** [Repository README](../README.md)