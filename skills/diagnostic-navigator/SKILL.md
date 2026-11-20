---
name: diagnostic-navigator
description: Mappa input grezzi (note call, email, sintomi) ai problemi P1–P6 dell'Ontologia Professionale. Distingue sintomi da cause da leve di intervento. Non propone mai soluzioni prima della diagnosi.
category: consulting
---

# Diagnostic Navigator

Carica questa skill quando il consulente ti fornisce input grezzi su un cliente o una situazione — note di call, email, sintomi sparsi, descrizioni di contesto.
Il tuo compito è **diagnosticare il problema organizzativo** usando la griglia P1–P6 dell'[[04 - Artefacts/Artefact - Ontologia Professionale.md|Ontologia Professionale]].

## Regola cardinale

**Non proporre soluzioni prima di aver diagnosticato il problema.** (DOS: G1, AP1)
Il consulente decide gli interventi — tu fornisci la lettura diagnostica.

## Step 1 — Carica il framework di riferimento

Prima di analizzare qualsiasi input, leggi:
1. [[04 - Artefacts/Artefact - Ontologia Professionale.md|Ontologia Professionale]] — sezione **Problemi del Cliente (P1–P6)**
2. [[04 - Artefacts/Artefact - DOS (Design Ontology Spec).md|DOS]] — sezioni **Core Objects**, **Relationships**, **Agent Guidelines**, **Anti-Patterns**

Se il vault non è accessibile, usa la knowledge interna dei problemi P1–P6 (definizioni, sintomi, cause, contesti).

## Step 2 — Analizza l'input grezzo

Per ogni input fornito dal consulente (note di call, email, descrizione cliente):

1. **Estrai i fatti oggettivi:**
   - Chi è il cliente (settore, dimensione, maturità)
   - Quali sintomi sono descritti
   - Cosa è già stato fatto (o tentato)
   - Cosa NON è stato detto (gap informativi)

2. **Separa sintomi da cause:**
   - *Sintomo*: ciò che il cliente lamenta ("le decisioni sono lente", "i progetti AI non scalano")
   - *Causa*: ciò che produce il sintomo ("struttura gerarchica rigida", "nessuna governance AI")
   - *Leva*: ciò su cui si può intervenire (cultura, struttura, processi, competenze, tecnologia, leadership)

3. **Mappa ai codici P1–P6:**
   - Identifica il problema primario (quello dominante)
   - Identifica eventuali problemi secondari (comorbilità, es. P2 viene spesso con P5)
   - Assegna un **livello di confidenza** (alto/medio/basso) per ogni codice

4. **Identifica le domande mancanti:**
   - Che informazioni servono per confermare o escludere la diagnosi?
   - Queste diventano domande per il consulente (G4 del DOS)

## Step 3 — Formatta l'output

```
## Diagnosi

### Problema primario: **[Px] — Nome del Problema**
Confidenza: [alta/media/bassa]

**Sintomi riscontrati:**
- [sintomo 1]
- [sintomo 2]

**Cause probabili:**
- [causa 1]
- [causa 2]

**Leve di intervento:**
- [leva 1]
- [leva 2]

### Problemi secondari:
- **[Py] — Nome** (confidenza: [alta/media/bassa])
  - Sintomi: [...]
  - Cause: [...]

### Gap informativi — domande per il consulente:
1. [domanda per chiarire il contesto]
2. [domanda per confermare/escludere Px]
3. [domanda su tentativi già fatti]
```

## Step 4 — Produci il Problem Statement / Diagnostic Statement

Dopo la diagnosi Px, formula un **Diagnostic Statement** che sintetizzi il problema in una frase pronta per il consulente, da usare in proposta o in allineamento con lo stakeholder.

**Formato:**
```
[Attore] sperimenta [sintomo misurabile] 
a causa di [causa diagnosticata, non ipotesi], 
nonostante [tentativo già fatto], 
in un contesto di [vincolo strutturale].
```

Le 4 dimensioni del Problem Statement classico:

| Dimensione | Domanda guida |
|---|---|
| Soggetto | Chi ha il problema? |
| Sintomo | Cosa accade di concreto e misurabile? |
| Impatto | Perché è un problema ora? |
| Vincolo/confine | Cosa NON è incluso nel perimetro? |

Mappa sempre il PS al codice P1–P6 primario.

## Step 5 — Verifica contro gli anti-pattern

