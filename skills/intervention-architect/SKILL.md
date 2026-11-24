|---
name: intervention-architect
description: Dato un problema diagnosticato (P1–P6), propone opzioni d'intervento (I1–I6) con framework associati (F1–F6). Modula tra versioni light/standard/trasformativa. Include durata, ticket, rischi.
category: consulting
prerequisites: [consulting/diagnostic-navigator]
ontology_refs: [P1, P2, P3, P4, P5, P6, I1, I2, I3, I4, I5, I6, F1, F2, F3, F4, F5, F6]
---

# Intervention Architect

Carica questa skill **dopo** aver diagnosticato un problema con [[consulting/diagnostic-navigator]]. 
Prende in input un codice Px (o multipli) e produce opzioni d'intervento strutturate.

Non può essere usata senza una diagnosi esplicita (DOS: R5, G1, AP1).

## Step 0 — Verifica precondizione

**Non procedere se non c'è un problema P1–P6 diagnosticato.** 
Se il consulente chiede "che intervento mi suggerisci per X?" senza diagnosi, fermati e rispondi:
> "Posso proporre interventi solo dopo aver diagnosticato il problema. Puoi fornirmi il codice Px o descrivere la situazione così che possa diagnosticarla?"

## Step 1 — Carica il framework di riferimento

Leggi dall'[[04 - Artefacts/Artefact - Ontologia Professionale.md|Ontologia Professionale]]:
- Sezione **Interventi Consulenziali (I1–I6)** — tabella completa con durata, ticket, scalabilità
- Sezione **Framework & Pratiche (F1–F6)** — mappa framework → problemi
- Sezione **Offerta (6 aree)** — dettaglio per ogni offerta
- Sezione **Contesto del Cliente** — tipo, settore, maturità

Leggi dal [[04 - Artefacts/Artefact - DOS (Design Ontology Spec).md|DOS]]:
- Sezione **Relationships** — le regole di collegamento
- Sezione **Rules (R1–R10)** — vincoli di consistenza

## Step 2 — Mappa problema → interventi candidati

Usa la tabella di mapping:

| Problema | Interventi candidati (priorità) |
|----------|-------------------------------|
| P1 | I1 (primario), I4 (supporto), I6 (se P4 concomitante) |
| P2 | I2 (primario), I5 (prerequisito: assessment), I4 (formazione AI literacy) |
| P3 | I1 (primario: pratiche NWoW), I4 (formazione/capacity), I6 (se disallineamento OKR) |
| P4 | I6 (primario: OKR), I1 (se contesto organizzativo), I4 (formazione) |
| P5 | I5 (primario: assessment), I2 (se focus AI), I3 (se innovation = servizio), I4 (alfabetizzazione) |
| P6 | I3 (primario: service design + GTM), I5 (prerequisito: readiness) |

## Step 3 — Costruisci le opzioni

Per ogni intervento candidato, produci **tre versioni**:

### Versione Light
- **Durata:** 1–4 settimane
- **Ticket:** Basso-medio
- **Cosa include:** Assessment rapido / workshop singolo / diagnosi + report
- **Output:** Report, canvas compilato, roadmap sintetica
- **Quando usarla:** Cliente dubbioso, primo contatto, budget limitato

### Versione Standard
- **Durata:** 2–4 mesi (valori dalla tabella Ix)
- **Ticket:** Medio-medio alto (valori dalla tabella Ix)
- **Cosa include:** Fasi complete dell'intervento (dalla tabella offerta)
- **Output:** Deliverable completi (playbook, toolkit, roadmap, formazione)
- **Quando usarla:** Cliente ingaggiato, budget adeguato, problema chiaro

### Versione Trasformativa
- **Durata:** 4–12+ mesi
- **Ticket:** Alto
- **Cosa include:** Intervento full + accompagnamento + follow-up
- **Output:** Trasformazione organizzativa misurata
- **Quando usarla:** Cliente strategicamente allineato, commitment C-level

## Step 4 — Associa il framework F1–F6

Ogni intervento deve specificare il framework usato:

| Intervento | Framework primario | Framework secondario |
|-----------|-------------------|---------------------|
| I1 | F2 — Organizational Design / Semco Style | F6 — Future of Work |
| I2 | F5 — AI Strategy & Governance | F4 — Platform Design |
| I3 | F1 — Design Thinking & HCD | F4 — Platform Design Toolkit |
| I4 | F6 — Future of Work | F3 — OKR (se allineamento) |
| I5 | Proprietario (Digital Readiness) | F5 — AI Governance |
| I6 | F3 — OKR & Performance Management | F2 — Organizational Design |

## Step 5 — Verifica vincoli

Prima di consegnare, controlla:

- ✅ **R2** — L'intervento ha il framework corrispondente? (Ogni Ix ha almeno un Fx)
- ✅ **R5** — Il problema mappa ad almeno un intervento?
- ✅ **R3** — Hai specificato la Definition of Done per i deliverable?
- ✅ **R10** — Il ticket è coerente con durata e complessità?
- ❌ **AP6** — Stai decidendo al posto del consulente? (G6: l'agente propone, il consulente sceglie)

## Step 6 — Formatta l'output

```
## Proposta di intervento

### Diagnosi di partenza
- **Problema primario:** [Px] — [nome]
- **Problemi secondari:** [Py] — [nome]

### Opzione Light — "[Nome breve]"
- **Durata:** [X] settimane
- **Ticket stimato:** €[range]
- **Framework:** Fx — [nome]
- **Cosa include:**
  - [attività 1]
  - [attività 2]
- **Deliverable:**
  - [deliverable 1]
  - [deliverable 2]
- **Definition of Done:** [criteri di accettazione]
- **Rischi:** [eventuali criticità]
- **Quando conviene:** [situazione ideale]

### Opzione Standard — "[Nome breve]"
...

### Opzione Trasformativa — "[Nome breve]"
...

### Raccomandazione del consulente
(lasciata vuota — la compila il consulente)
```

## Tabella riassuntiva I1–I6

| Codice | Nome | Problemi | Durata | Ticket | Scalabilità |
|--------|------|----------|--------|--------|-------------|
| **I1** | Trasformazione Organizzativa & NWoW | P1, P3, P4 | 3–12+ mesi | Alto | Media |
| **I2** | AI Strategy & Organizational Design | P2, P5 | 1.5–4 mesi | Medio-alto | Medio-alta |
| **I3** | Service & Product Design + GTM | P5, P6 | 3–9 mesi | Medio-alto | Media |
| **I4** | Programmi Formativi & Capacity Building | P3, P4, P5 | 1g – 6 mesi | Medio–medio-alto | Alta |
| **I5** | Assessment, Toolkit & Knowledge Systems | P4, P5, P3 | 1–2 mesi | Medio | Molto alta |
| **I6** | OKR & Allineamento Strategico | P4, P3 | 2–6 mesi | Medio-alto | Alta |