# Output Structures (Stage 3)

Everything here describes what the **user** sees. Working notation — ledger IDs, anchors, segment numbers, stage names, `[calc]` — never appears. Neither do sections about inconsistencies inside the document or about what the document does not state. Nothing follows the last section: no offer of a fact table, no closing remark.

## The shape

1. **`## Резюме`** — one paragraph, 3–5 sentences: what the document is, who issued it or who the parties are, what it covers, what it establishes. At most two headline figures.
2. **Sections in the logical sequence of the document type** — each opens with 1–4 sentences explaining how this part of the subject is arranged according to the document, followed by a table or list only if the detail needs one.
3. **Source limitation line** after "Резюме", only if needed.

## Register: business, not conversational

The output reads like an analytical note prepared for a manager or a lawyer: neutral, precise, impersonal. Not like a chat message, and not like bureaucratic officialese either.

**Do:**
- Neutral third person, declarative sentences: «Договор устанавливает…», «Оплата производится…», «Компания указывает…».
- Established business and legal vocabulary: «производится», «предусмотрен», «составляет», «в случае», «при условии», «не позднее», «в течение», «по состоянию на».
- The document's own terms exactly as written: «Заказчик», «Подрядчик», «Отчётный период», `EBITDA`.
- Headings as noun phrases: «Порядок оплаты», «Ответственность сторон», «Принятые решения».
- Standard abbreviations where natural: «п. 8.2», «млн руб.», «п.п.», «НДС».

**Don't:**
- Colloquialisms and conversational markers: «по сути», «короче», «то есть», «вообще», «как раз», «просто», «довольно», «штука», «деньги идут», «платит», «разбиты на».
- Questions or conversational phrasing in headings: «Что именно делается», «Если что-то нарушено», «Как подать заявку», «О чём договорились».
- Addressing the reader: «вы», «вам», «обратите внимание», «стоит учесть».
- Exclamations, rhetorical questions, metaphors, emphasis words («очень», «крайне», «всего лишь»).
- Officialese overload in the other direction: chains of genitives and verbal nouns («в целях осуществления обеспечения исполнения»). Business register is precise and readable, not heavy.

Ukrainian and English follow the same register in their own norms: «Договір встановлює…», «Оплата здійснюється…»; "The agreement provides…", "Payment is made…".

## The principle: explain, then detail

The reader should come away understanding the document, not holding a set of extracts from it. Two failures to avoid, and they pull in opposite directions:

- **A pile of theses** — each section is a list of facts lifted from the text, true and disconnected.
- **Mush** — everything poured into dense paragraphs: four figures, a condition and a decision in one sentence.

The fix for both is the same: **each section states in prose how this part is arranged, and hands the numbers to a table.**

What the explaining prose may use:

- **Structure and sequence** — always: «работы выполняются в три этапа», «после подписания акта», «по каждому этапу», «со стороны Заказчика».
- **Cause, purpose, condition, consequence** — only where the document states them (a `link` row in the ledger), and attributed where the document attributes: «согласно условиям договора», «компания связывает это с…», «по оценке авторов».
- **The document's own definitions and stated purpose** — quoted briefly when the wording matters.

What it may not use: a causal or purposive link the document does not state; a generalization the document does not make; any evaluation.

## Worked example — contract

```markdown
## Резюме
Договор подряда № 15/2025 от 3 марта 2025 года между ООО «Заказчик» и ООО «Подрядчик» на проектирование и монтаж системы вентиляции склада. Цена работ составляет **18 400 000 руб. с НДС**; работы выполняются в три этапа со сроком завершения не позднее 30 сентября 2025 года. Оплата производится по мере приёмки этапов.

## Предмет и этапы работ
Работы выполняются в три последовательных этапа. Согласно условиям договора, каждый последующий этап начинается после подписания акта приёмки по предыдущему.

| Этап | Содержание работ | Срок завершения |
|---|---|---|
| 1 | Проектирование | 30.04.2025 |
| 2 | Поставка оборудования | 30.06.2025 |
| 3 | Монтаж и пусконаладочные работы | 30.09.2025 |

## Порядок оплаты
Заказчик перечисляет аванс в размере 30% цены договора в течение 5 рабочих дней с даты подписания. Оставшаяся часть цены оплачивается поэтапно: в течение 10 рабочих дней после подписания акта приёмки соответствующего этапа, за вычетом пропорциональной части аванса.

## Порядок приёмки
По завершении этапа Подрядчик направляет акт приёмки; Заказчик в течение 5 рабочих дней подписывает его либо направляет мотивированный отказ. При отсутствии ответа в указанный срок этап «считается принятым».

## Ответственность сторон
Договор предусматривает неустойку для обеих сторон с ограничением предельной суммой.

| Сторона | Основание | Размер неустойки | Предельная сумма |
|---|---|---|---|
| Подрядчик | Нарушение срока этапа | 0,1% стоимости этапа за каждый день | 10% цены договора |
| Заказчик | Нарушение срока оплаты | 0,05% просроченной суммы за каждый день | 5% цены договора |

## Порядок расторжения
Заказчик вправе отказаться от исполнения договора в одностороннем порядке при нарушении срока любого этапа более чем на 30 дней, уведомив Подрядчика не менее чем за 10 дней. В этом случае оплате подлежат только выполненные и принятые работы.
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

And the same content in a conversational register — also not acceptable: «Деньги идут в два захода: сначала 30% аванса, потом остальное — по мере того как принимают этапы. Если заказчик молчит 5 дней, этап просто считается принятым.»

## Worked example — financial report

```markdown
## Резюме
Промежуточная неаудированная отчётность ООО «Альфа» по МСФО за 9 месяцев 2025 года. Выручка группы за отчётный период составила **4 512,3 млн руб.** (9 месяцев 2024 года: 3 998,0 млн руб.); чистая прибыль снизилась до 212,4 млн руб. Совет директоров рекомендовал не выплачивать дивиденды за 2025 год.