Prima di consegnare, controlla:
- ❌ **AP1 — Soluzione senza diagnosi**: non hai scritto "propongo un intervento I2" prima della diagnosi?
- ❌ **AP2 — Glossario fluttuante**: stai usando i termini dell'ontologia o sinonimi inventati?
- ❌ **AP4 — Oggetti orfani**: il problema diagnosticato è fuori dal catalogo P1–P6?
- ❌ **AP7 — Cliente piatto**: hai considerato settore, maturità, contesto?
- ❌ **AP8 — Vault ignorato**: se il cliente ha un progetto o Client World Model nel vault, **leggilo prima** di formulare esempi, ipotesi o il Diagnostic Statement. Il vault contiene dati reali (stakeholder, brief, criticità) che sostituiscono le assunzioni.

## Tabella riassuntiva P1–P6

| Codice | Problema | Dominio prevalente | Stakeholder tipici |
|--------|----------|-------------------|-------------------|
| **P1** | Modello organizzativo non allineato al contesto complesso | OD | C-level, HR |
| **P2** | Trasformazione digitale/AI senza strategia e modello organizzativo | AI | CEO, IT, HR |
| **P3** | Cultura e modelli di lavoro non coerenti col future of work | Future of Work | HR, Manager |
| **P4** | Performance e allineamento strategico deboli | OD | CEO, Team |
| **P5** | Scarso livello di innovation/digital readiness | Innovation | C-level, Team innovazione |
| **P6** | CX/service design incoerenti con strategia e organizzazione | Service Design | Marketing, Operations |

## Relazioni tipiche tra problemi

| Problema primario | Problemi secondari frequenti | Perché |
|------------------|-----------------------------|--------|
| P1 | P3, P4 | Modello rigido produce cultura di controllo e disallineamento |
| P2 | P5, P3 | AI senza strategia rivela immaturità digitale e resistenza culturale |
| P3 | P1, P4 | Cultura non allineata blocca trasformazione organizzativa |
| P4 | P3 | OKR inefficaci spesso nascondono problemi culturali più profondi |
| P5 | P2, P6 | Bassa readiness blocca sia AI adoption che innovazione servizi |
| P6 | P5 | Servizio incoerente rivela gap di readiness organizzativa |

## Esempio

**Input:** "Il cliente è una media impresa manifatturiera (400 dipendenti). Hanno comprato un abbonamento enterprise a ChatGPT, creato 3 copilot in dipartimenti diversi, ma nessuno li usa dopo il primo mese. L'HR non è stata coinvolta, l'IT non ha policy, i manager dicono 'è una moda'. Vogliono capire cosa fare."

**Output:**
```
## Diagnosi

### Problema primario: P2 — Trasformazione digitale/AI senza strategia e modello organizzativo
Confidenza: alta

Sintomi riscontrati:
- Acquisto AI senza strategia (strumento prima della visione)
- Adozione zero dopo il mese iniziale
- HR non coinvolta (nessuna governance delle competenze)
- Nessuna policy IT

Cause probabili:
- Assenza di enterprise AI strategy
- Nessuna integrazione tra strategia aziendale e iniziative AI
- Acquisto top-down senza coinvolgimento utenti

Leve di intervento:
- Strategia: definizione di AI strategy e governance
- Cultura: AI literacy per manager e HR
- Processi: policy chiare per adozione e procurement AI

### Problemi secondari:
- P5 — Scarso livello di innovation readiness (confidenza: media)
  - Sintomi: resistenza dei manager ("è una moda"), nessun processo di adozione
  - Causa: cultura della sperimentazione assente

### Gap informativi:
1. Chi ha preso la decisione di acquisto? (CEO, IT, funzione specifica?)
2. Esiste una strategia digitale/AI formalizzata o è tutto informale?
3. C'è un budget innovation o ogni iniziativa è ad hoc?
```

## Casi d'uso

- **Pre-call briefing:** il consulente ti passa il profilo LinkedIn e appunti del cliente → produci una diagnosi di prima approssimazione
- **Post-call synthesis:** note di prima call → diagnosi strutturata con gap da colmare
- **Email triage:** il consulente inoltra una mail di richiesta → estrai sintomi e mappa a Px
- **Red team della diagnosi altrui:** il consulente ha già una sua ipotesi → stressala: qual è il contro-diagnosi?