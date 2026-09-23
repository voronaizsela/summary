# Output Structures (Stage 3)

Everything here describes what the **user** sees. Working notation — ledger IDs, anchors, segment numbers, stage names, `[calc]`, `NOT STATED IN DOCUMENT` — does not appear in any of it.

## The universal shape

Every output, for every document type, has the same two parts in the same order:

1. **The body — a brief summary in continuous prose.** No headings, no bullets, no numbering, no anchors. A few connected paragraphs carrying the essence: what the document is and what matters in it.
2. **The apparatus — sections, tables and notes.** Structured, labelled, the place for the full detail: figures, obligations, deadlines, caveats, discrepancies and gaps. Headings and table columns in the output language.

No verification block, no counts, no notes on method. Stage 4 runs in full regardless; its record stays in working notes and is quoted only if the user asks for it.

Everything in the body comes from the ledger; everything in the apparatus is consistent with the body. Material the body leaves out moves down into the apparatus — it never leaves the output altogether.

## Writing the body

**Short by design.** Two or three paragraphs for an ordinary document; five or six at the very outside for a large and genuinely complex one — not pages. Length does not scale with the document. A 300-page annual report and a twelve-page contract get bodies of roughly the same size; what differs is the apparatus beneath.

The test: someone who reads only the body knows what the document is, what it establishes, and what in it would change a decision. The test is *not* that they could reconstruct the document — that is what the apparatus is for.

What the body carries, worked into the flow rather than listed:

- what the document is, who issued it or who the parties are, what period or subject matter it covers, what it is for;
- the two or three figures that carry the document — each with its unit, its period and the thing it belongs to, in the same sentence. The rest of the figures go in the table below;
- the obligations or terms that decide the substance, with the conditions attached to them — an obligation without its condition is a different obligation;
- the modality exactly as the source has it — a plan stays a plan, a proposal stays a proposal, an approved decision stays approved;
- the material risk, reservation or basis-of-preparation caveat — the one that changes how the rest should be read. Lesser caveats go into the apparatus;
- a contradiction, if the document contains a significant one: both versions, in words, no adjudication;
- a gap, if the absence is significant, said plainly.

Everything else is not omitted — it is placed below.

How it is written:

- One theme per paragraph. Order by the document's own weight: what it leads with, you lead with. Do not promote a buried caveat to the opening and do not demote a headline finding to the apparatus.
- Legal, regulatory and technical wording is quoted briefly and exactly, inside quotation marks, in the source language. Paraphrase changes scope.
- Connectives carry only relationships the document states. "Выручка снизилась, и в том же квартале сменился директор" is available; "выручка снизилась из-за смены директора" is not, unless the document says so.
- No filler sentences. "В документе рассматриваются различные аспекты деятельности" carries nothing and must not appear. In a short body a filler sentence costs a real one.
- Compression is by selection, not by vagueness. Drop a fact to the apparatus whole; never keep it in the body stripped of its period, its condition or its owner.

## Making the apparatus readable

The apparatus exists so the user does not have to open the document. It fails if it looks like the document.

- **One line per item.** A row in a table, or a bullet of one sentence. If an item needs three sentences, the first sentence is the item and the rest is usually restatement.
- **Front-load the line.** The figure, the deadline or the obligation comes first; the qualification follows on the same line: `Штраф — 5% от стоимости этапа, при просрочке свыше 30 дней, но не более 10% от цены договора.`
- **Tables for anything comparable** — figures across periods, obligations across parties, dates across stages. Prose for anything that is not.
- **Three to eight rows per table** in a typical document. Twelve is a lot. Forty means you are transcribing, not summarizing: keep what is material and say nothing about the rest, or offer it separately.
- **Sections are optional.** Each one earns its place by having material content. Delete the empty ones instead of writing "не указано" in five of them in a row. A gap is worth naming only where the absence itself matters.
- **No nesting.** No sub-bullets under bullets, no sub-sections under sections. One level, everywhere.
- **Bold sparingly**, and only on the thing the eye should land on first — not on every term.
- The whole apparatus for an ordinary document is a screen or two. For a very large and complex one, more — but driven by how many material items exist, never by page count of the source.

## Labels

Write every heading and column natively. Common ones:

| Function | Русский | Українська | English |
|---|---|---|---|
| figures | Ключевые цифры | Ключові цифри | Key figures |
| metric / period / change | Показатель / Период / Изменение | Показник / Період / Зміна | Metric / Period / Change |
| obligations | Обязательства | Зобов'язання | Obligations |
| party / deadline / condition | Сторона / Срок / Условие | Сторона / Строк / Умова | Party / Deadline / Condition |
| dates | Сроки и даты | Строки та дати | Dates and deadlines |
| liability | Ответственность | Відповідальність | Liability |
| termination | Расторжение | Розірвання | Termination |
| basis and caveats | Основа подготовки и оговорки | Основа підготовки та застереження | Basis of preparation and caveats |
| risks | Риски и ограничения | Ризики та обмеження | Risks and limitations |
| discrepancies | Расхождения в документе | Розбіжності в документі | Discrepancies in the document |
| gaps | Не указано в документе | Не зазначено в документі | Not stated in the document |
| decisions / actions | Решения / Поручения | Рішення / Доручення | Decisions / Action items |
| a derived figure | расчёт: … | розрахунок: … | calculated: … |
| percentage points | процентных пункта | відсоткових пункти | percentage points |

