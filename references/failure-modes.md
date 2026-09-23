# Distortion Catalog and Final Checklist (Stage 4)

Pass A catches numbers that are not in the source. It does **not** catch a correct number attached to the wrong thing. This file is about the second half.

## Nineteen ways summaries go wrong

The first fourteen corrupt the content. The last five corrupt the delivery — and a summary nobody can use fails just as completely as one that is wrong.

**1. Subject substitution.** The figure is right, but attached to the wrong segment, entity, party, or product.
*Check:* for every figure, return to the anchor and read what stands immediately **before** the number in the source sentence.

**2. Period shift.** Nine-month figures presented as annual; prior-year data as current; signing date as effective date.
*Check:* every figure in the output must carry an explicit period. No period means the figure is not ready to publish.

**3. Dropped condition.** "5% penalty" instead of "5% penalty on delays exceeding 30 days".
*Check:* near each fact in the source, look for "if", "provided that", "subject to", "in the event of", "unless", "except where".

**4. Stripped modality.** "Plans to enter" becomes "will enter". "Under consideration" becomes "decided". The least visible and most expensive error in contracts and corporate filings.
*Check:* verb in the summary against verb in the quote, word for word.

**5. False generalization.** Three reported incidents become "systemic failures". Two satisfied customers become "customers are satisfied".
*Check:* a generalization is permissible only if the document itself makes it. Otherwise revert to the enumeration.

**6. False causation.** Adjacency in time or on the page turns into "because of", "driven by", "as a result of". Continuous prose makes this easier to commit than a bulleted list does, because connectives are what prose is made of.
*Check:* the causal link must be stated in the source in words. No words, no link.

**7. Lost negation.** "Recommended against paying a dividend" becomes "recommended a dividend". Complete inversion.
*Check:* go through every row flagged `NEGATION` and locate each one in the output.

**8. Rounding and unit drift.** 12,480.3 mn becomes "roughly 12.5 bn". It looks harmless and it breaks every downstream reconciliation.
*Check:* character-level comparison against the ledger. Separately, confirm no "approximately", "over", "nearly" has appeared that was not in the source — and that none has been removed.

**9. Percent versus percentage points.** 12% to 15% is +3 pp, or +25% relative. "+3%" is wrong.
*Check:* re-read every change expressed as a percentage against its source sentence.

**10. Entity conflation.** Two similar subsidiaries, two similar agreements, two people with the same surname become one.
*Check:* list every proper noun in the output and reconcile against the `entity` rows in the ledger.

**11. "Improved" wording.** A tidier restatement of a legal or technical phrase changes its scope. "Is entitled to terminate" is not "can walk away". "Best efforts" is not "will try".
*Check:* in legal, regulatory, and technical passages, prefer a short exact quotation over your own rendering.

**12. Salience inversion.** Everything is accurate, but the emphasis is yours rather than the document's — a buried caveat gets the opening paragraph, or a headline finding is relegated to the apparatus. In a short body this is the sharpest risk of all: selection *is* the summary.
*Check:* ask what the document itself treats as central, then check that those are the things in the body. Whatever was moved down must be there because the document weights it lower, not because it was harder to phrase.

**13. Omission by fluency.** The text reads well precisely because the awkward, conditional, heavily qualified material was left out. Fluency and faithfulness pull in opposite directions here, and a short prose body raises the pressure to smooth: the caveat is the easiest thing to cut when cutting is the task.
*Check:* scan the ledger for `risk`, `obligation`, and `contradiction` rows and confirm each one appears either in the body or in the apparatus. Brevity in the body is achieved by moving material down, never by dropping it. A fact that is in neither place has been lost.

**14. Tail drift.** Toward the end of a long output, the model starts extending by momentum: conclusions appear that the source never drew, and forward-looking statements arrive unsourced.
*Check:* verify the final third as a separate task, from scratch, against the ledger. Expect to find something.

