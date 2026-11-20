---
name: practice-based-consulting
title: Practice-Based Consulting
description: Extract client-facing advice from the user's curated knowledge base (Obsidian vault). Maps client problems and scenarios to the user's documented practices, frameworks, and reflections to generate synthesis-aligned recommendations.
trigger:
  - User presents a real or hypothetical client problem
  - User asks what consulting routes or recommendations are possible given their work
  - Client scenario involves organizational friction, change resistance, system adoption, or process redesign
  - Any request like "in base alle mie pratiche", "dal mio vault", "dalle note che ho"
  - User wants to co-write a preface, article, or book with AI, anchored to vault knowledge
  - User asks for text "da inserire in una slide" (slide-ready copy: course day summaries, faculty bios, intro descriptions)
  - User wants to openly document the methodology of AI‑human collaboration for replication (blog post, GitHub repo)
  - User wants to restructure an existing document through a new conceptual lens (ontology, semantics, AI)
  - User wants to launch or promote a book/artifact combining AI collaboration with lead generation strategy (LinkedIn funnels, educational distribution, landing pages)
  - User asks for an editorial plan or content calendar tied to a specific launch date
  - User says "costruisci una lecture" / "progettiamo le due giornate" / "struttura il workshop"
  - User has a client project and needs to design a training program, workshop agenda, or lecture series
  - Any request to build a modular teaching/training program from vault knowledge
  - User has a client brief and an upcoming kickoff/exploratory call — "prepara domande diagnostiche", "5 domande da fare in call", "domande per la referente"
---

# Practice-Based Consulting

## Reference Files

This skill ships with structured reference files under `references/`:

- **`diagnostic-kickoff-questions.md`** — Preparing structured diagnostic questions for client discovery calls. Covers the progressive trust-building arc (concrete example → organizational context → capability baseline → real success criteria → hidden obstacles), question anatomy, delivery in call, and post-call documentation. Load this when the user has a client brief and an upcoming kickoff call.

- **`consulting-business-development.md`** — Designing consulting offer catalogs (micro/medium/structured tiers), pricing, lead gen routines (1h/week), timeline planning for income targets, DM scripts, and KPI tracking. Load this when the user asks for help building their own freelance/consulting pipeline rather than extracting client advice.

- **`consulting-agent-skill-design.md`** — Designing AI agent skills that augment a consulting practice. Covers the ontology-driven methodology (load DOS + Ontologia Professionale → derive 5-level skill hierarchy → validate against Px/Ix/Fx → create vault project). Use when the user asks "what skills should an agent like you have to support my consulting practice?" (Absorbed from former `ai-augmented-consulting` skill; see `references/ontology-derived-project-creation.md` for a worked example.)

- **`workflow-automation-audit.md`** — Mapping a solo professional's daily work tasks to identify what's delegable, automatable with AI agents, and what stays strategic. Covers the structured interview protocol (domain-by-domain), the Process×Task×Strumento×Tempo matrix, the 3-axis classification (delegabile/automatizzabile/strategico), and the agent design path. Load this when the user wants to audit their own workflow as a precursor to building dedicated agents.

