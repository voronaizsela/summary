# Output Structures (Stage 3)

Everything here describes what the **user** sees. Working notation — ledger IDs, anchors, segment numbers, stage names, `[calc]` — never appears. Neither do sections about inconsistencies inside the document or about what the document does not state. Nothing follows the last section: no offer of a fact table, no closing remark.

## The shape

1. **`## Суть`** — one paragraph, 3–5 sentences: what the document is, who issued it or who the parties are, what it covers, what it comes down to. At most two headline figures.
2. **Sections in the logical sequence of the document type** — each opens with 1–4 sentences explaining how this part of the subject works according to the document, followed by a table or list only if the detail needs one.
3. **Source limitation line** after "Суть", only if needed.

## The principle: explain, then detail

The reader should come away understanding the document, not holding a set of extracts from it. Two failures to avoid, and they pull in opposite directions:

- **A pile of theses** — each section is a list of facts lifted from the text, true and disconnected. The reader has to assemble the picture.
- **Mush** — everything poured into dense paragraphs: four figures, a condition and a decision in one sentence. The reader has to untangle the picture.

The fix for both is the same: **each section says in prose how the thing works, and hands the numbers to a table.**

What the explaining prose may use:

- **Structure and sequence** — always: "работы разбиты на три этапа", "сначала… затем", "со стороны заказчика", "для каждого этапа".
- **Cause, purpose, condition, consequence** — only where the document states them (a `link` row in the ledger), and attributed where the document attributes: "по условиям договора", "компания объясняет это…", "авторы связывают…".
- **The document's own definitions and stated purpose** — quoted briefly when the wording matters.

What it may not use: a "because / so that / therefore / as a result" the document does not say; a generalization the document does not make; any evaluation.

## Worked example — contract

```markdown
## Суть
Договор подряда № 15/2025 от 3 марта 2025 года между ООО «Заказчик» и ООО «Подрядчик» на проектирование и монтаж системы вентиляции склада. Цена работ — **18 400 000 руб. с НДС**, работы выполняются в три этапа и должны быть завершены не позднее 30 сентября 2025 года. Оплата по договору привязана к приёмке каждого этапа.

## Этапы работ
Работы разбиты на три последовательных этапа: по условиям договора каждый следующий начинается после подписания акта по предыдущему.

| Этап | Содержание | Срок окончания |
|---|---|---|
| 1 | Проектирование | 30.04.2025 |
| 2 | Поставка оборудования | 30.06.2025 |
| 3 | Монтаж и пусконаладка | 30.09.2025 |

## Оплата
Заказчик платит аванс 30% от цены договора в течение 5 рабочих дней после подписания. Остальное оплачивается по этапам: за каждый этап — в течение 10 рабочих дней после подписания акта приёмки, за вычетом пропорциональной части аванса.

## Приёмка
По окончании этапа подрядчик передаёт акт, а заказчик в течение 5 рабочих дней подписывает его или направляет мотивированный отказ. Если в этот срок ответа нет, этап «считается принятым».

## Если сроки нарушены
Неустойка предусмотрена для обеих сторон и ограничена предельной суммой.

| Сторона | Нарушение | Неустойка | Предел |
|---|---|---|---|
| Подрядчик | Просрочка этапа | 0,1% стоимости этапа за день | 10% цены договора |
| Заказчик | Просрочка оплаты | 0,05% просроченной суммы за день | 5% цены договора |

## Расторжение
Заказчик вправе отказаться от договора в одностороннем порядке, если просрочка любого этапа превышает 30 дней, уведомив подрядчика за 10 дней. В этом случае оплачиваются только выполненные и принятые работы.
```

The same content as a pile of theses — what must not be produced:

```markdown
## Ключевые условия
- Цена — 18 400 000 руб.
- Аванс 30%.
- Срок — 30.09.2025.
- Приёмка — 5 рабочих дней.
- Неустойка 0,1% в день, не более 10%.
- Односторонний отказ при просрочке более 30 дней.
```

