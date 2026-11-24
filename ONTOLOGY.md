# Consulting Ontology Reference

This document defines the semantic codes used across the consulting skills in this repository. Each code references a concept from Filippo Scorza's professional ontology — the categorization system for client problems, consulting interventions, frameworks, and principles that underpin every skill.

---

## P — Client Problems (P1–P6)

Client situations and organizational frictions, diagnosed before any intervention is proposed.

| Code | Problem | Domain | Typical Stakeholders |
|------|---------|--------|---------------------|
| **P1** | Organizational model misaligned with complex context | Organizational Design | C-level, HR |
| **P2** | Digital/AI transformation without strategy and organizational model | AI & Digital | CEO, IT, HR |
| **P3** | Culture and work models inconsistent with the future of work | Future of Work | HR, Managers |
| **P4** | Weak performance and strategic alignment | Organizational Design | CEO, Team |
| **P5** | Low innovation/digital readiness | Innovation | C-level, Innovation teams |
| **P6** | CX/service design inconsistent with strategy and organization | Service Design | Marketing, Operations |

### Common problem co-occurrences

| Primary | Frequent secondary | Why |
|---------|-------------------|-----|
| P1 | P3, P4 | Rigid model produces control culture and misalignment |
| P2 | P5, P3 | AI without strategy reveals digital immaturity and cultural resistance |
| P3 | P1, P4 | Misaligned culture blocks organizational transformation |
| P4 | P3 | Ineffective OKRs often hide deeper cultural issues |
| P5 | P2, P6 | Low readiness blocks both AI adoption and service innovation |
| P6 | P5 | Incoherent service reveals organizational readiness gaps |

---

## I — Consulting Interventions (I1–I6)

Structured service offerings, each targeting specific problem codes.

| Code | Name | Target Problems | Duration | Fee Level | Scalability |
|------|------|-----------------|----------|-----------|-------------|
| **I1** | Organizational Transformation & NWoW | P1, P3, P4 | 3–12+ months | High | Medium |
| **I2** | AI Strategy & Organizational Design | P2, P5 | 1.5–4 months | Medium–high | Medium–high |
| **I3** | Service & Product Design + GTM | P5, P6 | 3–9 months | Medium–high | Medium |
| **I4** | Training Programs & Capacity Building | P3, P4, P5 | 1 day – 6 months | Medium–medium-high | High |
| **I5** | Assessment, Toolkit & Knowledge Systems | P4, P5, P3 | 1–2 months | Medium | Very high |
| **I6** | OKR & Strategic Alignment | P4, P3 | 2–6 months | Medium–high | High |

### Problem–Intervention mapping

| Problem | Primary intervention | Supporting interventions |
|---------|---------------------|------------------------|
| P1 | I1 | I4, I6 (if P4 concurrent) |
| P2 | I2 | I5 (prerequisite: assessment), I4 (AI literacy training) |
| P3 | I1 (NWoW practices) | I4, I6 (if OKR misalignment) |
| P4 | I6 (OKR) | I1 (if organizational context), I4 |
| P5 | I5 (assessment) | I2 (if AI focus), I3 (if innovation = service), I4 |
| P6 | I3 (service design + GTM) | I5 (prerequisite: readiness assessment) |

---

## F — Frameworks & Practices (F1–F6)

Methodologies and tools used within interventions.

| Code | Framework | Primary intervention | Secondary intervention |
|------|-----------|---------------------|----------------------|
| **F1** | Design Thinking & Human-Centered Design | I3 | — |
| **F2** | Organizational Design / Semco Style | I1 | I6 |
| **F3** | OKR & Performance Management | I6 | I2 |
| **F4** | Platform Design Toolkit | I3 | I2 |
| **F5** | AI Strategy & Governance | I2 | I5 |
| **F6** | Future of Work & NWoW | I1 | I4 |

---

## M — AI Manifesto Principles (M1–M10)

Ethical and design principles from the AI Manifesto. Used primarily in content positioning and governance context.

| Code | Principle |
|------|-----------|
| **M1** | People at the center |
| **M2** | Transparency and explainability |
| **M3** | Human oversight and control |
| **M4** | Fairness and non-discrimination |
| **M5** | Bias and discrimination prevention |
| **M6** | Accountability |
| **M7** | Privacy and data protection |
| **M8** | Security and robustness |
| **M9** | Widespread AI literacy |
| **M10** | Ethics across the lifecycle |

---

## DOS — Design Ontology Spec References

Skills reference rules (R), guidelines (G), and anti-patterns (AP) from the Design Ontology Spec.

### Rules (R)

| Code | Rule |
|------|------|
| **R2** | Every intervention has at least one corresponding framework (Fx) |
| **R3** | Every deliverable has a Definition of Done |
| **R5** | The problem maps to at least one intervention |
| **R9** | All content must align to at least one Framework (F1–F6) or AI Manifesto Principle (M1–M10) |
| **R10** | Fee level is consistent with duration and complexity |

### Agent Guidelines (G)

| Code | Guideline |
|------|-----------|
| **G1** | Diagnose before proposing solutions |
| **G2** | Only reference frameworks that exist in the catalog (F1–F6) |
| **G4** | Identify missing information and ask the consultant clarifying questions |
| **G6** | The agent proposes, the consultant decides |

### Anti-Patterns (AP)

| Code | Anti-Pattern |
|------|-------------|
| **AP1** | Solution before diagnosis |
| **AP2** | Floating glossary — using invented synonyms instead of ontology terms |
| **AP4** | Orphan objects — diagnosing a problem outside the P1–P6 catalog |
| **AP6** | Deciding for the consultant |
| **AP7** | Flat client — ignoring sector, maturity, and context |
| **AP8** | Vault ignored — not reading existing client data before formulating |