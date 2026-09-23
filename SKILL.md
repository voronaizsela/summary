---
name: summary
description: Summarize long documents with zero fabrication and full numeric fidelity, using an evidence-ledger workflow where every claim is anchored to the source. Use this skill whenever the user asks for a summary, digest, brief, recap, TL;DR, key points, executive summary, "what's important here", "break down this report/contract/filing/paper/transcript", or hands over a long document and asks what it says. Use it especially when the document is long (financial report, contract, tender, research paper, deposition, meeting transcript, email thread, policy document) or when accuracy of figures, dates, amounts, obligations, and exact wording matters. Apply it even when the user never says the word "skill" and simply drops a file with "what's in this".
---

# Summary

Ordinary summarization fails in three ways. The model **invents** content that was never in the text. It **corrupts numbers** — rounds them, shifts the period, swaps the unit, attaches a figure to the wrong entity. And it **loses the middle and the tail** of long documents, where the later sections get progressively thinner and vaguer.

This skill removes all three with one structural rule:

> **The summary is never written from the document. It is written from an evidence ledger of verbatim extracts, and every claim carries an anchor back to where it came from.**

The ledger is the whole mechanism. It forces reading to be separated from writing, so the summary cannot be a fluent reconstruction of a vague impression. It makes every sentence auditable in seconds. And it makes the verification pass possible at all — you cannot check a summary against a 300-page document from memory, but you can check it against a ledger.

**The mechanism is internal. The delivered text is a piece of writing, not a work log.** The ledger, the anchors, the segment numbers, the stage names and the checklists live in your working process. The user sees a finished summary in their own language. Read "What the user sees" below before writing a single line of output.

## Hard invariants

These hold regardless of how the request is phrased. They are what the skill is for.

1. **No outside knowledge.** Only what the document says. If a fact is common knowledge and obviously true but absent from the text, it is absent from the summary.
2. **Every claim carries an anchor — internally.** A pointer back to the source (`§4.2`, `p.14`, `Table 3, "Revenue"`, `Ivanov, 12:04`) exists for every single claim in the ledger and is used in verification. A claim you cannot anchor is a claim you do not write. The anchor itself is **not printed in the delivered text** — see "What the user sees".
3. **Numbers are copied character for character.** No rounding, no rescaling to "convenient" units, no currency conversion, no recomputation. A number travels with its unit, its period, and its subject.
4. **Derived figures are declared.** If you computed it, both operands must already be in the ledger, and the output says so in the output language — `(расчёт: 1 284,6 − 1 010,2)`, `(розрахунок: …)`, `(calculated: …)`. Internally you mark it `[calc]`; that notation never reaches the user.
5. **Gaps are named as gaps.** If the document does not say, write it plainly in the output language — "в документе это не указано", "у документі це не зазначено", "the document does not state this". Never "presumably", never "typically in such cases". The internal marker `NOT STATED IN DOCUMENT` is working notation, not output text.
6. **Contradictions are preserved.** If the document says two different things in two places, both go in, in words. You do not adjudicate and you do not average.
7. **Output language follows the document**, unless the user asks for another one or clearly writes in another one. Everything visible is in that language: the running text, every heading, every table header, every label, every note. Quoted material is never translated inside the quotation marks; give a translation alongside if needed.
8. **Coverage is exhaustive.** Every segment of the document leaves a trace in the ledger — even if the trace is "segment 7: table of contents and boilerplate, no substantive content".
9. **No voice of your own.** No assessment, no advice, no conclusions the document did not draw, no "this looks risky", "стоит обратить внимание", "показатели выглядят сильными". Evaluative adjectives are commentary: a figure is 1 284,6 млн, not "solid" or "тревожный". You report what the document says and, where it matters, that it is silent. Nothing else.
10. **Exhaustive coverage, selective output.** The ledger holds everything; the summary holds what a reader needs to act. Reading the whole document is not a reason to reproduce it.

## What the user sees

The user gets a summary — something that replaces reading the document for most purposes, not a second document to read.

