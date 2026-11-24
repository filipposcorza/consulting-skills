|---
name: assessment-engine
description: "Gestisce il ciclo completo di un assessment I5: survey design, interviste strutturate, analisi, report, roadmap. Include Digital Readiness Checkup, ONA light, OKR maturity."
category: consulting
prerequisites: [consulting/diagnostic-navigator, consulting/client-world-model-keeper]
ontology_refs: [P1, P2, P3, P4, P5, P6, I5]
---

# Assessment Engine

Carica questa skill quando il consulente:
- Deve fare un assessment (I5): readiness, maturità, OKR, digitale
- Chiede "aiutami a costruire una survey / griglia di intervista"
- Ha dati di assessment e vuole analizzarli
- Deve produrre un report e una roadmap
- Parla di Digital Readiness Checkup

**Intervento di riferimento:** I5 — Assessment, Toolkit & Knowledge Systems
**Ticket medio:** Medio
**Durata tipica:** 1-2 mesi

## Tipi di assessment nel catalogo

| Assessment | Problemi | Contesto ideale | Output |
|-----------|---------|-----------------|--------|
| **Digital Readiness Checkup** | P5, P2 | Aziende che iniziano digital/AI journey | Maturity score + gap analysis + roadmap |
| **AI Readiness (AI Foundation Layer)** | P2, P5 | Aziende con iniziative AI frammentate | 10 presupposti (P01-P10), maturity score per zona |
| **Organizational Assessment** | P1, P3 | Trasformazione organizzativa, new WoW | Mappa cultura/struttura/ruoli/fiducia |
| **OKR Maturity** | P4, P3 | OKR ritualizzati o inesistenti | Gap analysis ciclo OKR + piano |
| **ONA Light (Network Analysis)** | P1, P4 | Silos, collaborazione, innovazione | Mappa collaborazione/confini/hub |
| **Skill Gap Assessment** | P3, P5 | Upskilling, transformation, AI literacy | Gap competenze per ruolo + piano formativo |
| **Workflow Automation Assessment** | — | Knowledge worker che vuole mappare task per automazione/delega | Mappa task × tempo × strumento + matrice delegabile/automatizzabile/strategico + design agenti |

Vedi `references/workflow-automation-assessment.md` per la metodologia completa del Workflow Automation Assessment.

| Assessment | Problemi | Contesto ideale | Output |
|-----------|---------|-----------------|--------|
| **Digital Readiness Checkup** | P5, P2 | Aziende che iniziano digital/AI journey | Maturity score + gap analysis + roadmap |
| **AI Readiness (AI Foundation Layer)** | P2, P5 | Aziende con iniziative AI frammentate | 10 presupposti (P01-P10), maturity score per zona |
| **Organizational Assessment** | P1, P3 | Trasformazione organizzativa, new WoW | Mappa cultura/struttura/ruoli/fiducia |
| **OKR Maturity** | P4, P3 | OKR ritualizzati o inesistenti | Gap analysis ciclo OKR + piano |
| **ONA Light (Network Analysis)** | P1, P4 | Silos, collaborazione, innovazione | Mappa collaborazione/confini/hub |
| **Skill Gap Assessment** | P3, P5 | Upskilling, transformation, AI literacy | Gap competenze per ruolo + piano formativo |

## Struttura standard di un assessment (I5)

```
# Assessment — [Cliente] — [Tipo]

## 1. Obiettivi e Perimetro
[cosa vogliamo scoprire, quali decisioni deve supportare]

## 2. Metodologia
- **Fase 1 — Desk analysis:** documenti, dati esistenti, contesto
- **Fase 2 — Survey:** [N] domande, scala [tipo], target [N] rispondenti
- **Fase 3 — Interviste:** [N] interviste semi-strutturate con stakeholder chiave
- **Fase 4 — Analisi:** pattern, gap, priorità
- **Fase 5 — Report e Roadmap:** documento+presentazione

## 3. Survey Design
[dimensioni, domande, scale]

## 4. Guida Interviste
[domande per stakeholder, struttura]

## 5. Analisi
[criteri di lettura, matrice di priorità]

## 6. Report — Struttura standard
1. Executive Summary
2. Contesto e obiettivi
3. Metodologia
4. Risultati per dimensione
5. Gap Analysis
6. Raccomandazioni e Roadmap
7. Appendice: dati grezzi

## 7. Roadmap
[fasi, tempi, priorità, owner suggeriti]
```

## Procedure

### 1. Survey Design