- **`workshop-timing-review.md`** — Reviewing and stress-testing workshop/training agendas for timing, flow, participant energy, and technical risk. Covers online vs in-person session calibration, slide-count heuristic failures, and Miro onboarding time traps. Use when the user asks you to review a slide deck or training syllabus. (Absorbed from former `workshop-design` skill; see `references/timing-analysis-methodology.md` for the calibration tables.)
- **`ontology-framework.md`** — The user's professional ontology: problems (P1–P6), interventions (I1–I6), frameworks (F1–F6), offers, manifesto, and semantic glossary. Load this first when the client problem touches transformation, AI strategy, organizational design, or innovation readiness — it maps directly to the user's consulting categories.
- **`google-slides-extraction.md`** — Technique for reading Google Slides content when `google_api.py` doesn't support the `presentation` service. Workaround: Drive download as PDF + pymupdf text extraction.
- **`book-positioning-copywriting.md`** — Generating provocative titles, payoffs, and positioning copy from vault knowledge for book covers, LinkedIn, and thought leadership. Audience calibration (CEO/HR), provocative levers, and vault-mining patterns for copywriting.
- **`content-redeclination.md`** — Restructuring an existing document through a new conceptual lens (e.g., ontology, AI, semantic capital) using vault knowledge as generative frame.
- **`ai-coauthored-prefaces.md`** — Writing a preface together with an AI agent and openly declaring the collaboration, as a live example of the book's thesis (demonstrative transparency).
- **`book-launch-leadgen.md`** — Launching a book as a lead generation engine: Gumroad distribution, educational distribution (master students as early readers), LinkedIn+Newsletter+landing page funnel, seasonal framing (August "sotto l'ombrellone"), freemium progression. Covers timing around a real-world event anchor and lead gen mechanics.
- **`open-documentation-ai-collaboration.md`** — Document and share the methodology of AI‑human co‑creation as a public artifact (blog post, GitHub repo) to embody transparency and enable replication.
- **`vault-to-chapter-synthesis.md`** — Taking an existing published article (LinkedIn, newsletter) and weaving it together with related vault materials into a coherent book chapter structure. Covers: LinkedIn paywall workaround (r.jina.ai), vault reconnaissance, cross-reference table construction, narrative threading, and the propose-don't-write-first pass pattern.
- **`workshop-lecture-design.md`** — Designing structured workshops, training programs, and lecture series from vault materials. Covers: vault reconnaissance for teaching content, modular architecture (double diamond, waterfall, sprint), theory/practice alternation rhythm, exercise design anchored to client challenges, wikilinking back to source artefacts, and timetable construction. Load this when building a training program rather than extracting advice.
- **`change-charter.md`** — The Change Charter template: a social contract (not a project charter) that defines what changes, why, who's involved, boundaries, progress criteria, rules of engagement, failure scenarios, and duration. From the user's book Cap. 12.2. Use when onboarding a collaborator into a complex system, designing an embedded partnership, or structuring a high-uncertainty transformation.
- **`brief-to-solution-poc.md`** — Generating solution/PoC concepts from workshop/layer briefs with domain calibration. Covers the 5-layer ontology (Identity/Domain/Memory/Entity/Execution) mapped to a specific vertical (AI per il Marketing), with reusable structure per brief and domain-defaulting pitfalls. Load this when the user shares N brief documents and asks for solution concepts.
- **`slide-copy-training.md`** — WRITING the slide-ready copy for training courses (complement to workshop-lecture-design, which designs the structure). Covers the user's non-negotiable rules for slide text (max 5 righe, pronto all'uso, focus ontologico/semantico, compressione iterativa, incorporare redesign forniti in chat), the workflow, and pitfalls (GDrive .gdoc placeholders → "Resource deadlock avoided", no internal logistics in slide copy). Carries the TAG Master "Advanced PM & AI Automation" context: redesign prima giornata (3 fasi: Name-Same-Fame-Pain-Aim-Game, Discovery con Project Owner, mappatura 5 layer ontologia), sintesi docenti (Fullone), fonti vault.

## Templates

This skill provides a reusable client account template:

- **`templates/client-world-model.md`** — Structured template per la mappatura di un cliente/progetto. 12 sezioni: dati progetto, stakeholder map, descrizione progetto, timeline, decisioni e prossimi passi, meeting, rischi e criticità, competitor, link materiali, letteratura, lezioni apprese, trascrizioni. Usalo quando apri un nuovo cliente o un nuovo progetto con un cliente esistente. Copia il template, compilalo via via, e aggiornalo alla chiusura con le lezioni apprese.

## Utility Scripts

This skill provides one utility script:

- **`scripts/estimate_page_count.py`** — Estimate the number of A5 pages a Markdown text will occupy, useful for book layout planning.

Also search the Obsidian vault per the method below.

### Absorbed: Italian Labor Costs (formerly separate skill)

Full workflow and calculator at `references/italian-labor-costs.md` and `references/calcolo-italian-labor-costs.py`.