Other languages: build the same set natively. Never fall back to the English label.

## Apparatus by document type

These are checklists of what to look for, not sections you must produce. Keep the ones the document fills with material content, delete the rest, add anything it needs. Headers are shown in Russian as the worked example; write them in the output language.

### Financial report / management accounts

```markdown
## Ключевые цифры
| Показатель | Сопоставимый период | Отчётный период | Изменение |
Только показатели, определяющие картину. Изменение, не указанное в документе напрямую: (расчёт: A − B)
## Факторы, названные в документе
Только то, что документ сам называет фактором. Своих объяснений нет.
## Разовые статьи и оговорки
Аудировано или нет, пересчёт прошлых периодов, сноски, «предварительно», «оценка менеджмента».
## Планы и прогнозы
С сохранением модальности: план ≠ решение ≠ прогноз.
## Расхождения в документе
## Не указано в документе
```

### Contract / agreement / terms

```markdown
## Стороны и предмет
Одна-две строки.
## Деньги
Цена, порядок и сроки оплаты, налоги, индексация, валюта.
## Сроки
Вступление в силу, срок действия, этапы, автопролонгация, уведомления.
## Обязательства
| Сторона | Обязательство | Срок | Условие |
Только те, за которыми стоит последствие.
## Ответственность и расторжение
Штрафы и проценты с базой начисления, лимиты, исключения; основания и последствия расторжения.
## На что обратить внимание в тексте
Односторонние права, эксклюзивность, автоматические продления, уступка прав, применимое право и подсудность — если они в договоре есть. Формулировки цитируются, не пересказываются.
## Не урегулировано договором
```

The heading above names where the reader should look; it does not evaluate. "Заказчик вправе расторгнуть договор в одностороннем порядке, уведомив за 10 дней" is the entry. "Это рискованное условие" is not.

For contracts, quote more than you otherwise would. Legal wording does not survive paraphrase.

### Research paper / study / analyst report

```markdown
## Вопрос и метод
Что изучали, на какой выборке, каким методом, за какой период. Три-четыре строки.
## Результаты
Цифры с доверительными интервалами, p-значениями и размерами эффекта ровно так, как они приведены.
## Выводы авторов
Их выводы, в их модальности.
## Ограничения
Почти всегда есть в статье и почти всегда теряется первым.
## Финансирование и конфликт интересов
## Что исследованием не установлено
```

Distinguish throughout between what was measured, what was inferred, and what was speculated.

### Transcript / minutes / meeting record

```markdown
## Решения
| Решение | Кто принял | Срок |
## Поручения
| Что | Ответственный | Срок |
## Разногласия
Кто какую позицию занял. Атрибуция обязательна.
## Открытые вопросы
```

Decisions and action items come first — that is what the reader came for. Participants are named in the prose body, not in a separate list, unless attendance itself is at issue.

### Tender / RFP / statement of work / regulation

```markdown
## Предмет и заказчик
## Требования
| № | Требование | Обязательное или желательное |
Обязательные — все. Желательные — существенные.
## Критерии оценки и веса
## Сроки и этапы
## Требования к оформлению заявки
Комплектность, формат, способ подачи. На этом срезается больше заявок, чем по существу.
## Основания для отклонения
## Неоднозначные положения
Формулировки, допускающие больше одного прочтения: приводится сама формулировка и оба прочтения.
```

### Email thread / document set / multi-source

Keep a separate ledger per document, then merge. Internally, the anchor carries the document (`doc2 §4.2`). In the delivered text, name the document the way the user would name it ("во втором письме", "в приложении к договору").

```markdown
## Хронология
| Дата | Событие | Документ |
Только события, меняющие положение дел.
## Расхождения между документами
Самая ценная часть разбора нескольких документов. Не сглаживать.
## Пробелы
Упомянутые, но отсутствующие приложения; вопросы без ответа; разрывы в переписке.
```

## Verification is not printed

The output ends with the apparatus. No verification block, no coverage counts, no "checked against the source".

Keep the record in working notes all the same — parts processed and parts with no substantive content, rows extracted, statements written and statements confirmed, figures checked, figures derived, contradictions found, gaps. If the user asks how this was checked or what was covered, answer then, in ordinary sentences in the output language, with the real numbers. Never supply a plausible one: an invented count converts an honest summary into a falsely certified one.

Two things do reach the user without being asked for, because they are facts about the source rather than commentary on method: limits on what the summary can be trusted for (figures recognized from a scan, missing or truncated pages, an attachment referred to but not supplied), stated where they belong in the text; and the one-sentence offer below.

## Source references on request

At the very end, one sentence offering the table of extracted facts with references to places in the document — phrased in the output language, e.g. "Могу приложить таблицу фактов со ссылками на конкретные пункты документа."

Give the table only when asked. In it, the reference column is written the way the document labels itself — `п. 4.2`, `Таблица 3, строка «Выручка»`, `с. 14`, `Иванов, 12:04` — not as internal notation. If the user asks about a single claim, answer with the location in a sentence, same wording rules.