## Результаты за отчётный период
Показатели приведены в сравнении с аналогичным периодом 2024 года, млн руб.

| Показатель | 9М2024 | 9М2025 | Изменение |
|---|---|---|---|
| Выручка | 3 998,0 | 4 512,3 | +514,3 (расчёт) |
| EBITDA | 801,2 | 845,7 | +44,5 (расчёт) |
| Чистая прибыль | 305,9 | 212,4 | −93,5 (расчёт) |

## Факторы, указанные компанией
Снижение чистой прибыли компания связывает с ростом процентных расходов по кредиту ПАО «Банк». Рост выручки, согласно отчётности, обусловлен открытием 14 магазинов в сегменте «Розница».

## Долг и финансирование
Чистый долг по состоянию на 30.09.2025 составил 2 010,6 млн руб. (на 30.09.2024 — 1 540,0 млн руб.). Компания планирует рефинансировать кредит ПАО «Банк» до конца I квартала 2026 года.

## Оговорки
Отчётность не прошла аудит. Операционные расходы приведены без учёта разовых списаний в размере 37,2 млн руб.
```

«Компания связывает», «согласно отчётности» — the causal links appear only because the document states them, and they are attributed. Without such statements the section «Факторы, указанные компанией» does not exist.

## Rules for each part

**Резюме.** Connected prose, 3–5 sentences. Identity of the document, then what it establishes. No «в данном документе рассматривается». At most two figures, each with subject, period and unit.

**Section prose.**
- 1–4 sentences, opens the section, states how this part is arranged.
- At most two figures; three or more comparable figures go into a table under it.
- One sentence — one step of the explanation. No chains of «а также… при этом… кроме того».
- Does not refer to anything not yet introduced above.

**Tables.** Only for comparable data. Fixed columns with business headings; unit and period in the header where uniform; one number format per column; 3–10 rows.

**Lists.** Only for genuinely parallel items (grounds for termination, requirements, documents). Always introduced by a sentence stating what they are.

**Everywhere.**
- `##` headings only, as noun phrases; no sub-sections, no sub-bullets.
- A section with nothing material is deleted, never marked «не указано». A section with one fact merges into its neighbour.
- Each fact appears once.
- Legal, regulatory and technical wording quoted briefly and exactly, in the source language.
- Bold only for the key value in «Резюме», sparingly.

## Labels

| Function | Русский | Українська | English |
|---|---|---|---|
| summary | Резюме | Резюме | Summary |
| results | Результаты за отчётный период | Результати за звітний період | Results for the period |
| metric / period / change | Показатель / Период / Изменение | Показник / Період / Зміна | Metric / Period / Change |
| scope and stages | Предмет и этапы работ | Предмет та етапи робіт | Scope and stages |
| payment | Порядок оплаты | Порядок оплати | Payment terms |
| acceptance | Порядок приёмки | Порядок приймання | Acceptance procedure |
| obligations | Обязательства сторон | Зобов'язання сторін | Obligations of the parties |
| party / deadline / condition | Сторона / Срок / Условие | Сторона / Строк / Умова | Party / Deadline / Condition |
| liability | Ответственность сторон | Відповідальність сторін | Liability |
| termination | Порядок расторжения | Порядок розірвання | Termination |
| special terms | Особые условия | Особливі умови | Special terms |
| stated factors | Факторы, указанные компанией | Фактори, зазначені компанією | Factors stated by the company |
| debt | Долг и финансирование | Борг та фінансування | Debt and financing |
| caveats | Оговорки | Застереження | Qualifications |
| plans | Планы и прогнозы | Плани та прогнози | Plans and outlook |
| discussion | Ход обсуждения | Хід обговорення | Discussion |
| decisions / actions | Принятые решения / Поручения | Ухвалені рішення / Доручення | Decisions / Action items |
| a derived figure | расчёт | розрахунок | calculated |
| percentage points | п.п. | в.п. | pp |

