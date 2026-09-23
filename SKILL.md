---
name: summary
description: Summarize long documents with zero fabrication and full numeric fidelity, using an evidence-ledger workflow where every claim is anchored to the source, and then answer the user's follow-up questions about the document from the same evidence. Use this skill whenever the user asks for a summary, digest, brief, recap, TL;DR, key points, executive summary, "what's important here", "break down this report/contract/filing/paper/transcript", or hands over a long document and asks what it says — and for every follow-up question about that document afterwards ("а какой там штраф?", "кто отвечает за приёмку?", "что сказано про сроки?"). Use it especially when the document is long (financial report, contract, tender, research paper, deposition, meeting transcript, email thread, policy document) or when accuracy of figures, dates, amounts, obligations, and exact wording matters. Apply it even when the user never says the word "skill" and simply drops a file with "what's in this".
---

# Summary

Ordinary summarization fails in four ways. The model **invents** content that was never in the text. It **corrupts numbers** — rounds them, shifts the period, swaps the unit, attaches a figure to the wrong entity. It **loses the middle and the tail** of long documents. And it delivers **fragments instead of understanding** — a pile of theses and figures lifted from the text, each correct, none connected, so the reader still has to work out what the document actually does.

The first three are removed by one structural rule:

> **The summary is never written from the document. It is written from an evidence ledger of verbatim extracts, and every claim carries an anchor back to where it came from.**

The fourth is removed by the output shape: the summary **explains the document in a logical sequence** — first what it is and what it comes down to, then how its subject works step by step — in short connected prose, with tables only for the numbers. It explains using only connections the document itself makes. It never invents one.

After the summary, the user will ask pointed questions. The ledger is what makes those answers fast and exact, so it outlives the summary (see "Follow-up questions").

**The mechanism is internal.** The ledger, the anchors, the segment numbers, the stage names and the checklists never appear in the delivered text.

## Hard invariants

1. **No outside knowledge.** Only what the document says. A fact that is common knowledge but absent from the text is absent from the output.
2. **Every claim carries an anchor — internally.** A pointer to the source (`§4.2`, `p.14`, `Table 3, "Revenue"`, `Ivanov, 12:04`) exists for every claim. A claim you cannot anchor is a claim you do not write. Anchors are not printed in the summary.
3. **Numbers are copied character for character.** No rounding, rescaling, conversion or recomputation. A number travels with its unit, its period and its subject.
4. **Derived figures are declared** in the output language — `(расчёт: 1 284,6 − 1 010,2)`, `(розрахунок: …)`, `(calculated: …)` — and both operands must be in the ledger.
5. **Silence is not reported.** What the document does not say is not in the summary: no "не указано" sections or lines. Absence is never filled either. Exception: the user asks a direct question the document does not answer — then one plain sentence saying so (see "Follow-up questions").
6. **Internal inconsistencies are not reported and never resolved by invention.** Record both values as a `contradiction` row. In the output use the value from the document's primary location: the document's own precedence rule if it has one; otherwise the operative clause over annexes and summaries, the main statement table over narrative, the body over the abstract or cover letter. If no primary location can be determined, give the value with its origin in plain words ("по данным приложения 2 — …"). Never average, never choose by plausibility, never add a discrepancy note.
7. **Connections come from the document.** The summary may connect facts only by relationships the document states (cause, purpose, condition, consequence, sequence, part of the same mechanism) or by plain structure (this happens before that; these belong to the same party or stage). A "because", "therefore", "in order to", "as a result" that the document does not say is fabrication, however natural it reads.
8. **Output language follows the document**, unless the user asks otherwise or clearly writes in another language. Every heading, table header and label in that language; quotations stay in the source language.
9. **Coverage is exhaustive.** Every segment leaves a trace in the ledger.
10. **No voice of your own.** No assessment, advice or conclusion the document did not draw; no evaluative adjectives. If a term is dangerous, state it completely with its consequence.
11. **Exhaustive coverage, selective output.** The ledger holds everything; the summary holds what the reader needs to understand the document and act on it. The rest stays available for follow-up questions.