Every line is true, and the reader still does not know who pays the advance and when, what the 5 days apply to, whose delay the 0,1% is for, or 10% of what.

## Worked example — financial report

```markdown
## Суть
Промежуточная неаудированная отчётность ООО «Альфа» по МСФО за 9 месяцев 2025 года. Выручка группы за период составила **4 512,3 млн руб.** против 3 998,0 млн руб. за 9 месяцев 2024 года, чистая прибыль снизилась до 212,4 млн руб. Совет директоров рекомендовал не выплачивать дивиденды за 2025 год.

## Результаты за период
Отчётность сравнивает 9 месяцев 2025 года с тем же периодом 2024 года; суммы в млн руб.

| Показатель | 9М2024 | 9М2025 | Изменение |
|---|---|---|---|
| Выручка | 3 998,0 | 4 512,3 | +514,3 (расчёт) |
| EBITDA | 801,2 | 845,7 | +44,5 (расчёт) |
| Чистая прибыль | 305,9 | 212,4 | −93,5 (расчёт) |

## Что компания называет причинами
Снижение чистой прибыли компания объясняет ростом процентных расходов по кредиту ПАО «Банк». Рост выручки отчётность связывает с открытием 14 новых магазинов в сегменте «Розница».

## Долг
Чистый долг на 30.09.2025 — 2 010,6 млн руб. (на 30.09.2024 — 1 540,0 млн руб.). Кредит ПАО «Банк» компания планирует рефинансировать до конца I квартала 2026 года.

## Оговорки
Отчётность не прошла аудит. Операционные расходы приведены без учёта разовых списаний на 37,2 млн руб.
```

Note: "компания объясняет", "отчётность связывает" — the causal links are there only because the document states them, and they are attributed. Without such statements, the section "Что компания называет причинами" does not exist, and nothing in the output hints at a cause.

## Rules for each part

**Суть.** Connected prose, 3–5 sentences. Identity of the document, then what it establishes. No "в документе рассматривается". At most two figures, each with subject, period and unit.

**Section prose.**
- 1–4 sentences, opens the section, explains the mechanism of this part.
- At most two figures; three or more comparable figures go into a table under it.
- One sentence, one step of the explanation. No chains of "а также… при этом… кроме того".
- Does not refer to anything not yet introduced above.

**Tables.** Only for comparable data. Fixed columns; unit and period in the header where uniform; one number format per column; 3–10 rows.

**Lists.** Only for genuinely parallel items (grounds for termination, requirements, documents). Always introduced by a sentence saying what they are.

**Everywhere.**
- `##` headings only; no sub-sections, no sub-bullets.
- A section with nothing material is deleted, never marked "не указано". A section with one fact merges into its neighbour.
- Each fact appears once.
- Legal, regulatory and technical wording quoted briefly and exactly, in the source language.
- Bold only for the key value in "Суть", sparingly.

## Labels

| Function | Русский | Українська | English |
|---|---|---|---|
| gist | Суть | Суть | In brief |
| figures / results | Результаты за период | Результати за період | Results for the period |
| metric / period / change | Показатель / Период / Изменение | Показник / Період / Зміна | Metric / Period / Change |
| stages | Этапы работ | Етапи робіт | Stages |
| payment | Оплата | Оплата | Payment |
| acceptance | Приёмка | Приймання | Acceptance |
| obligations | Обязательства | Зобов'язання | Obligations |
| party / deadline / condition | Сторона / Срок / Условие | Сторона / Строк / Умова | Party / Deadline / Condition |
| breach | Если сроки нарушены / Ответственность | Відповідальність | Liability |
| termination | Расторжение | Розірвання | Termination |
| special terms | Особые условия | Особливі умови | Special terms |
| stated reasons | Что компания называет причинами | Що компанія називає причинами | Reasons given by the company |
| caveats | Оговорки | Застереження | Caveats |
| plans | Планы | Плани | Plans |
| decisions / actions | Решения / Поручения | Рішення / Доручення | Decisions / Action items |
| a derived figure | расчёт | розрахунок | calculated |
| percentage points | п.п. | в.п. | pp |

