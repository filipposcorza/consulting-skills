---
name: mappatura-automazione-workflow
description: "Audit completo del flusso di lavoro di un professionista/knowledge worker: mappatura task reali (da calendario + intervista), classificazione D×A (delegabile × automatizzabile), progettazione agenti autonomi. Output: matrice attività, priorità automazione, specifica primo agente."
category: consulting
---

# Mappatura e Automazione del Workflow

Carica questa skill quando il professionista chiede:
- "Come posso mappare le mie attività quotidiane?"
- "Cosa posso automatizzare del mio lavoro?"
- "Voglio capire cosa delegare e cosa tenere"
- "Costruiamo un agente per la pipeline commerciale/contenuti/etc."
- "Fammi una fotografia della mia settimana lavorativa"

## Metodologia in 3 Fasi

### Fase 1: Mappatura (costruire la fotografia reale)

**Non chiedere al professionista di descrivere la sua settimana — leggila dai suoi strumenti.**

1. **Identifica le Macro-aree candidate:**
   - Pipeline commerciale (lead gen, qualificazione, nurturing, proposte)
   - Contenuti (post, newsletter, blog)
   - Operativa/Amministrazione (fatture, contabilità, agenda, email, CRM)
   - Delivery clienti (workshop, formazione, design, meeting)
   - Studio/Ricerca (formazione, sperimentazione tool)
   - Altro (progetti personali, amministrazione personale)

2. **Leggi i dati reali prima di chiedere:**
   - Calendario Google (leggi tutti i calendari connessi, non solo il primario)
   - Analytics sito (GA, Plausible, etc.)
   - Tool già in uso (LinkedIn, CRM, task manager)
   - **Lead magnet / prodotti gratuiti** (Gumroad, Amazon, etc.) — API REST spesso disponibile, controlla se il professionista offre download gratuiti che generano lead
   - Usa `google_api.py calendar list` per estrarre la settimana reale (non fermarti al calendario primario — leggi anche secondari)
   - **Riconosci i pattern fuori dall'orario lavorativo:** eventi ricorrenti non lavorativi (es. "Giardino e lavori" ogni pomeriggio) rivelano i confini della giornata lavorativa vera

3. **Intervista strutturata per aree:**
   - Fai domande NUMERATE e CONCISE (max 3-4 per turno)
   - Ogni domanda copre un parametro: attività × strumento × frequenza × tempo
   - Esempio: "Come trovi i lead? Fonti? Tempo/settimana?"
   - Lascia spazio a risposte breve — il professionista corregge quello che sbagli

4. **Scrivi la mappa su file persistente:**
   - Struttura: tabella per area con colonne Attività | Strumento | Frequenza | Tempo
   - Segna con ❓ ciò che è ancora da raccogliere
   - Aggiorna dopo ogni risposta

### Fase 2: Classificazione (delegabile × automatizzabile)

1. **Costruisci la matrice D×A per ogni attività:**
   - **D (delegabile a umano)** 1-5: 1=solo tu, 5=può farlo chiunque
   - **A (automatizzabile con agente/software)** 1-5: 1=serve giudizio umano, 5=può farlo un agente

2. **Presenta come tabella compatta:**
   ```
   | Attività | D | A | Note |
   |---|---|---|---|
   | Contenuti | 2 | 5 | Già automatizzato |
   | Qualificazione lead | 3 | 4 | Agente prepara scheda |
   | Workshop live | 1 | 1 | Insostituibile |
   ```

3. **Lascia che il professionista corregga — conosce meglio il suo lavoro.**
   - Pitfall: la classificazione "fatture" vs "contabilità" è spesso diversa (fatture richiedono firma/dati specifici, contabilità sì automatizzabile)

4. **Raggruppa l'output in 4 categorie:**
   - 🟢 Già automatizzato (ottimizzare)
   - 🟡 Automatizzabile subito (candidato agente)
   - 🟠 Parzialmente automatizzabile
   - 🔴 Insostituibile (solo il professionista)

### Fase 3: Progettazione agente

1. **Definisci l'agente candidato** (in base alla priorità):
   - Nome e scopo (es. "Agente Pipeline")
   - Fonti dati (LinkedIn, GA4, CRM, calendario, sito)
   - Trigger (report settimanale automatico, comando on-demand)
   - Output (report, alert, bozze)
   - Integrazioni necessarie (API, OAuth, skill Hermes)

2. **Verifica la fattibilità delle integrazioni:**
   - Google Analytics 4 → API GA4 (richiede scope OAuth aggiuntivo `analytics.readonly` — va aggiunto agli scope Google esistenti, non sostituito, pena perdita accesso a drive/sheets)
   - LinkedIn → MCP LinkedIn (già attivo se disponibile)
   - CRM (Zoho Bigin, HubSpot, Sheets) → API o Google Sheets
   - WordPress → REST API se accessibile
   - Calendario → google_api.py (già configurato)
   - **Gumroad** → API REST con access_token (endpoint: `/v2/products`, GET per sales_count, POST per creazione)

3. **Specifica la segmentazione lead da lead magnet:**
   Se il professionista ha prodotti gratuiti (es. Gumroad), segmenta i lead per prodotto scaricato — ogni prodotto rivela un interesse specifico:
   ```
   | Prodotto | Segmento | Intervento candidato |
   |---|---|---|
   | Refactoring | Change management | I1–I3 |
   | Validazione Rapida | Lean startup | I2–I4 |
   ```
   Chi scarica 2+ prodotti è un lead caldo da alertare immediatamente.