- **One language, natural in that language.** No English service vocabulary leaks into a non-English output: no "ledger", "anchor", "Stage 2", "Pass A", "[calc]", "NOT STATED IN DOCUMENT", "coverage", "provenance", "verified". Write the equivalents natively. The *document's own* terminology is different — if the source says `EBITDA`, `SLA`, `force majeure`, keep it exactly as the source has it; that is the document's word, not your jargon.
- **No anchors in the delivered text.** `F-014`, `[§4.2]`, `[p.14]`, segment numbers, ledger IDs and row references stay in your working notes. The text reads as continuous writing, not as an annotated exhibit. Invariant 2 is unchanged — anchors remain mandatory internally, because Stage 4 is impossible without them.
- **No procedure in the delivered text.** No stage names, no numbered walkthrough of how the work was done, no "extraction complete", no "now verifying", no verification block, no counts of segments or checks. If the document is large, at most one neutral line up front that it will take a few minutes — nothing about the internal machinery.
- **The body is a short summary in continuous prose.** Unbroken running text, no headings, no bullets, no numbered steps — and **brief**. It answers "what is this document and what matters in it", not "what does it contain". Detail lives in the apparatus underneath.
- **No padding.** No sentence about what the summary will cover, no closing sentence about what the document "demonstrates", no restating a fact in prose that is already in a table below, no "важно отметить", no hedging that adds nothing. Every sentence carries a fact the reader did not have a moment ago.
- **Traceability on demand.** If the user asks where something came from, give the location in the document's own natural wording ("пункт 4.2", "таблица 3, строка «Выручка»", "стр. 14") and offer the full table of extracted facts with source references as a separate attachment. That table is the only place raw anchors are shown, and only when the user asks for it.

### Shape of the delivered output

1. **Main body — a brief summary in prose.** What the document is, who the parties are, what it establishes or reports, and the handful of things that actually matter — the load-bearing figures, the decisive obligations, the material risk or caveat, a contradiction if there is one. Connected paragraphs, no headings, no lists, no anchors, no service markers.
2. **Below it — the structured apparatus.** Compact sections and tables, per document type: key figures, obligations and deadlines, dates, caveats. Skimmable, one line per item. Formats are in `references/output-templates.md`; every heading and label is written in the output language.

The apparatus is the detail, not the document. A table of the twelve figures that matter, not of every figure in the report. A section exists only if the document has material content for it; empty and near-empty sections are deleted, not filled.

**Nothing critical is dropped anywhere.** The body carries the essence; the apparatus carries the rest of what is decision-relevant; the ledger carries everything else and is available on request. What must never happen is a material fact — a deadline, a penalty, a condition, a liability cap, a caveat that changes how a figure reads — existing only in the ledger.

### What earns a place in the output

Include, always, if the document contains it: money and the terms attached to it; deadlines and dates that trigger something; obligations and what happens if they are missed; liability, penalties, caps; grounds and consequences of termination; conditions that limit any of the above; the figures that carry the result, with their basis; caveats that change how a figure or finding should be read; contradictions; significant silences.

Leave out: restatements of the same fact in different words, procedural and boilerplate passages with no specific content, background the document itself treats as background, figures that change nothing, and anything you are including because it was in the document rather than because it matters. When unsure whether an item is material, ask what changes for the reader if it is missing. Nothing — leave it out. Something — it stays, in full, with its condition.

The length of the output is set by how much decision-relevant material the document holds, not by how long the document is. A 200-page report with six real findings gets a short summary.

There is no verification block. Stage 4 still runs in full, and the counts still exist in your working notes; you simply do not print them. If the user asks how the summary was checked, or what the coverage was, answer then — in plain language, with the real numbers.

## The pipeline

Work through the stages in order. Skipping ahead to the writing stage is the single largest cause of degraded output. The stages are yours; they are never narrated to the user.

### Stage 0 — Intake

Establish the shape of the document before reading it for content: type, author or parties, date, total length, section structure, where the numbers live (tables, appendices, exhibits), and whether anything is missing (truncated pages, unreadable scans, references to attachments that are not present).

Then set the segmentation. Split the document into segments of roughly 8–12 pages, cutting only at structural boundaries — section headings, article breaks, speaker turns, table edges. **Never split a table.** Number the segments and write the list down; this list is your coverage checklist for the rest of the job.

