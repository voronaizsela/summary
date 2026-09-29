---
name: document-summary
description: Use when the user asks to summarize a document, asks what is in a document, or asks for its key points, terms or figures.
---

# Document Summary

Produce a structured, accurate summary of a document the user has shared. Accuracy comes first: every statement must be traceable to the document.

## 1. User constraints override the defaults

Before writing, check the request for extra conditions and follow them exactly, even if they conflict with the default format below:
- Length limits ("one page", "half a page", "5 sentences", "short") — respect them strictly. One page is about 400-500 words.
- Form ("bullet points only", "theses", "no tables", "as a table", "as a paragraph").
- Focus ("only financial terms", "only risks", "only section 4", "for a lawyer").
- Language ("in English"). Otherwise, answer in the language the user wrote the request in.

If a constraint makes it impossible to cover everything, keep the most important points and say in one line what was left out.

## 2. Default format

1. **Title**: `# Summary: <document name>`.
2. **Identification line** (1-2 sentences): document type, who approved or signed it, date, number, version, what it replaces or amends.
3. **Sections that mirror the document's structure.** Each block starts with a bold lead-in naming the topic and the section reference, e.g. `**Composition and election (sec. 3)**`, followed by short bullets.
   - One fact per bullet; concrete numbers, deadlines, thresholds and parties.
   - For long lists (competences, obligations, conditions), group items into logical categories with an italic label: `- *Finance:* ...`.
   - Keep original section/clause numbers so the user can check the source.
4. **Figures table(s)** whenever the document contains numbers (see section 3).
5. **Notes on the document text**: inconsistencies between clauses, differences between language versions, typos, missing or ambiguous provisions, internal contradictions. State only what is actually in the text, with clause references. Never speculate about external practice or law you have not checked. Omit this block if there is nothing to report.
6. **Closing line**: form of the document (bilingual, number of pages, signatories), if relevant.

Style: no introductory filler, no conclusions that repeat the summary, no recommendations unless asked.

## 3. Numbers, tables and calculations

If the document contains figures (amounts, percentages, dates, terms, quantities, thresholds):
- Put them into a table: `Parameter | Value | Source (clause/page)`.
- Add derived figures that help the reader (totals, differences, shares, growth rates, per-unit values, deadlines computed from dates, thresholds converted into absolute amounts when the base is given). Mark every derived figure as calculated and show the formula, e.g. `Calculated: 120 / 480 = 25%`.
- If a calculation needs data the document does not contain, do not invent it: state what is missing, or show the formula with a placeholder.
- Run any non-trivial arithmetic in code (Python) when a shell is available instead of computing mentally.

## 4. Verification (mandatory, several passes)

Before sending, re-check everything against the source, not against memory:
1. **Pass 1 — facts**: for each bullet, find the supporting clause. Remove or fix anything you cannot locate.
2. **Pass 2 — numbers**: compare every number, date, percentage and deadline in the summary and tables with the source, digit by digit. Check units and "business days vs calendar days" type distinctions.
3. **Pass 3 — calculations**: recompute every derived figure independently (preferably in code) and confirm it matches.
4. **Pass 4 — attributions and quantifiers**: check who does what (body, role, party) and wording like "at least", "not more than", "all", "majority", "exclusive".
5. **Pass 5 — constraints**: confirm the answer meets every condition the user set (length, form, focus, language).

## 5. No fabrication

- Do not add facts, figures, names, dates or legal interpretations that are not in the document.
- If something is unclear, illegible or ambiguous, say so explicitly instead of guessing.
- Distinguish clearly between what the document says and your own calculations or observations.

## 6. Follow-up questions about the document

For questions like "what does the document say about X": answer directly with the relevant provisions, clause references and figures, using the same rules on tables, calculations, verification and no fabrication. Use the full format only when a summary is requested.
