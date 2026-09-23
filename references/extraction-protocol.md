# Extraction Protocol (Stage 2)

Read this before the first segment. The goal of this stage is not to understand the document — it is to **get its contents into a checkable form**. Understanding happens at Stage 3, once the material is laid out and audited.

Extract widely here; select narrowly later. The ledger is not the summary — Stage 3 decides what is material enough to reach the user, and it can only choose from what you recorded. Over-collecting costs a little time; under-collecting costs a reread of the document.

Everything in this file is working notation. The ledger, the IDs and the anchors are yours; none of it appears in the delivered text unless the user explicitly asks for the table of extracted facts.

## What counts as a fact

Record anything falling into these categories:

| Type | What it covers | Why it matters |
|---|---|---|
| `number` | any quantitative value with its frame | most fragile element; corrupted or dropped more than anything else |
| `date` | dates, deadlines, periods, effective dates | period shift is the second most common error after subject substitution |
| `entity` | parties, organizations, roles, products, jurisdictions | "the company" in a document is always a specific company |
| `decision` | decisions taken, approvals granted, resolutions passed | categorically different from a plan — never merge the two |
| `obligation` | duties, requirements, conditions, liabilities, penalties | the core of contracts; conditions attached to them are routinely lost |
| `claim` | assertions, estimates, forecasts, positions | requires preserving modality and attribution |
| `risk` | risks, limitations, caveats, disclaimers | almost always discarded during compression, and often the most important content |
| `fact` | other substantive statements | |
| `link` | connections the document itself states between facts: cause, purpose, condition, consequence, sequence ("в связи с", "в целях", "при условии", "в случае", "после", "в результате") | verbatim quote + IDs of the rows it connects; the only licence for causal or purposive connectives in the output |
| `contradiction` | places where the document conflicts with itself | both versions recorded, plus which location is primary (the document's own precedence rule, else operative clause / main table / body). Internal only: governs which value the output uses, never itself output |
| `empty` | segment with no substantive content | evidence the segment was read rather than skipped |

Do not record: running headers and footers, page numbers, repeated table headers, boilerplate with no specific content, the table of contents (the map covers that).

## Ledger row format

| ID | Seg | Anchor | Type | Subject | Value | Period | Verbatim quote | Note |

- **ID** — sequential, `F-001`, `F-002`, never reused.
- **Anchor** — the most precise locator the document supports, in this order of preference: numbered clause (`§4.2.1`) > table cell (`Table 3, row "Revenue", col "9M2025"`) > page (`p.14`) > heading plus position (`"Risk Factors", 3rd para`) > speaker and timestamp (`Ivanov, 12:04`). Precision matters because Stage 4 requires you to return to this exact spot — and because, when the user asks "where is this from", you must be able to name the place in the document's own wording immediately.
- **Subject** — who or what the fact is about, stated fully enough to stand alone. "Revenue" is not a subject. "Revenue, Retail segment, consolidated" is.
- **Value** — the normalized value for `number` and `date` rows. Its digits must appear in the quote.
- **Verbatim quote** — copied from the source. Joining across a line break is fine; changing a word, an ending, an abbreviation, or the order is not. Truncating at a sentence boundary is fine; cutting out a middle is not — if you need two fragments, make two rows.
- **Note** — your annotation: the applicable footnote, the attached condition, an ambiguity, what the figure relates to.

## Tables

Tables carry the most valuable and most vulnerable data in most documents.

- **Capture the header block first**, as an `entity` row: what the columns are, what units apply, what period is covered, what the stated basis is. Units are typically declared once ("in millions of USD unless otherwise stated") and every cell below is meaningless without them. Carry those units into the `note` of each cell row.
- **One significant cell, one row.** Build the subject from the row label and the column header together.
- **Totals go in as stated, never recomputed.** If a column does not sum to its printed total, record that as a `contradiction` (internal). The output uses the printed total as stated; the discrepancy is not reported.
- **Do not narrate the table in prose at this stage.** Prose summary of a table is where cells quietly merge and disappear.
- Footnote markers inside cells (`*`, `(a)`, `¹`) are part of the cell. Resolve them and record the resolution.

## Footnotes, caveats, and basis of preparation

A footnote is part of the fact, not decoration. `Operating costs of 9,870.1 mn*` carrying `* excluding one-off write-offs of 340.0 mn` is a materially different figure from the number alone. Put the qualifier in the row's `note` and repeat it beside the figure in the summary — in the prose body, in the same sentence as the figure.

The same applies to: "preliminary", "unaudited", "management estimate", "restated", "on a like-for-like basis", "at constant currency", "in 2024 prices", "pro forma". These phrases change what the number means and are the first thing lost in compression.

## Modality and attribution

Preserve the distinctions exactly:

- *resolved / approved* ≠ *plans / is considering / has proposed*
- *shall* ≠ *may* ≠ *is entitled to* ≠ *is expected to*
- *was* ≠ *is anticipated to be* ≠ *is forecast at*

Where a statement belongs to someone — a party to a contract, a speaker, a cited source, management — put the owner in the subject: `Contractor's position: …`. In transcripts, correspondence, and any adversarial document, attribution is mandatory on every row. An unattributed statement in a deposition is a distortion, not a shortcut. In the delivered prose, the owner is carried by ordinary wording of the output language ("подрядчик настаивает, что…", "по оценке менеджмента…").

## Negation

Negation is easy to lose in compression and inverts the meaning completely when lost. Flag rows containing it in the `note` as `NEGATION`. Watch for: "shall not", "except", "other than", "unless", "was not approved", "recommended against", "no longer", "is under no obligation".

## Cross-references

Documents refer to themselves constantly: "as defined in Section 2", "subject to Schedule B", "see note 14". A fact that depends on a cross-reference is incomplete until you resolve it. Either resolve it and record the resolved meaning with both anchors, or record the dependency explicitly in the `note` so the summary can flag it.

If the cross-referenced material is not present in what you were given, record that in the `note`. It reaches the output only as a source limitation (one line after the lead), and only when a figure or term actually used in the output depends on the missing material.

## Multilingual documents

Quotes stay in the source language. Subject and note are in the output language. Terms with an established translation still get the original in parentheses at first use. Where a document exists in two languages and they differ, record a `contradiction` and use the version the document names as governing; if it names none, the version in the output language, attributed in plain words.

Terminology rule for the output: the document's own terms travel unchanged (`EBITDA`, `SLA`, `covenant`, `due diligence` — if that is how the source writes them). Your own vocabulary — everything that is not the document's word — is written natively in the output language. A summary that mixes your English scaffolding into a Russian or Ukrainian text reads as machine output and hides where the document ends and you begin.

## Order and isolation

- Segments are processed **in ascending order, one at a time**.
- Do not skip ahead for context, and do not go back. If a passage is unintelligible without context, record it as-is and describe the problem in the `note`. Connecting things up is Stage 3's job.
- Do not let extraction thin out as you go. The natural tendency is to record less and less toward the end of a long document, which is precisely how the tail of a summary becomes vague. If your rows-per-segment is falling, check whether the document is actually thinning or you are.

## Signs extraction is going wrong

- Rows per segment drop sharply relative to comparable earlier segments.
- Quotes get shorter and tidier — the sign that you have started paraphrasing rather than copying.
- Quotes contain words you cannot find in the source when you look.
- The `note` column fills with conclusions instead of source annotations.
- You find yourself writing a subject from memory of the section rather than from the sentence in front of you.