**Quick reference — CCNL Commercio parameters (2026):**
- 14 mensilità, INPS dipendente 9.19%, INPS ditta ~30%, TFR 1/13.5 = 7.41%
- Moltiplicatore RAL→costo: ~1.389×
- IRPEF scaglioni: 0-28K 23%, 28K-50K 35%, oltre 50K 43%

**The "socio SRL + amministratore + dividendi" alternative** is documented in `references/scenario-ibrido-socio-srl.md`. Use when the user asks about alternatives to hiring an employee.

### Absorbed: Italian Social Enterprise Advisory (formerly separate skill)

Full framework at `references/italian-social-enterprise.md`.

**Three legal models compared:**
| Feature | Impresa Sociale interna | Srl Benefit + ETS | Cooperativa Sociale |
|---------|------------------------|-------------------|---------------------|
| Nuova entità | No | Sì | Sì |
| Attrarre equity | No | Sì | Difficile |
| Fiscalità | 11% IRES se ≤65% commerciale | Standard Srl | 0% IRES su utili reinvestiti |

**Recommendation ladder:** Subito → restare ETS e validare. 12-18 mesi → Impresa Sociale interna. Con investitore → Srl Benefit.

### Absorbed: Financial Modeling for Consulting (formerly separate skill)

Full workflow at `references/financial-modeling.md`.

Build a financial twin of a consulting business: extract revenue data from Google Sheets, simulate future scenarios via Monte Carlo, and calculate net after taxes (forfettario + Inarcassa).

**Key parameters for Italian forfettario:**
| Parameter | Value |
|-----------|-------|
| Coefficiente ATECO | 78% (codice 71.12.10) |
| Aliquota imposta sostitutiva | 15% |
| Contributi Inarcassa | ~20% del reddito lordo |
| Soglia forfettario | €85.000 |

**Traffic light thresholds** for the forfettario cap:
- 🟢 OK: < 50%
- 🟡 META: 50-65%
- 🟠 ATTENZIONE: 65-80%
- 🔴 ALLARME: > 80%

## Goal
Take a client problem and ground the advisory output in the user's actual intellectual work product—their notes, frameworks, articles, and practices—rather than generic consulting templates.

## Method

### 0. Calibrate domain before generating — mandatory first step

Before reading any brief or proposing any solution, **identify the actual audience and domain**. The briefs' framework domain (e.g. generic Project Management) may be different from the students'/audience's domain (e.g. AI for Marketing). Defaulting to the brief's internal framing produces solutions that miss the mark.

- Ask or infer: who is the end audience? What is their course/program/industry?
- Check the file names, slide decks, and context clues for audience metadata (master name, course title, student profiles).
- **If the briefs use a generic framework (5 layers, DOS, ontology), and the audience is a specific vertical (marketing, HR, finance), the solutions MUST be re-contextualized into that vertical** — the framework is the tool, the audience's domain is the application.
- Document your domain assumption explicitly before generating, so it can be verified.

### 1. Understand the client surface
- Capture the client's words verbatim when provided.
- Identify: what the client *says* they feel, what they *actually* describe (behavior, workflow breaks, dependency on external support), and the domain (HR, leadership, agility, AI adoption, etc.).

### 2. Mine the knowledge base — multi-source

**Do not limit to the vault.** Cross-reference all available sources:

| Source | How to access | When to use |
|--------|--------------|-------------|
| **Obsidian vault** | `search_files` + `read_file` | Primary: practices, frameworks, content notes |
| **Google Workspace** (Slides, Docs, Sheets) | `drive download --export-mime application/pdf` + pymupdf for Slides; `google_api.py docs get` for Docs; `google_api.py sheets get` for Sheets | Client presentations, reports, proposals the user shared |
| **Session history** | `session_search` with domain terms | Past video summaries, earlier consulting outputs, decisions about client framing |
| **Web search** | `web_search` | Contextual research to complement client scenarios |

