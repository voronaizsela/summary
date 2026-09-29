---
name: faithful-summary
description: Summarize documents accurately and readably — key facts kept, nothing invented, figures in a table, useful derived metrics calculated and marked as calculated. Use this skill whenever the user asks for a summary, digest, brief, recap, TL;DR, key points, executive summary, "what's important here", "break down this report/contract/filing/paper", or simply hands over a document and asks what it says. Use it especially for financial statements, contracts, tenders, research papers, transcripts and long reports, and whenever accuracy of figures, dates, amounts and obligations matters. Apply it even when the user never says the word "skill".
---

# Faithful Summary

Write a summary the user can act on without opening the document. Keep everything that changes a decision, drop everything that does not, invent nothing.

## Follow the request

The user's instructions outrank the default shape below. If they asked for one page, it is one page. Bullets — bullets. Continuous prose — prose. Only the risks — only the risks. Three sentences — three sentences, and the most material three.

Unstated, default to the shape in the example: title line, a short "what this document is" opener, then thematic sections with tight bullets, plus a figures table when there are figures.

**Output language follows the document**, unless the user writes in or asks for another. Everything visible is in that language — headings, table columns, notes. The document's own terms stay as the document writes them (МСФО, EBITDA, SLA, iXBRL, force majeure). Quotes are never translated inside the quotation marks.

## The default shape

```markdown
Тезисное summary: консолидированная отчётность ПрАТ «Київстар» за 2025 год (МСФО)

Что за документ. Годовая консолидированная отчётность группы «Київстар» (iXBRL)
за год, закончившийся 31.12.2025. В неё входят управленческий отчёт, аудиторское
заключение, основные формы и примечания. Отчётность утверждена к выпуску 30.04.2026.

Ключевые цифры (млрд грн)
| Показатель            | 2025  | 2024  | Изменение |
| Выручка               | 48,0  | 36,9  | +30%      |
| Операционная прибыль  | 18,0  | 15,3  | +18%      |
| Чистая прибыль        | 12,65 | 11,16 | +13%      |

Ключевые сделки
• Uklon (апрель 2025): куплено 97% за 6,63 млрд грн. Гудвил составил 4,62 млрд грн,
  а справедливая стоимость чистых активов — 2,01 млрд грн.
• Helsi: доля выросла до 97,99% после выкупа 28% за 441 млн грн.
• После отчётной даты (2026): Tabletki.ua за ~6,9 млрд грн и провайдер ISP Shtorm
  за ~420 млн грн.

Риски и условные обязательства
• Неотражённые налоговые риски: 2,34 млрд грн (в 2024 году 1,74 млрд).
• Возможные штрафы за несоблюдение повышенных требований к резервному
  энергоснабжению: ~365 млн грн. Резерв не создан, риск оценён как «возможный».
```

How it reads: one fact per bullet, one or two sentences. The figure comes first, its qualification follows on the same line. Sections named after what is in the document, ordered by weight — what the document leads with, you lead with. No section survives without material content: delete it rather than write "не указано" five times. No nesting, no sub-bullets. A fact appears once — if it is in the table, the bullets do not repeat it.

Open on the document itself, not on what you are about to do. Close on the last substantive fact — no summing-up paragraph.

## When the document is not a report

The shape above fits anything with sections and substance. Adjust it when the document is not that:

- **A one-page regulatory notice, order or letter** — answer in two or three sentences. No title line, no sections, no table. Scaffolding on a one-page document is noise.
- **A charter, regulations, contract or any legal text** — sections follow what the reader needs to act: who decides what, thresholds and quorums, terms and deadlines, restrictions, procedures for change. Quote the wording more than elsewhere; legal phrasing does not survive paraphrase.
- **Minutes, a protocol or a transcript** — decisions and action items first, with who and by when. Attribution on every position: an unattributed statement turns one person's view into the record's.
- **A structure chart, an org diagram, a form with no prose** — describe what it shows in a few lines, name the entities and the relationships, and say plainly that it contains nothing else.
- **A machine format** (XML, iXBRL, a zip of them, a .p7s signature wrapper) — unpack and read the underlying data, then summarize the substance, not the format. Name the format once, at the top.
- **Several documents of one series** (quarterly reports, a set of notices) — one summary with the periods side by side in a table, and the changes between them called out. Do not summarize each separately unless asked.

## Figures

- **Any document with financials or a meaningful set of numbers gets a table.** Metric, comparative period, reporting period, change. Prose is for what a table cannot hold.
- **Copy figures exactly**, with unit, period and subject. `1 284,6 млн` does not become "около 1,3 млрд". Ranges stay ranges, "приблизительно" stays.
- **Rescaling for readability is allowed if you declare it once** in the heading: `Финансовые результаты (тыс. грн → в млрд)`, `Ключевые цифры (млрд грн)`. After that, be consistent.
- **Calculate what is useful and say that you did.** Growth rates, margins, shares of total, per-unit figures, organic versus acquired, what is left after one-off items — compute them when they help, from figures in the document, and mark them in ordinary language: `По моим расчётам, операционная маржа снизилась с ~41% до ~37%`, or once at the bottom: `Проценты изменений, доли и «без Uklon» — расчёты по данным отчётности`. Never present a calculation as something the document states.
- **% vs п.п.** A move from 41% to 37% is −4 п.п., not −4%.
- **Footnotes travel with the figure**, in the same sentence: "затраты 9,87 млрд (без разовых списаний)".
- **No currency or unit conversion** unless the document gives the rate or the user asks.

## Never

- **Invent.** Only what the document says. Not what is obviously true, not what such documents usually contain, not the plausible number where the document is silent. If it does not say, write that it does not say — plainly, once, where it matters.
- **Evaluate.** No advice, no warnings, no conclusions the document did not draw, no "это рискованно", "показатели выглядят сильными". Where a term is dangerous, state it completely, with its consequence — that is the warning.
- **Shift meaning.** Plans ≠ decided. May ≠ shall. Estimate ≠ result. Three incidents ≠ "систематические сбои". Adjacent facts ≠ causation. Keep negations intact ("рекомендовал не выплачивать" inverts easily).
- **Smooth over contradictions.** If the document says two different things, give both and say it does not explain the difference.
- **Pad.** No sentence announcing what follows, no "важно отметить", no restating a fact twice.

## Always include, if the document has it

Money and the terms attached to it; deadlines and dates that trigger something; obligations and what happens if they are missed; penalties, caps, liability; grounds and consequences of termination; conditions limiting any of the above; the figures that carry the result and their basis (audited, preliminary, restated, management estimate); caveats that change how a figure reads; contradictions; significant silences.

Leave out: repetition, boilerplate, background the document itself treats as background, figures that change nothing. The test — what breaks for the reader if this is missing? Nothing means leave it out. Something means it stays whole, with its condition. When cutting, cut the item entirely; never keep it stripped of its period, owner or qualifier.

Length is set by how much material the document holds, not by its page count. A 200-page report with six real findings gets a short summary.

## Before sending

- Every figure carries unit, period and subject; every derived figure is marked as yours.
- Every obligation carries its condition and its consequence.
- Nothing material left out; nothing stated twice; no sentence that could be deleted for free.
- No evaluation of your own, no fact that is not in the document.
- One language throughout; the document's own terms unchanged.
- If the source was flawed — scan read by OCR, missing pages, an attachment referred to but not supplied — say so in a line. That is a fact about the document, not a note on method.

Never describe the process: no stages, no "приступаю к анализу", no verification block, no counts.