3. **Specifica l'output del report:**
   Formato sintetico per messaggio (Slack/Telegram):
   ```
   ━━━ Pipeline Weekly — [data] ━━━

   📥 LEAD INBOUND (N)
     • Nome — Ruolo @ Azienda — da Fonte (stato)

   📊 WEBSITE
     • Visite: +/-X% vs settimana scorsa
     • Top page: /pagina
     • N form submission

   📣 CONTENUTI
     • Post LinkedIn: N impressions, N engagement
     • Newsletter: +/-N iscritti

   🎯 AZIONI CONSIGLIATE
     • Contattare [lead] entro 48h
     • Preparare proposta per [cliente]
   ```

4. **Struttura di implementazione dell'agente:**
   - **Skill Hermes** (`pipeline-agent`) con tutte le istruzioni, token API e template report
   - **Cron job** — crea con `cronjob(action='create', schedule='0 9 * * 1', prompt='...', skills=['pipeline-agent'])`. Il cron job carica la skill e produce il report come risposta finale, che viene consegnata al canale origin via `deliver='origin'`.
   - **Tool interattivo** (comando on-demand) — carica la skill e risponde a "Fammi il punto pipeline"
   - **Reference files** nella skill: `references/gumroad-api.md` (token, prodotti), `references/weekly-report-template.md` (template output), `references/bigin-schema.md` (placeholder CRM)

## Regole di stile per l'intervista

- Domande NUMERATE, mai più di 4 per turno
- Dopo ogni risposta del professionista: sintetizza in 2-3 righe cosa hai capito
- Non scrivere paragrafi — usa tabelle e liste
- Fai una domanda per messaggio se il professionista risponde secco
- Quando hai abbastanza dati, proponi la classificazione completa e chiedi correzioni
- Leggi il calendario prima di chiedere — evita di far descrivere ciò che puoi vedere

## Pitfall comuni

- **Il calendario racconta una verità diversa da quella che il professionista ricorda.** Leggi SEMPRE i dati reali. Inoltre, presta attenzione agli eventi ricorrenti NON lavorativi (es. "Giardino e lavori" tutti i pomeriggi) — rivelano i confini reali della giornata lavorativa e la capacità di carico del professionista.
- **Fatture ≠ contabilità.** Il professionista spesso distingue tra emissione fattura (manuale) e tenuta contabilità (automatizzabile). Chiedi.
- **Pipeline "zero" è un dato.** Se il calendario non mostra call commerciali né follow-up, è un'info utile — non chiedere perché, prendi atto.
- **Non proporre soluzioni prima di aver classificato tutto.** La tentazione è saltare subito all'agente. Finisci la mappa prima.
- **Il professionista sa correggere la classificazione meglio di te.** Presenta come proposta, non come verità.
- **"Studio" e "Ricerca" sono attività fantasma** — il professionista dice di farlo molto ma non è tracciato a calendario. Chiedi con che strumenti e frequenza.
- **Gumroad come fonte lead è spesso dimenticata.** Il professionista ha prodotti gratuiti che generano lead ma non li traccia come pipeline. Controlla direttamente via API REST (`GET /v2/products?access_token=<token>`) prima di chiedere — estrai sales_count e verifica se i prodotti sono a prezzo zero (lead magnet), non fidarti del ricordo del professionista.
- **Lead magnet zero-price ≠ zero valore.** I download gratuiti generano contatti pre-qualificati spesso più caldi dei lead freddi. Non ignorarli. Segmenta per prodotto scaricato: chi scarica 2+ prodotti è lead caldo.
- **GA4 scope OAuth va aggiunto, non sostituito.** Quando estendi l'autorizzazione Google, includi TUTTI gli scope esistenti più il nuovo, altrimenti perdi accesso a drive/sheets/calendar.
- **Lead magnet zero-price ≠ zero valore.** I download gratuiti generano contatti pre-qualificati spesso più caldi dei lead freddi. Non ignorarli.
- **Delivery non è pipeline.** Workshop e formazione correnti sono consegna, non vendita. Distinguili nel mapping per non gonfiare la pipeline.
- **Cron job: la schedule va in formato cron, non in linguaggio naturale.** `cronjob(action='create', schedule='0 9 * * 1')` funziona; `schedule='every monday 09:00'` no. Usa cron syntax o formato ISO/relativo (`30m`, `2h`).

## Output del processo

1. **File di mappa** (`~/.hermes/work-map/giornata-lavorativa-<nome>.md`) — persistente, evolutivo
2. **Matrice D×A** — classificata e corretta dal professionista
3. **Specifica del primo agente** — integrazioni, trigger, output
4. **Cron job** — report automatico settimanale
5. **Skill Hermes** per l'agente costruito

## Esempi d'uso

### Pipeline agent (da questa sessione)
- Fonti: LinkedIn (MCP), GA4 (API), Zoho Bigin (API), Calendario Google
- Trigger: report lunedì mattina + comando on-demand
- Integrazioni già pronte: LinkedIn MCP, Google Calendar, Google Sheets
- Da configurare: GA4 scope OAuth, Zoho Bigin API credentials

## Relazione con altre skill

- **opportunity-pipeline-navigator** — gestisce la pipeline ESISTENTE (a valle di questa skill)
- **travel-calendar-manager** — lettura calendario Google (riusa lo stesso script google_api.py)
- **time-energy-steward** — complementare per la parte di protezione del deep work