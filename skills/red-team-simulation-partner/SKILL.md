|---
name: red-team-simulation-partner
description: "Simula conversazioni cliente: CEO scettico, CHRO che deve vendere la proposta internamente, stress-test su roadmap e offerte. Prepara il consulente alle obiezioni prima che arrivino."
category: consulting
prerequisites: [consulting/diagnostic-navigator, consulting/intervention-architect, consulting/proposal-designer-ontologico]
ontology_refs: [F1, F2, F3, F4, F5, F6]
---

# Red Team & Simulation Partner

Carica questa skill quando il consulente:
- Ha una bozza di offerta e vuole stress-testarla prima di inviarla
- Si prepara per una call difficile con un cliente
- Vuole simulare una conversazione (vendita, negoziazione, gestione obiezioni)
- Chiede "cosa potrebbe andare storto?"
- Ha una diagnosi/intervento e vuole il punto di vista opposto

## Principio guida

Questa skill non è un "prompt engineer" che genera dialoghi finti. È un **sistema di stress-test** che:
1. Assume punti di vista diversi (CEO, CHRO, IT, sindacato, fornitore)
2. Trova buchi logici, rischi non considerati, presupposti non detti
3. Simula obiezioni reali basate su pattern di esperienza
4. Prepara il consulente a gestire le conversazioni difficili

## Procedure

### 1. Red Team dell'offerta o della proposta

Dato un documento (offerta, proposta, roadmap, diagnosi), applica:

**1a. Check strutturale (dal DOS)**
- La diagnosi viene prima della soluzione? (AP1)
- Il glossario è coerente? (AP2)
- Il cliente è modellato con contesto? (AP7)
- I deliverable hanno Definition of Done? (R3)
- I framework citati esistono in F1-F6? (G2)
- Il ticket è nella fascia Ix corretta? (R10)

**1b. Check posizionamento**
- Questa proposta è coerente con la Visione a 5 Anni?
- Ci sta allontanando dalla boutique di design organizzativo verso commodity?
- Stiamo vendendo giorni o vendendo impatto?

**1c. Roleplay — assumi il punto di vista di:**

```
### 👤 CEO scettico
"Perché dovrei spendere €XX per questo? Il mio team è già sovraccarico, quando lo farebbero? Cosa mi garantisce che funzioni?"
Obiezioni tipiche: ROI non chiaro, tempo perso, già provato e fallito, priorità contrastanti.

### 👤 CHRO che deve vendere la proposta internamente
"Bello, ma il mio CFO non lo approverà mai con questa cifra. Come lo ridimensioniamo? E se il mio CEO mi chiede 'e questo chi è?' "
Obiezioni tipiche: budget visibility, competizione interna, bisogno di vendere l'idea a qualcun altro.

### 👤 Middle manager sulla linea di fuoco
"Un altro progetto? Ma io devo già fare il mio lavoro. Questo è l'ennesimo programma che parte e poi muore."
Obiezioni tipiche: change fatigue, mancanza di tempo, scetticismo su iniziative top-down.

### 👤 Legale / Compliance
"Tutto molto bello, ma come gestiamo i dati? Siamo compliant con AI Act? Chi è responsabile se qualcosa va storto?"
Obiezioni tipiche: rischi normativi, privacy, responsabilità, audit.

### 👤 Il consulente stesso (auto-red team)
"Se questa proposta fallisce, qual è la probabile causa? Cosa sto sottovalutando? Quale informazione non ho e mi servirebbe?"
```

### 2. Simulazione di conversazione

Il consulente può chiedere: "Simula una call con un CEO che ha appena ricevuto la mia proposta".

1. **Carica** il CWM del cliente (contesto, stakeholder, storico)
2. **Carica** la proposta/diagnosi in esame
3. **Esegui** la simulazione a turni:
   - Turno 1: Il cliente fa la prima obiezione (basata sul suo profilo)
   - Turno 2: Il consulente risponde (tu aspetti la risposta — non la scrivi tu)
   - Turno 3: replica del cliente in base alla risposta data
   - Continua fino a risoluzione o cambio di strategia

**Regole della simulazione:**
- Il cliente NON è stupido — ha ragioni valide per le sue obiezioni
- Il cliente ha vincoli reali (budget, tempo, politica interna)
- La simulazione deve essere scomoda per il consulente — altrimenti non serve
- Dopo la simulazione, fornisci un debrief: cosa ha funzionato, cosa no, alternative

### 3. Pre-call briefing con red team

Prima di una call importante, il consulente dice: "Tra 30 minuti ho la call con X".