If the document is large, you may say one line to the user about how long it will take and what the output will look like — in their language, with no segment counts, no stage names, no internal terminology.

### Stage 1 — Map

Skim headings, the table of contents, the first lines of each segment, and the list of tables and exhibits. Produce a short structural map: what each section is for, and where the load-bearing material sits. The map is internal.

The map exists so that Stage 2 knows what counts as significant. Without it, extraction degenerates into transcribing whatever happens to be on the page.

**Write no conclusions at this stage.** Structure only. Forming a view of "what the document says" before you have read it carefully is exactly the failure mode this skill exists to prevent.

### Stage 2 — Build the evidence ledger

This is the stage that determines quality. Go segment by segment, **strictly in order, one at a time**, and record facts in a running ledger. One row per fact:

| ID | Seg | Anchor | Type | Subject | Value | Period | Verbatim quote | Note |
|---|---|---|---|---|---|---|---|---|
| F-014 | 3 | §4.2 | number | Revenue, Retail segment | 1,284.6 mn | 9M2025 | "Revenue in the Retail segment for 9M2025 was 1,284.6 mn." | net of VAT per fn.3 |

Types: `number`, `date`, `entity`, `decision`, `obligation`, `claim`, `risk`, `fact`, `contradiction`, `empty`.

The rules that make it work:

- **Extract, do not compress.** Over-collect here. Compression happens at Stage 3, once everything is on the table. A fact that never entered the ledger cannot be recovered later without rereading the document.
- **Every number in the segment gets its own row.** Numbers are the most fragile element and the most costly to get wrong.
- **The quote is a copy.** Not "close enough". You will verify against it later, and a paraphrase recorded as a quote silently destroys that check.
- **A segment with nothing substantive still gets one `empty` row** explaining why. That is how you prove it was read rather than skipped.
- **Do not look ahead or back.** Handle each segment in isolation. This is deliberate: in long generation, faithfulness decays toward the end as the model starts extending by momentum instead of reading. Isolating segments breaks that momentum.
- **Watch your extraction rate.** If segment 9 produced 30 rows and segment 14 produced 4, either segment 14 really is thin, or you have started drifting. Check which.

The ledger is working material. It is never shown to the user unless they ask for it.

Read `references/extraction-protocol.md` before the first segment — it covers tables, footnotes, modality, negation, and attribution in detail.

**Before moving on**, run the ledger audit: walk the ledger top to bottom and for each row confirm the quote is verbatim, the anchor points to where the quote actually is, and the value's digits appear in the quote. Then check the coverage list — every segment accounted for. Fix everything you find. A bad row here becomes an invisible error downstream, because from Stage 3 onward the ledger *is* the truth.

### Stage 3 — Compose from the ledger

Now close the document. From here you work only from the ledger.

First **sort the ledger by materiality**, not by segment: which rows are decision-relevant (see "What earns a place in the output"), and of those, which two or three carry the whole document. Then group the material rows by theme and write each part **independently of the others**. Do not write by accumulating onto a running draft — accumulation preserves more detail but drifts further from the source and loses coherence over long outputs; independent drafting is more stable.

**The prose body:**

- **Short.** Two or three paragraphs for an ordinary document; five or six at the outside for a large and genuinely complex one. If it is running longer, you are retelling the document instead of summarizing it.
- Open with what the document is and what it establishes or reports — in one sentence, not a paragraph of throat-clearing. No "в данном документе рассматривается".
- Carry the two or three figures that decide the picture, the terms that bind, and the caveat or contradiction that changes how the rest should be read. A figure that appears here carries its unit, its period and its subject in the same sentence — brevity never justifies a naked number.
- One theme per paragraph, ordered by the document's own weight. What the document leads with, you lead with.
- No headings, no bullets, no numbering, no anchors, no internal markers inside this part.
- Connect with the ordinary connective tissue of the output language ("при этом", "отдельно оговорено"), never with connectives that assert a relationship the document does not assert.
- Close on the last substantive fact. No summing-up sentence, no assessment, no "таким образом, документ демонстрирует".