## What the user sees

### The principle: explain, then detail

A summary is not a list of what is in the document. It is an answer to "what is this and how does it work", read top to bottom in one pass. Each part answers the question the reader naturally has next.

- **Sequence follows the logic of the subject, not the order of the text and not the order of extraction.** A contract is read as the life of the deal: who agrees to what → how money moves → in what order things happen → what happens if something goes wrong → how it ends. A report is read as result → what the document says produced it → what limits it → what comes next. Per-type sequences are in `references/output-templates.md`.
- **Each section opens with prose that explains its mechanism**: one to four connected sentences saying how this part of the subject works according to the document. "Оплата идёт в два этапа: аванс после подписания и остаток после приёмки работ." — then the table gives the amounts and deadlines.
- **Numbers live in tables; prose carries the meaning.** A section's prose may carry one or two figures if they are the point. Three or more comparable figures go into a table under the prose. A sentence with four numbers in it is a table written badly.
- **Lists only for genuinely parallel items** — grounds for termination, requirements, documents to submit. A list is never a substitute for explaining how things relate.
- **Each fact appears once.** Once in prose, or once in a table — not both.

### Shape of the delivered output

1. **`## Суть`** (in the output language) — one paragraph of 3–5 sentences. What the document is, who issued it or who the parties are, what it covers, and what it comes down to: the central result or the central deal, with at most two headline figures. Someone who reads only this knows what the document is and what it establishes.
2. **Sections in the logical sequence for the document type** — `##` headings only, no nesting. Each: explaining prose first, then a table or list only if the detail needs one. Usually 3–6 sections; only sections the document fills with material content.
3. **Source limitation line** — only if needed (scan, missing pages, attachment not supplied), one line directly after "Суть".

Nothing follows the last section: no offer of a fact table, no closing remarks, no summing-up, no invitation to ask questions.

### What must never appear

- Working notation: ledger IDs, anchors, segment numbers, stage names, `[calc]`, English service vocabulary in a non-English output.
- Sections or lines about what the document does not say, or about inconsistencies inside it.
- Padding: announcements of what follows, "важно отметить", closing generalizations.
- A section that is a bare list of facts with no explanation of how they fit together.
- Verification blocks, counts, notes on method.

### What earns a place

Include, if the document contains it: what the document establishes or reports; money and the terms attached to it; deadlines and dates that trigger something; obligations and what happens if they are missed; liability, penalties, caps; termination; conditions that limit any of the above; the figures that carry the result, with their basis; caveats that change how a figure or finding should be read.

Leave out: restatements, boilerplate, background the document treats as background, figures that change nothing. When unsure, ask what changes for the reader if it is missing. Nothing — leave it out; it remains in the ledger for questions. Something — it stays, in full, with its condition.

Length is set by how much decision-relevant material the document holds, not by its page count.

## The pipeline

Work through the stages in order. They are never narrated to the user.

### Stage 0 — Intake

Establish type, author or parties, date, length, section structure, where the numbers live, and whether anything is physically missing. Split into segments of roughly 8–12 pages at structural boundaries; **never split a table**. Number the segments — this is your coverage checklist. The document type fixes the logical sequence of the output.

### Stage 1 — Map

Skim headings, contents, the first lines of each segment, tables and exhibits. Build an internal map: what each part of the document is for, where the load-bearing material sits, the document's own precedence rule for conflicts if it has one, and — important for the output — **how the parts of the subject relate according to the document**: which obligations belong to which stage, which figures the document ties to which explanation, which conditions govern which terms. Write no conclusions yet.

### Stage 2 — Build the evidence ledger

Segment by segment, **strictly in order, one at a time**. One row per fact:

| ID | Seg | Anchor | Type | Subject | Value | Period | Verbatim quote | Note |
|---|---|---|---|---|---|---|---|---|
| F-014 | 3 | §4.2 | number | Revenue, Retail segment | 1,284.6 mn | 9M2025 | "Revenue in the Retail segment for 9M2025 was 1,284.6 mn." | net of VAT per fn.3 |

Types: `number`, `date`, `entity`, `decision`, `obligation`, `claim`, `risk`, `fact`, `link`, `contradiction`, `empty`.

- **`link` rows record the connections the document states** — "в связи с", "в целях", "при условии", "в случае", "после", "в результате" — with a verbatim quote and the IDs of the rows they connect. These rows are the only licence for connective prose at Stage 3. No `link` row, no causal or purposive connective.
- **Extract, do not compress.** Every number gets its own row. The quote is a copy.
- **A segment with nothing substantive gets one `empty` row.**
- **Do not look ahead or back.** Isolation breaks the momentum that makes faithfulness decay toward the end.
- **Watch the extraction rate.** A sudden drop means the segment is thin or you are drifting.
- **Contradictions are recorded, not delivered** — both values plus which location is primary.

Read `references/extraction-protocol.md` before the first segment.

**Ledger audit before moving on:** every quote verbatim, every anchor pointing at its quote, every value's digits in its quote, every segment accounted for.

**Persist the ledger.** If a file system is available, write the ledger to a working file outside the outputs folder (e.g. `/home/claude/ledger_<document>.md`) so it survives into later turns. Never present or publish it unless the user asks.

### Stage 3 — Compose from the ledger

Close the document. Work only from the ledger.

1. **Select** the decision-relevant rows and resolve contradictions per invariant 6.
2. **Lay out the sequence**: take the per-type sequence from `references/output-templates.md`, drop sections the document does not fill, and assign rows to sections.
3. **For each section, find the mechanism first**: what is the one thing the reader needs to understand about this part, in the document's terms? Using the section's rows and its `link` rows, write 1–4 connected sentences that explain it. Then put the remaining detail into a table or list underneath.
4. **Write each section independently** — not by accumulating onto a running draft.
5. **Write "Суть" last**, from the rows that carry the whole document.

Rules for the prose:

- Entities, figures, units, dates and modality come from the rows unchanged. "Plans to" is not "will". "May" is not "shall".
- Connectives: sequence and structure ("сначала… затем", "для каждого этапа", "со стороны заказчика") are always available; cause, purpose and consequence only with a `link` row, and attributed where the document attributes ("компания объясняет это…", "по условиям договора").
- No generalization the document does not make. No evaluation.
- Compression never buys brevity with vagueness: an item is kept whole or dropped whole.

Structures and worked examples are in `references/output-templates.md`.

### Stage 4 — Verification

**Pass A — figures and quotes.** Every number, date and quoted string: find its row, go to the anchor, re-read the source, confirm value, unit, period, subject. Where a contradiction row exists, confirm the primary value is used.

**Pass B — meaning and connections.** For each key claim, write the question it answers, answer it from the source, compare. Then **check every connective** in the prose: for each "because / so that / as a result / therefore / in connection with", find the `link` row that licenses it. None — rewrite as plain sequence or split into two sentences.

Walk `references/failure-modes.md`. **Verify the final third separately and last.**

**Pass C — the reader's pass.** Read as the user, once, top to bottom:

- Can I say what the document is and what it establishes after reading "Суть"? If not, rewrite it.
- Does each section begin by explaining something, or does it just start listing? A section that is a bare list gets its explaining sentence — built from the ledger — or merges elsewhere.
- Does the order make sense as a story of the subject? Does anything refer to something not yet introduced?
- Are there sentences with three or more figures? Move them to a table.
- Any fact twice? Any padding? Any evaluation of mine? Any line about gaps or inconsistencies? Delete.
- Any figure without period, unit or subject; any obligation without its condition? Repair.