1. **Leggi** il CWM del cliente
2. **Leggi** lo storico delle interazioni recenti
3. **Produci** un pre-call briefing:

```
## Pre-call briefing — [Cliente]

### Contesto
[stato attuale della relazione]

### Stakeholder presenti
- [Nome] — [tipo: caldo/freddo/neutrale] — [cosa vuole da questa call]

### Obiettivi della call
1. [obiettivo 1]
2. [obiettivo 2]

### Obiezioni probabili
1. [obiezione] → Risposta suggerita: [...]
2. [obiezione] → Risposta suggerita: [...]

### Domande da fare assolutamente
1. [domanda che sblocca informazioni decisive]
2. [domanda che testa l'allineamento]

### Cosa evitare di dire
- [frase/concetto che potrebbe innescare una reazione negativa]

### Segnali di successo
- [cosa deve succedere perché la call sia produttiva]
```

#### 4a. Twin-building — prima della simulazione

Prima di simulare, costruisci un **profilo specifico** della persona da impersonare, basato su dati reali. Questo sostituisce o affina gli archetype generici.

#### Input disponibili (dal più ricco al più povero)

1. **Video/audio pubblici** (YouTube, TEDx, webinar)
   - Estrai transcript: `yt-dlp --write-auto-sub --sub-lang it --skip-download -o "file" "URL"` (sottotitoli autogenerati; attenti al rate-limit 429)
   - Leggi il file `.vtt`, rimuovi tag `<...>` e righe di timing
   - Identifica la persona target (usa marker `>>` nel transcript per separare speaker)
   - Analizza: tono, ritmo, metafore, riempitivi ("eh", "ehm", "diciamo", "no?"), gergo, auto-correzioni

2. **Call transcript interni** (riunioni di team, 1:1)
   - Da Google Docs: `curl -sL "https://docs.google.com/document/d/ID/export?format=txt"` (no auth, plain text)
   - Leggi l'intero file, estrai interventi della persona target
   - **Confronta comportamento pubblico vs privato** — qui emerge la distanza maggiore: linguaggio, bestemmie, assertività, vulnerabilità, humor

3. **Messaggi Slack/email** — cattura stile scritto (lunghezza, formalità, emoji, tempi di risposta, uso maiuscole)

4. **Documenti prodotti** (slide, report, note) — evidenzia come struttura il pensiero e comunica per iscritto

5. **LinkedIn** (profilo + post)
   - Usa `mcp_linkedin_get_person_profile` con `sections: "experience,education,posts"` e `max_scrolls: 15`
   - I post sono la vetrina curata — confrontala con la call transcript per vedere quanto filtra
   - Cerca: libri citati, visione politica, intellettuali di riferimento, chi viene amplificato

#### Assi di profilazione (estrarre per ogni fonte)

```
| Asse | Posizione | Evidenza testuale |
|------|-----------|-------------------|
| Propensione al rischio | Cauto / Esplorativo / Aggressivo | [citazione] |
| Stile comunicativo | Sintetico / Narrativo-metaforico / Analitico / Direttivo | [citazione] |
| Orientamento decisionale | Dati / Gut feel / Consenso / Autorità | [citazione] |
| Assertività | Alta-dosata / Alta-sempre / Media / Bassa | [citazione e pattern di disaccordo] |
| Ascolto | Alto (rilancia metafore altrui) / Medio / Basso (sovrappone) | [pattern di risposta] |
| Trigger emotivi | Cosa lo chiude, alza la voce, evita | [pattern osservato] |
| Priorità implicite | Carriera / Relazioni / Risultati / Controllo | [pattern] |
| Rapporto con incertezza | A suo agio / Ansioso / Evitante | [citazione] |
| Rapporto con incertezza | A suo agio / Ansioso / Evitante | [citazione] |
```

#### Pattern di confronto pubblico/privato

Quando hai sia fonte pubblica che interna, confronta:

| Dimensione | Pubblico | Privato | Gap |
|------------|----------|---------|-----|
| Lingua | Formale/politically correct | Diretta/casuale/bestemmie | Distanza = quanto filtra |
| Assertività | Misurata/sfumata | No secco / disaccordo esplicito | Quanto trattiene in pubblico |
| Humor | Professionale | Privato/irriverente | Confidenza nel gruppo |
| Vulnerabilità | Nessuna | "Sono bollito", "l'ho ammetto" | Fiducia concesso |

#### Stima DISC (output)