**15. Notation leak.** Working notation reaches the user: `F-014`, `[§4.2]`, `[p.14]`, `[calc]`, `NOT STATED IN DOCUMENT`, segment numbers, stage names, "ledger", "anchor", "Pass B", or a running commentary on the procedure.
*Check:* read the output as a stranger would. Search it for brackets, for `F-`, for `§`, for any word from this skill's vocabulary. Anchors are used, not shown.

**16. Padding and duplication.** The output is twice the length it needs to be: a sentence announcing what follows, a closing sentence generalizing what came before, "важно отметить", a fact stated in the prose and again in the table below it. Nothing here is false, and the reader still pays for it in attention.
*Check:* delete every sentence whose removal costs the reader nothing, and every second appearance of the same fact. If a paragraph survives the deletion of its first and last sentence, those sentences were padding.

**17. Smuggled opinion.** An evaluation arrives dressed as a summary: "условие рискованное", "показатели выглядят устойчивыми", "стоит обратить внимание на пункт 7". Also its quieter forms — an adjective the document never used, a "всего" or "лишь" before a figure, an ordering that argues a case.
*Check:* every evaluative word in the output must be the document's own. Where you wanted to warn the reader, state the term completely instead, with its consequence — that is what warning looks like in this format.

**18. Template filling.** Sections exist because the format has them, not because the document filled them: five headings in a row saying "не указано", a two-item table given a page, a "Risks" section assembled from generic phrasing because the document had no risks section.
*Check:* every section has material content from the ledger, or it is deleted. A gap is named only where the absence itself matters.

**19. Language drift.** English service vocabulary inside a Russian or Ukrainian output; labels left untranslated; calqued phrasing that no native writer would produce; or, the opposite error, translating the document's own term (`EBITDA`, `SLA`, `covenant`) into something the document never said.
*Check:* every heading, column header and marker is in the output language; every term that came from the document is exactly as the document has it.

## Question-based verification

For each key claim in the output:

1. Write the question it answers: "How much was Retail segment revenue for 9M2025?"
2. Answer that question **from the source**, by going to the anchor and reading its surroundings.
3. Compare that answer to the claim.

Any divergence means the text changes. If the question cannot be answered at the anchor, the claim is resting on something other than what it cites — find the real support or delete the claim.

For every figure, ask all four: **who, how much, when, under what condition.**

## Final checklist

- [ ] Every ledger quote confirmed verbatim against the source
- [ ] Every ledger anchor confirmed to point at its quote
- [ ] Every segment accounted for on the coverage list
- [ ] Every figure in the output verified at its anchor (value, unit, period, subject)
- [ ] Every derived figure declared as a calculation, with operands present in the ledger
- [ ] Every quoted string confirmed verbatim and left in the source language
- [ ] Footnotes and qualifiers travelled with their figures, in the same sentence
- [ ] Verb modality matches the source
- [ ] Negations intact
- [ ] No causal link absent from the text
- [ ] No generalization absent from the text
- [ ] Contradictions presented as contradictions
- [ ] Emphasis proportional to the document
- [ ] Gaps stated plainly where relevant
- [ ] Final third re-verified separately
- [ ] Body is short and is continuous prose: no headings, no lists, no anchors inside it
- [ ] Every figure that did appear in the body carries its unit, period and subject
- [ ] Everything left out of the body is present in the apparatus; everything in the output is in the ledger
- [ ] No working notation anywhere in the output
- [ ] One language throughout, with the document's own terms unchanged
- [ ] No padding: no announcements, no summing-up, no sentence that could be deleted for free
- [ ] No fact stated twice in two places
- [ ] No evaluation, advice or warning that is not the document's own
- [ ] Every section present has material content; no section filled to look complete
- [ ] Checked against the ledger: no material fact — deadline, penalty, condition, cap, caveat, contradiction — left only in the ledger
- [ ] No verification block, no counts, no notes on method in the delivered text
- [ ] Verification record kept in working notes, with real numbers, in case it is asked for