Other languages: build the same set natively. Never fall back to the English label.

## Logical sequence by document type

Each sequence follows the questions a reader has, in the order they have them. Sections the document does not fill are dropped; the order of the rest does not change. Headings may be adapted to the document ("Если сроки нарушены" vs "Ответственность сторон") as long as the sequence holds.

### Contract / agreement / terms — the life of the deal

1. **Суть** — parties, subject, price, overall term.
2. **Что именно делается** — scope, stages, deliverables; how the work is divided.
3. **Оплата** — how money moves: advance, stage payments, what triggers each, taxes, indexation.
4. **Приёмка / исполнение** — how performance is confirmed and what happens if it is not.
5. **Обязательства сторон** — the remaining duties that carry a consequence, grouped by party.
6. **Если что-то нарушено** — penalties with base and cap, exclusions, limits of liability.
7. **Расторжение** — grounds, notice, what is paid on exit.
8. **Особые условия** — unilateral rights, exclusivity, auto-renewal, assignment, governing law, jurisdiction; wording quoted, not evaluated.

### Financial report / management accounts — result, then what explains it, then what limits it

1. **Суть** — issuer, period, standard, audit status, headline result.
2. **Результаты за период** — table of the figures that carry the picture.
3. **Что компания называет причинами** — only what the document itself states, attributed.
4. **Долг и финансирование / Денежные потоки** — if material.
5. **Оговорки** — audit, restatements, one-offs, footnotes that change a figure.
6. **Планы и прогнозы** — with modality intact.

### Research paper / study / analyst report — question, method, finding, limits

1. **Суть** — who studied what, and the main finding in the authors' modality.
2. **Как проводилось исследование** — sample, method, period.
3. **Результаты** — prose on what was found, table with values, CIs, p-values as printed.
4. **Выводы авторов** — what they infer, kept apart from what was measured.
5. **Ограничения** — as the authors state them.
6. **Финансирование и конфликт интересов** — if stated.

### Transcript / minutes / meeting record — what was decided and who does what

1. **Суть** — what meeting, when, who, what it was about, what it decided.
2. **Как шло обсуждение** — per agenda item, in order: the question, the positions with attribution, the outcome.
3. **Решения** — table: Решение | Кто принял | Срок.
4. **Поручения** — table: Что | Ответственный | Срок.
5. **Отложено** — only items the participants themselves deferred.

### Tender / RFP / statement of work / regulation — what is wanted, how it is judged, how to apply

1. **Суть** — customer, subject, procedure, key dates.
2. **Что требуется** — prose on the scope, table of mandatory requirements.
3. **Как оцениваются заявки** — criteria and weights.
4. **Сроки и этапы процедуры** — in order.
5. **Как подать заявку** — composition, format, method.
6. **Основания для отклонения**.

### Email thread / document set — how things developed

Keep a separate ledger per document, then merge. Name documents as the user would ("во втором письме", "в приложении к договору").

1. **Суть** — what the set is about and where things stand at the last document.
2. **Как развивались события** — prose in chronological order, with a table Дата | Событие | Документ if there are many steps.
3. **О чём договорились** — attributed.
4. **Позиции сторон на последний момент** — what each side proposes or requires.

Where documents give different values for the same thing, use the latest or the one the set treats as governing (a signed version over a draft) — without a discrepancy section.

## Verification is not printed

No verification block, no counts. Keep the record in working notes; if asked, answer in ordinary sentences with real numbers.

## Follow-up answers

Format for answers to the user's later questions (rules in SKILL.md, "Follow-up questions"):

```markdown
Неустойка подрядчика за просрочку этапа — 0,1% от стоимости просроченного этапа за каждый день, но не более 10% от цены договора. Начисляется она только при просрочке «по вине Подрядчика»; просрочка из-за непредоставления заказчиком исходных данных под неё не подпадает.

Это пункт 8.2 договора.
```

Answer first, then the condition that changes how it reads, then the location in the document's own wording. No headings, no re-summary.