Usa il pattern raccolto per stimare la configurazione DISC:
- **D (Dominance)**: comanda o facilita? Impone o coinvolge?
- **I (Influence)**: metafore, entusiasmo, costruzione relazioni?
- **S (Steadiness)**: pazienza, visione lunga, resistenza?
- **C (Conscientiousness)**: rigore metodologico, dati, precisione?

#### Modello a tre registri (pubblico / privato / curato)

Quando hai almeno due fonti (es. video pubblico + call interna), costruisci tre ritratti separati e confrontali:

| Dimensione | Pubblico (YouTube/TEDx) | Privato (call interna/Slack) | Curato (LinkedIn/post) |
|------------|-------------------------|------------------------------|------------------------|
| **Lingua** | Formale, politically correct | Diretta, gergo interno, bestemmie | Saggistica, colta, misurata |
| **Assertività** | Sfumata, condizionale | No esplicito, disaccordo diretto | Ferma ma educata, mai aggressiva |
| **Humor** | Professionale, sorriso | Irriverente, battute tra pari | Raramente presente |
| **Vulnerabilità** | Zero | "Sono bollito", "l'ho ammesso" | Intellettuale, mai personale |
| **Metafore** | Lunghe, didattiche, costruite | Rapide, quasi per scherzo | Letterarie, citazioni colte |
| **Lunghezza interventi** | Turni lunghi, articolati | Turni brevi, alternati | Saggi monografici |

Schema: **Il registro curato (LinkedIn) è ciò che la persona vuole essere. Il registro pubblico (video) è ciò che mostra ai clienti. Il registro privato (call/Slack) è ciò che è.** Il twin realistico usa quest'ultimo come base e calibra verso l'alto in base al contesto.

#### Cosa manca al twin (gap analysis)

Ogni twin ha buchi: dichiara sempre cosa NON si sa:
- Manca il lato sotto stress/pressione
- Manca la comunicazione scritta asincrona
- Manca la dinamica 1:1 specifica con l'interlocutore

Chiedi all'utente di colmare con:
- 3-5 email/messaggi reali
- 1 transcript di call 1:1 con lui
- Esempi di feedback negativo che ha dato

#### System prompt builder

Dopo l'analisi, produci un system prompt strutturato:

```text
Sei [Nome] — [ruolo] in [azienda].
Stile: [comunicativo] — [esempi concreti: usa metafore di X tipo, riempitivi come Y, bestemmia/no, lunghezza frasi]
Decisioni: [come decide, cosa lo convince]
Trigger: [cosa evita, cosa lo fa chiudere]
Con te (interlocutore specifico): [tono, confidenza, dinamica nota]
Limiti del twin: [cosa questo modello NON sa su di lui, cosa manca per raffinarlo: chiama l'utente a colmare con messaggi reali o una call 1:1 trascritta]
```

#### Deliverable: salvataggio nel vault

Dopo l'analisi, offri di salvare il profilo twin nel vault Obsidian:
1. **Nota:** `04 - Artefacts/Artefact - Digital Twin [Nome Cognome].md`
2. **Frontmatter:** data, stato (completo/bozza), tags (digital-twin, personality-profile), related wikilinks
3. **Contenuto:** sezioni come il profilo sopra + citazioni reali + cosa NON fare + scenario trigger
4. **Index:** aggiungi entry nella sezione `📁 Artefacts` dell'index.md
5. **Nota all'utente:** specifica cosa manca e cosa serve per raffinare

## 4. Scenario stress-test per decisioni

Il consulente dice: "Sto pensando di [azione]. Che ne pensi?"

1. **Analizza** la decisione
2. **Applica** 3 prospettive:
   - **Best case:** se funziona, cosa succede?
   - **Worst case:** se fallisce, cosa succede? Qual è il downside massimo?
   - **Most likely case:** qual è lo scenario più probabile?
3. **Valuta** la decisione contro: allineamento visione, impatto su risorse, rischi, alternative

```
## Stress-test: [decisione]

✅ Punti di forza: [...]
⚠️ Rischi: [...]
❌ Se fallisce: [...]

Parere: [andare / non andare / modificare / rimandare] — [motivazione in una frase]
```

## Relazione con le altre skill

- **diagnostic-navigator** → red team della diagnosi: e se il problema fosse un altro?
- **intervention-architect** → red team dell'intervento: opzione migliore?
- **proposal-designer-ontologico** → red team automatico dell'offerta
- **client-world-model-keeper** → CWM per simulazioni contestualizzate
- **opportunity-pipeline-navigator** → stress-test sull'opportunità: conviene?