Other languages: build the same set natively, in business register. Never fall back to the English label.

## Logical sequence by document type

Each sequence follows the order in which a reader needs the information. Sections the document does not fill are dropped; the order of the rest does not change. Headings may be adjusted to the document's own terminology (e.g. «Ответственность Исполнителя») but stay noun phrases in business register.

### Contract / agreement / terms

1. **Резюме** — parties, subject, price, overall term.
2. **Предмет и этапы работ** — scope, stages, deliverables.
3. **Порядок оплаты** — advance, stage payments, what triggers each, taxes, indexation.
4. **Порядок приёмки** (or «Порядок исполнения») — how performance is confirmed and the consequences of refusal or silence.
5. **Обязательства сторон** — remaining duties that carry a consequence, grouped by party.
6. **Ответственность сторон** — penalties with base and cap, exclusions, limits of liability.
7. **Порядок расторжения** — grounds, notice, settlement on exit.
8. **Особые условия** — unilateral rights, exclusivity, auto-renewal, assignment, governing law, jurisdiction; wording quoted, not evaluated.

### Financial report / management accounts

1. **Резюме** — issuer, period, standard, audit status, headline result.
2. **Результаты за отчётный период** — table of the figures that carry the picture.
3. **Факторы, указанные компанией** — only what the document itself states, attributed.
4. **Долг и финансирование** / **Денежные потоки** — if material.
5. **Оговорки** — audit, restatements, one-offs, footnotes that change a figure.
6. **Планы и прогнозы** — with modality intact.

### Research paper / study / analyst report

1. **Резюме** — authors, subject of study, main finding in the authors' modality.
2. **Методология** — sample, method, period.
3. **Результаты** — prose on what was found, table with values, CIs, p-values as printed.
4. **Выводы авторов** — what the authors infer, kept apart from what was measured.
5. **Ограничения исследования** — as the authors state them.
6. **Финансирование и конфликт интересов** — if stated.

### Transcript / minutes / meeting record

1. **Резюме** — meeting, date, participants, agenda, outcome.
2. **Ход обсуждения** — per agenda item, in order: the issue, the positions with attribution, the outcome.
3. **Принятые решения** — table: Решение | Кем принято | Срок.
4. **Поручения** — table: Поручение | Ответственный | Срок.
5. **Отложенные вопросы** — only items the participants themselves deferred.

### Tender / RFP / statement of work / regulation

1. **Резюме** — customer, subject, procedure, key dates.
2. **Предмет закупки и требования** — prose on scope, table of mandatory requirements.
3. **Критерии оценки заявок** — criteria and weights.
4. **Сроки и этапы процедуры** — in order.
5. **Требования к оформлению заявки** — composition, format, submission method.
6. **Основания для отклонения заявки**.

### Email thread / document set

Keep a separate ledger per document, then merge. Refer to documents in business terms («письмо от 12.03.2025», «Приложение № 2 к договору»).

1. **Резюме** — subject of the correspondence and status as of the last document.
2. **Хронология** — prose in chronological order, with a table Дата | Событие | Документ if there are many steps.
3. **Достигнутые договорённости** — attributed.
4. **Позиции сторон** — as of the date of the last document.

Where documents give different values for the same thing, use the latest or the one the set treats as governing (a signed version over a draft) — without a discrepancy section.

## Verification is not printed

No verification block, no counts. Keep the record in working notes; if asked, answer in ordinary sentences with real numbers.

## Follow-up answers

Format for answers to the user's later questions (rules in SKILL.md, "Follow-up questions"). Same business register.

```markdown
Неустойка Подрядчика за нарушение срока этапа составляет 0,1% стоимости соответствующего этапа за каждый день просрочки, но не более 10% цены договора. Неустойка начисляется только при просрочке «по вине Подрядчика»; просрочка, вызванная непредоставлением Заказчиком исходных данных, под это условие не подпадает.

Основание: п. 8.2 договора.
```

Answer first, then the condition that changes how it reads, then the reference in the document's own numbering. No headings, no re-summary.