**The apparatus:**

- One line per item. Tables for figures, obligations, dates; short sections for caveats, discrepancies and silences. A qualifier travels with its item on the same line, not in a paragraph of its own.
- A section appears only if the document gives it material content. Two obligations means a two-row table, not a page. No section is filled to look complete.
- **A fact appears once.** If it is in the figures table, the prose does not restate it; the prose may name the one headline figure and let the table carry the rest. Duplication is the main way a summary doubles in length while adding nothing.
- Order within each section by weight, not by page number.

**Throughout, prose and apparatus alike:**

- Every sentence traces to one or more ledger rows. You know the anchor; you do not print it.
- The phrasing is yours. The **entities, figures, units, dates, and modality** come from the row unchanged. "Plans to" is not "will". "May" is not "shall".
- Do not merge rows into a generalization unless the document itself generalizes. Three reported incidents are three incidents, not "systemic reliability problems".
- Do not assert causation the text does not assert. "Revenue fell, and the director departed" is not "revenue fell because the director departed".
- No commentary, no evaluation, no recommendations, no warnings of your own. If something in the document is dangerous for the reader, the way to convey that is to state the term accurately and completely, including its consequence — not to add that it is dangerous.
- Include a section on what the document **does not** state whenever the user asked about something the document does not cover, or where the absence is itself significant — titled in the output language.

Compression must never buy brevity with vagueness. Dropping an item is allowed when it is immaterial; keeping an item while stripping its period, condition, owner or qualifier is not. When a thing has to go, it goes whole.

Structures for financial reports, contracts, research papers, transcripts, tenders, and multi-document sets, with label sets per language, are in `references/output-templates.md`.

### Stage 4 — Verification

Two passes, both mandatory. Neither can be done from memory — both require going back to the anchors.

**Pass A — figures and quotes.** Extract every number, date, and quoted string from the draft into a checklist. For each one: find its ledger row, then go to the anchor and read the surrounding sentence in the source. Confirm four things — the value, the unit, the period, and the subject it attaches to. Mark it verified only after you have actually re-read the source. Anything that fails is a fabrication, an undeclared calculation, or a transcription slip; all three get fixed, not explained.

**Pass B — meaning.** Correct figures attached to the wrong subject survive Pass A untouched. Catch them by questioning: for each key claim, write the question it answers ("How much was Retail revenue in 9M2025?"), answer it **from the source only** via the anchor, then compare to what the draft says. Any divergence means the draft is wrong, not the source.

Then walk the distortion checklist in `references/failure-modes.md` — subject substitution, period shift, dropped condition, stripped modality, false generalization, lost negation, and the rest, plus the delivery checks: leaked notation, padding and duplication, smuggled opinion, template filling, mixed language.

**Verify the final third separately and last.** Faithfulness in long outputs falls off measurably toward the end; the closing paragraphs are where invented conclusions and unsupported forward-looking statements cluster. Treat the tail as a fresh task and check it against the ledger from scratch. The continuous-prose body makes this more important, not less: prose drifts more easily than a bulleted list.

**Pass C — the reader's pass.** Fidelity is not enough on its own; the output also has to be worth reading. Read the draft once as the user, not as its author, and cut or fix:

- Any sentence that, removed, costs the reader nothing. Announcements of what follows, closing generalizations, "важно отметить", "документ также содержит информацию о…" — all of it goes.
- Any fact stated twice — once in the prose and again in a table, or twice in two sections. Keep the better placement, delete the other.
- Any evaluation, advice or conclusion that is yours rather than the document's. This is not a stylistic fix: it is a fabrication of a different kind.
- Any figure that arrived without its period, unit or subject; any obligation without its condition; any qualifier that got separated from the item it qualifies. If it cannot be repaired compactly, it still stays — accuracy wins over economy every time they collide.
- Any section that exists because the template has it rather than because the document filled it.

Then the last question, against the ledger, not the draft: **is there a material fact — a deadline, a penalty, a condition, a cap, a caveat, a contradiction — that lives only in the ledger?** If yes, it goes back into the output. That question is what keeps brevity honest.