Per ogni dimensione da valutare, definisci:
- **Domanda** (chiara, non ambigua)
- **Scala** (1-5 Likert, SI/NO/IN PARTE, frequenza)
- **Target** (tutta l'organizzazione / funzione specifica / C-level)

**Regole survey:**
- Massimo 25-30 domande per survey (oltre si perde attenzione)
- Mix di quantitative (scala) e qualitative (open-ended)
- Sempre una domanda aperta finale: "cos'altro dovremmo sapere?"
- Ogni dimensione ha almeno 3 domande per affidabilità

Template dimensioni per **Digital Readiness Checkup** (dal vault):
| Dimensione | Cosa misura | N. domande |
|-----------|-------------|-----------|
| Cultura e mindset | Propensione a sperimentare, tolleranza errore, orientamento dati | 4-5 |
| Competenze digitali | AI literacy, competenze tecniche, data fluency | 4-5 |
| Processi e governance | Policy, ruoli chiari, processi di adozione | 4-5 |
| Dati e tecnologia | Accesso dati, infrastruttura, tool | 3-4 |
| Leadership e strategia | Visione, sponsorship, allineamento | 3-4 |

### 2. Guida Interviste Semi-strutturate

Per ogni stakeholder profile, prepara:

**C-level / Executive:**
- Qual è la vostra visione su [tema]?
- Cosa vi preoccupa di più?
- Cosa avete già provato? Con che risultato?
- Dove vedete la più grande opportunità?
- Quali sono i vincoli reali (budget, tempo, politica interna)?

**Middle management:**
- Come funziona [processo] oggi?
- Cosa funziona? Cosa non funziona?
- Cosa vi servirebbe per fare meglio?
- Come vivete il cambiamento in corso?
- Cosa non viene detto nei meeting?

**Operations / Team:**
- Qual è la tua giornata tipica?
- Cosa ti rallenta?
- Cosa cambieresti subito se potessi?
- Come usi [strumento/processo] oggi?
- Cosa pensi di [iniziativa in corso]?

### 3. Analisi — Matrice di Priorità

Dopo aver raccolto survey e interviste, usa questa matrice per ordinare gli interventi:

| Asse | Descrizione |
|------|-------------|
| **X — Impatto** | Quanto risolvere questo gap cambia le cose? (1-5) |
| **Y — Urgenza** | Quanto è urgente? (1-5) |
| **Bolla — Sforzo** | Quanto è difficile da implementare? (piccola = facile, grande = difficile) |

Risultato: **Quick wins** (alto impatto, basso sforzo) → **Progetti strategici** (alto impatto, alto sforzo) → **Da monitorare** (basso impatto) → **Da evitare**

### 4. Report — Output standard

```
## Assessment Report — [Cliente]

### Executive Summary
[1 paragrafo: cosa abbiamo trovato, cosa raccomandiamo]

### Maturity Score
| Dimensione | Score (1-5) | Giudizio | Priorità |
|-----------|-------------|----------|----------|
| Cultura | 2.3 | Emergente | Alta |
| Competenze | 1.8 | Bassa | Alta |
| Processi | 3.1 | Definito | Media |
| ... | ... | ... | ... |
| **Media** | **2.4** | **Emergente** | |

### Gap Analysis
[tabella: dimensione → situazione attuale → target → gap → azione]

### Roadmap
| Fase | Azioni | Tempo | KPI |
|------|--------|-------|-----|
| Quick win (0-3 mesi) | ... | ... | ... |
| Strategico (3-6 mesi) | ... | ... | ... |
| Trasformativo (6-12 mesi) | ... | ... | ... |

### Raccomandazioni chiave
1. [priorità 1] — perché, cosa serve, chi deve coinvolgere
2. [priorità 2] — ...
```

### 5. Mapping assessment → interventi successivi

Al termine dell'assessment, suggerisci sempre il prossimo passo:

| Risultato assessment | Intervento candidato | Perché |
|---------------------|---------------------|--------|
| Readiness bassa | I4 — Formazione e AI literacy | Prepara il terreno |
| Readiness media | I2 — AI Strategy + OD | Strategia + struttura |
| Readiness alta | I2 + I3 — Strategy + Service Design | Si può andare veloci |
| Gap cultura organizzativa | I1 — Trasformazione Organizzativa | Cambiare modello |
| Gap OKR | I6 — OKR & Allineamento | Strutturare obiettivi |

## Relazione con le altre skill

- **diagnostic-navigator** → la diagnosi Px determina quale assessment fare
- **client-world-model-keeper** → il CWM fornisce il contesto per calibrare survey e interviste
- **intervention-architect** → il risultato dell'assessment alimenta le opzioni di intervento
- **workshop-facilitation-co-designer** → assessment ed interviste possono essere condotti in workshop