**Google Slides extraction pitfall:** The `google_api.py` does NOT support `presentation` as a service. Workaround: download as PDF (`drive download <ID> --export-mime application/pdf --output /tmp/slides.pdf`) then extract text via `pymupdf` (Python's `fitz` module — `doc = fitz.open(path); [page.get_text() for page in doc]`).

- Search each source with domain terms, emotion signals, and artifact names from the client surface.
- Prefer the user's **practices** and **articles** as primary sources. Avoid summaries of summaries when originals are readable.
- Look for the *most load-bearing file(s)*: the one that names the paradox, the one that lists the counter-practices, the one that defines the user's stance.

### 3. Read deeply before synthesizing
- Open the 1-3 most relevant files fully.
- Note: what principle is being violated? What framework has become dogma? What symptom matches the user's existing diagnosis?

### 4. Multi-modal synthesis — bridge across sources
When the task involves integrating content from multiple origins (e.g. "suggest themes from past video summaries to add to a presentation"), do not default to a single-source approach. Instead:

1. **Extract the target artifact** — Read the Google Slides/Doc/Sheet the user wants to augment
2. **Retrieve past context** — Search session history for relevant prior work (video summaries, past analyses, related content notes). Use `session_search` with key terms from the user's request.
3. **Read vault notes for depth** — Open the full Content notes from Obsidian to get the detail, not just the session summary.
4. **Map across sources** — Create a structured matrix: theme → source (Floridi/Harari/other) → where it fits in the target artifact → why it adds value

**Output formats shift with context:**
- Client scenario → advisory routes (3-5 distinct pathways with vault references)
- Presentation augmentation → theme matrix with slide positions and rationale
- Knowledge synthesis → structured summary with source provenance

### 4. Map, don't just list
- For each client symptom, find the closest practice or principle in the vault.
- Explain the mapping: "what the client describes sounds like X in your work on Y."
- Do not simply enumerate practices. Choose the subset that coheres around a single diagnostic thread.

### 5. Formulate the output
**For consulting scenarios** (client problem → advice):
Offer 3-5 distinct consulting pathways. Each route should:
- Name the leverage point (e.g., "redesign the onboarding ritual", "rebalance the HR-IT boundary").
- Reference a specific vault insight that justifies it.
- State what would change in the client's daily experience, not just in theory.

**For presentation/content augmentation** (existing artifact → enriched):
Produce a structured recommendation matrix. Each row should:
- Name the theme and its source (which video, which author).
- Explain the core concept in 1-2 sentences.
- Specify which slide or section it fits into and why.
- Optionally add a hook or quote for the slide.

**For knowledge synthesis** (raw input → distilled):
Use structured note format with source provenance, key quotes, and explicit mapping to the user's ontology (P/I/F codes).

**For content re-declination** (existing artifact → restructured through a new conceptual lens):
This is the pattern of taking an existing document (book outline, presentation, strategy doc) and re-interpreting/restructuring it using vault knowledge as the generative lens. Typical triggers: "vorrei dargli una declinazione più incentrata su X", "riscrivi questa struttura alla luce di Y", "come cambia questo se lo guardo con Z?".

Method:
1. **Read the target artifact** — Google Doc (`google_api.py docs get <doc_id>`), Slides (PDF+pymupdf), or raw text
2. **Extract its current anatomy** — list chapters/sections as they are now
3. **Mine the vault for thematic resonance** — search for notes on the desired lens (e.g. "ontologia", "semantica", "AI", "capitale semantico", "Floridi", "Harari", "Talisman", "context graph")
4. **Read deeply** — open the 3-5 most load-bearing vault notes fully; understand the user's stance, not just surface keywords
5. **Map vault concepts onto the document's structure** — for each existing chapter, ask: "what does this look like through the new lens?" — discard sections that become irrelevant, add new ones the lens introduces
6. **Produce the restructured outline** — present as:
   - Part/Chapter breakdown with the new lens applied
   - For each section: what vault concept justifies it, what it replaces from the original
   - The "meta-shift" statement: a 1-2 line summary of how the lens changes the document's thesis

Output format: structured outline with Part/Section headers, each annotated with the vault source that inspired it and the shift from the original. End with a "What changes" synthesis paragraph.

**For book launch strategy** (book → lead generation engine):
Produce a phased plan with:
- Anchor event + target date (master start, conference, course launch)
- Channel architecture: LinkedIn posts + newsletter + landing page + delivery (Gumroad)
- Lead gen mechanics: free for first X subscribers → tracked conversion → freemium pricing
- Educational distribution: dedicated coupon for students/master participants as early readers
- Timeline in weeks with clear actions per channel per week
- Landing page strategy: narrative blog post on own domain (not third-party) with embedded form
- Post-launch plan: follow-up content, testimonial collection, transition to paid pricing

Keep the landing page narrative central — the AI co-authorship story IS the conversion mechanism.

**For content marketing calendar** (editorial plan toward a launch):
Produce a week-by-week table with:
- LinkedIn post: hook, angle, CTA
- Newsletter: theme, narrative frame (seasonal), depth
- Parallel action: form status, subscriber count, landing page updates
- The editorial arc: announcement → teaser → behind-the-scenes → countdown → launch → post-launch

**For workshop / lecture design** (vault knowledge → modular training program):
Follow the method in `references/workshop-lecture-design.md`. The output is a structured note with:
- Modular sections with titles, timing, theory/practice split
- Content bullet points for each slide/segment, drawn from vault artefacts
- Hands-on exercises connected to the client's real challenges
- Wikilinks per module back to source vault materials
- Timetable summary at the end (run sheet for the facilitator)
- File saved as `Lecture - <Title> Struttura.md` under the client project folder

Output format per module:

```
### Modulo X.Y — Title (Duration)

| Elemento | Contenuto |
|----------|-----------|
| **Titolo** | ... |
| **Durata** | X min lecture + Y min esercizio |
| **Slide/Keynote** | [da preparare] |

**Contenuti chiave:**
1. Concept + detail

**Esercizio:** description + duration + output

**Riferimenti vault:** [[Wikilink to source]]
```

**For slide-ready course copy** (text to paste into a slide for the user's training courses):
Follow the rules in `references/slide-copy-training.md`. In short: max 5 righe, single text block ready to paste, Italian, one line per phase, openings with impact, ontology/semantics-centered for PM/AI courses (not tools), and always incorporate redesigns the user pastes in chat (they override older vault notes). On "ancora più sintetica", compress immediately — have 3-line and 2-line versions ready.

Do not turn the answer into a knowledge dump. The output is *consulting advice*, *actionable enrichment*, or *a restructured artifact*, not a literature review.

## Pitfalls

- **Domain-defaulting on briefs**: When the user gives you briefs/framework documents and says "generate solutions," the briefs' internal domain (e.g. generic PM) is NOT necessarily the audience's domain (e.g. marketing, HR, finance). Step 0 — calibrate domain first, or the solutions will miss.
- **Dump risk**: Long lists of practices are not a deliverable. Clients pay for judgment.
- **Doctrine drift**: Do not let the user's frameworks become a new dogma. Center the client's reality, even when it contradicts a neat model.
- **Surface matching**: Avoid lukewarm links. If the client problem does not truly resonate with a vault document, say so rather than forcing a connection.
- **Language consistency**: Use the user's terms when they map directly to vault concepts; translate gently when needed for the client's context.
- **No-date trap**: Book launches without a hard anchor date drift. Always pair the launch with a real-world event (master start, conference, course) that gives the date weight beyond the publishing calendar.
- **Form-over-narrative**: The landing page must tell the story first, embed the form second. Leading with the form kills conversion — the AI co-authorship narrative IS the conversion driver.

## Language Rule
Match the user's conversational language. If the user writes in Italian, produce all advisor-facing recommendations in Italian. Only switch to English if explicitly asked.

## Verification
Before responding, confirm:
- [ ] Client's exact words were incorporated or referenced
- [ ] At least one specific vault practice is cited (file or concept)
- [ ] The output reads as advice, not as internal notes
- [ ] Multi-source: if the task spanned multiple sources (Slides + session history + vault), are all sources represented and attributed?
- [ ] Presentation augmentation: is each recommendation mapped to a specific slide or section?