### Stage 5 — Deliver

Ship the brief prose body and the apparatus. Nothing else: no verification block, no counts, no notes on method, no covering remarks about the document.

Keep the verification record in your working notes — segments processed, rows extracted, claims anchored, figures checked, derived figures, contradictions found, gaps. It is not printed, but it must be real and available, because the user may ask and because the offer below depends on it.

Two things still reach the user in words, in the output language:

- **One sentence offering the table of extracted facts with references** to places in the document — e.g. "Могу приложить таблицу фактов со ссылками на пункты документа." One sentence, at the very end, no elaboration.
- **Anything that limits what the summary can be trusted for**, stated plainly inside the text where it belongs: figures read by character recognition from a scan, missing or truncated pages, an attachment referred to but not supplied. That is not procedural commentary — it is a fact about the source.

If the user asks how it was verified, or what was covered, give the real numbers then. Never supply a plausible one. A count you did not actually keep is worse than no count, because it converts an honest summary into a falsely certified one.

## Numbers get their own rules

Numbers break more often than anything else, so they get extra handling:

- **A number travels with its frame.** Record subject + value + unit + period + condition, never the bare figure. Half of all numeric errors are a correct number wearing the wrong period. In the prose body this is non-negotiable: a figure without its period and its subject in the same sentence is not ready to ship.
- **Preserve the original rendering.** `1 284,6 млн` does not become `1,2846 млрд` and does not become `1284,6`. Keep the source's own separators and unit words. If another form is genuinely useful, give both, with the second marked as a calculation in the output language.
- **Percentages: distinguish % from percentage points.** A move from 12% to 15% is +3 pp, and +25% in relative terms. Writing "+3%" is an error. Use the output language's own term for percentage points ("процентных пункта", "відсоткових пункти", "percentage points"). If the document does not specify, do not specify for it.
- **Do not collapse ranges or hedges.** "40 to 60" stays a range. "approximately 500" keeps its "approximately". And never add a hedge the source did not have.
- **Tables go in cell by cell.** Each significant cell becomes a ledger row, with its column header and row label as the subject. Capture the table's header block first — units and periods are usually declared once, at the top, and cells are meaningless without them. Totals go in as stated; if a column does not add up to its stated total, that is a `contradiction`, not something to correct.
- **Never convert units or currencies** unless asked. If asked, use a rate stated in the document and say in the text that it is a conversion at that rate. No rate in the document means the conversion cannot be made — say that.
- **Footnotes are part of the number.** "Operating costs of 9,870.1 mn*" with "* excluding one-off write-offs" is a different fact from the figure alone. The qualifier travels with the figure into the text, inside the same sentence.

## When the source is inadequate

- **Scanned document with no text layer** → OCR it, and say plainly in the output that the figures were read by character recognition and may contain digit errors.
- **Truncated or missing pages** → say so, state the boundaries of what you actually have, and summarize only that.
- **The user asks for something the document cannot support** ("what's the 2027 forecast?") → say the document does not contain it, then show the nearest relevant thing that it does contain.

Never close a gap with plausible text. The entire value of this skill is that its output can be trusted without rereading the source, and one invented sentence forfeits that for the whole document.

## Calibrating to the request

Ask, or decide yourself when it is obvious, only the things that actually change the work:

- **Depth** — the prose body alone, the body with the usual apparatus, or an exhaustive breakdown that also includes the immaterial detail. Depth changes how much of the apparatus is filled in; the prose body stays short in all three cases, the material facts are present in all three, and the verification never changes.
- **Focus** — general overview, or specific questions (risks, obligations, figures, decisions, deadlines).
- **Format** — text in chat, a document file, or a table of extracted facts alongside.

Rigor is not a dial. Stages 2 and 4 run every time, including when the user says "just quickly". Quick means a shorter summary, not an unverified one.

## Files

- `references/extraction-protocol.md` — what to extract and how (read before Stage 2)
- `references/output-templates.md` — output structures and language labels (read before Stage 3)
- `references/failure-modes.md` — distortion catalog and final checklist (read before Stage 4)