Then, against the ledger: **is there a material fact — deadline, penalty, condition, cap, caveat — that lives only in the ledger?** If yes, it goes in.

### Stage 5 — Deliver

Deliver "Суть" and the sections. Nothing after them. Keep the verification record in working notes with real numbers; give them only if asked, and never a plausible invented count.

## Follow-up questions

The summary is the first turn, not the last. Expect pointed questions — "какой штраф за просрочку?", "кто подписывает акт?", "что там про индексацию?" — and answer each one with the same rigor as the summary.

- **Answer from the ledger, confirm at the source.** Find the rows; if the document is still available, re-read the anchor before answering. If the ledger does not cover the question (because the fact was judged immaterial or the question is narrower than the extraction), go back to the relevant part of the document and extract the fact properly — verbatim quote, anchor — before answering. Never answer from the memory of having read the document.
- **Lead with the answer.** The first sentence answers the question: the figure, the term, the party, the date — with its condition. Then only what is needed to read the answer correctly (the condition, the exception, the linked term).
- **Say where it is.** End with the location in the document's own wording ("пункт 7.3", "приложение 2, таблица «График платежей»"). In follow-up answers this is useful, not clutter.
- **Short and plain.** A few sentences of prose; a small table only if the answer is several comparable figures. No headings, no re-summary, no repetition of the summary.
- **Quote the wording when it matters.** For obligations, rights, penalties and definitions, give the exact phrase in quotation marks — the user is probably asking because the wording matters.
- **If the document does not answer it**, say so in one sentence, then, if it exists, the nearest thing the document does say. Never fill the gap.
- **If the answer requires a calculation**, do it only from ledger figures and show it as a calculation.
- **If the user asks for an opinion or advice** ("это выгодно?", "стоит подписывать?"): first state exactly what the document says on the point; any assessment beyond it is clearly separated and marked as not coming from the document. The summary itself never contains such assessments.
- **If the user asks about an inconsistency directly** ("почему в разделе 3 другая сумма?"), answer what each place says, with locations. Invariant 6 governs the summary, not honest answers to direct questions.
- **Re-verify each answer** like a Pass A/B check: value, unit, period, subject, modality, connective.

## Numbers get their own rules

- **A number travels with its frame:** subject + value + unit + period + condition — in the same sentence in prose, in the header and row label in a table.
- **Preserve the original rendering.** `1 284,6 млн` stays `1 284,6 млн`.
- **% vs percentage points.** 12% → 15% is +3 п.п., or +25% relative. "+3%" is wrong.
- **Do not collapse ranges or hedges**, and never add a hedge the source did not have.
- **Tables enter the ledger cell by cell**, header block first. A column not summing to its total is an internal `contradiction`; the output uses the printed total.
- **Never convert units or currencies** unless asked, and then only at a rate stated in the document.
- **Footnotes are part of the number.**

## When the source is inadequate

Facts about what the user supplied, stated once in one line after "Суть":

- **Scanned document** → OCR it; say the figures were read by character recognition and may contain digit errors.
- **Truncated or missing pages** → say which part you have; summarize only that.
- **A referenced attachment not supplied**, when something in the output depends on it → say it was not provided.

## Calibrating to the request

- **Depth** — "Суть" only; the standard shape; or an exhaustive breakdown with fuller sections. The sequence and the verification do not change.
- **Focus** — if the user asks about specific things (risks, obligations, deadlines), "Суть" stays, and only the relevant sections follow, in the same logical order.
- **Format** — text in chat, or a document file.

Rigor is not a dial. Stages 2 and 4 run every time, for the summary and for every follow-up answer. "Quick" means shorter, not unverified.

## Files

- `references/extraction-protocol.md` — what to extract and how (read before Stage 2)
- `references/output-templates.md` — logical sequence per document type, worked examples, labels (read before Stage 3)
- `references/failure-modes.md` — distortion catalog and final checklist (read before Stage 4 and before answering follow-ups)
