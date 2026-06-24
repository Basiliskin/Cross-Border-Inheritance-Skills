---
name: inheritance-prompt-builder
description: >
  Generates a ready-to-paste PROMPT that the user can give to any LLM to get a detailed,
  well-structured analysis of a cross-border inheritance / succession situation. Use this
  skill when the user wants a prompt, template, or "question to ask another AI" about an
  estate that spans two or more countries — cues like "make me a prompt for ChatGPT about
  my inheritance case", "generate a prompt I can give an LLM to compare succession in X
  and Y", "I want a detailed query about my cross-border estate", "build a prompt about
  the loan/insurance/administrator situation". The OUTPUT of this skill is a prompt (not the
  legal analysis itself). The user supplies the countries and their situation; this skill
  turns it into a high-quality prompt. If instead the user wants the analysis directly, use
  the cross-border-inheritance-comparison skill. Interact, and produce the prompt, in the
  user's language.
---

# Inheritance prompt builder

This skill produces a **prompt** that, when pasted into any capable LLM, will elicit a
thorough, structured answer about a cross-border inheritance situation. You are building a
prompt — you are not answering the legal question yourself in this mode.

A good generated prompt does three things: (1) loads the target LLM with the user's specific
facts, (2) tells it exactly what analysis to perform and in what structure, and (3) bakes in
the quality and safety guardrails (verify/cite, state assumptions, flag deadlines, not legal
advice, recommend a local lawyer). The full template is in
`references/prompt-template.md`; a filled example is in `references/filled-example.md`.

## Workflow

### Step 1 — Decide tailored vs generic
Ask the user (briefly) whether they want:
- a **tailored prompt** — you collect a few facts first, then fill them in; or
- a **generic template** — a reusable prompt with clearly-marked placeholders they fill in
  themselves later.

If they already gave plenty of detail, default to tailored and just confirm gaps.

### Step 2 — Gather the decisive facts (for a tailored prompt)
Collect, in the user's language, only what's missing. These are the facts that change the
answer, so the generated prompt should carry them:
1. Countries involved (and which one the assets / deceased / heirs connect to).
2. Deceased's **habitual residence / domicile** at death (distinct from citizenship).
3. Deceased's **nationality / nationalities**.
4. **Will?** Where made; any **choice-of-law clause**.
5. **Assets**: what and where; **movable** vs **immovable** (real estate).
6. **Stage** of the process; the **user's role** (heir / administrator / creditor / spouse /
   guardian); any **dispute** and with whom.
7. The user's **specific question or the decision** they face (e.g. the loan-with-insurance
   sequencing, accept vs renounce, where to start proceedings).
8. The **language** the user wants the eventual answer in.

Keep it to one light round — don't interrogate. For anything still unknown, use a labelled
placeholder in the prompt (e.g. `[HABITUAL RESIDENCE AT DEATH — to confirm]`) rather than
guessing.

### Step 3 — Build the prompt from the template
Fill `references/prompt-template.md` with the user's facts. The generated prompt must instruct
the target LLM to:
- **Determine which country's law applies** to which assets, and why (habitual residence /
  domicile / nationality / situs of immovable property / any choice-of-law clause / EU
  Succession Regulation where relevant).
- **Compare** the involved countries on the dimensions that matter: forced heirship vs
  testamentary freedom (with exact shares), the administrator/executor's role and its limits,
  the deceased's debts and any personal-liability triggers, procedure (grants/orders/
  resealing), renunciation and its deadlines, and tax.
- **Lay out the decision options** (when the user faces a choice) as parallel paths, each with
  what it depends on, advantages, costs/risks, and deadlines — neutrally, without picking one.
- **Flag the mental-model traps** where one country's intuition misleads in the other.
- **Verify and cite**: prefer current primary/high-quality sources, state assumptions, ask
  for missing decisive facts, mark uncertainty honestly.
- **Caveat**: give general information, not legal/financial advice; recommend a jurisdiction-
  qualified lawyer; highlight deadlines.
- **Output format**: structured sections, a comparison table, an options table (if relevant),
  and an "open questions / facts to confirm" list.

### Step 4 — Deliver
Output the finished prompt in the user's language as a single clearly-delimited block they can
copy in one go. Briefly tell them: which facts you filled vs left as placeholders, and that
they can paste it into any LLM. Offer to tweak (shorten, add a specific sub-question, change
the target answer language, or harden the "must cite sources" instruction).

## Notes
- You are generating a prompt, not legal advice. The prompt itself instructs the downstream
  LLM to add the appropriate caveats and to recommend a qualified lawyer.
- Keep the generated prompt model-agnostic so it works in any LLM.
- If the user wants the analysis now instead of a prompt, hand off to the
  cross-border-inheritance-comparison skill.


---

# Appendix — inlined reference material

*(Consolidated into this single file for phone/web install.)*


---

# Master prompt template

Fill the `[BRACKETED]` fields from the user's answers. Leave unknown decisive facts as
labelled placeholders (e.g. `[HABITUAL RESIDENCE AT DEATH — to confirm]`) so the downstream
LLM knows to ask or assume explicitly. Translate the labels and instructions into the user's
language when you produce the final prompt. Deliver the result as one copy-pasteable block.

---

You are an expert assistant on **cross-border inheritance and succession law**. Help me
understand my situation in detail. It involves more than one country, so be careful about
which country's law actually applies before reasoning about outcomes.

## My situation
- Countries involved: **[COUNTRY A]** and **[COUNTRY B]** (add more if any).
- The deceased: relationship to me = **[e.g. my father]**; date of death = **[DATE]**.
- Deceased's **habitual residence / domicile** at death: **[PLACE — or "to confirm"]**.
- Deceased's **nationality/-ies**: **[NATIONALITY]**.
- **Will?** **[yes/no; where made]**. Does it contain a **choice-of-law clause** electing a
  particular country's law? **[yes/no/unknown — quote it if available]**.
- **Assets and where they are**: **[list, marking each as movable — accounts, shares,
  vehicles — or immovable — real estate — and its country]**.
- **Stage of the process**: **[nothing started / order or grant applied for / administrator
  appointed / collecting assets / distribution]**.
- **My role**: **[heir / executor or administrator / creditor / spouse / guardian of a minor]**.
- **Dispute?** **[yes/no; with whom]**.
- **My specific question / the decision I face**: **[e.g. there is insurance on the deceased's
  bank loan — should I wait for the insurer, or pay the debt and reclaim later; or: accept vs
  renounce; or: in which country to start]**.

## What I need you to do
1. **Determine which country's law applies** to which assets, and explain why — using the
   right connecting factor (habitual residence, domicile, nationality, or the situs of
   immovable property), any choice-of-law clause in the will, and the EU Succession Regulation
   650/2012 where an involved country is bound by it. If two countries' rules point
   differently, say so.
2. **Compare [COUNTRY A] and [COUNTRY B]** on the points relevant to my situation:
   - Forced heirship vs freedom of testation — with the **exact reserved shares** and who is
     protected.
   - The estate **administrator/executor's role and its limits** (whose interests they serve;
     are they my personal advocate or not).
   - The deceased's **debts**: paid from the estate first? Can I become **personally liable**
     (e.g. by distributing early, or by accepting without "benefit of inventory")? Can assets
     be sold to pay creditors? Are accounts **frozen** pending a grant/order?
   - **Procedure**: what order/grant is needed, who issues it, and whether a foreign grant must
     be **resealed/recognised** to act locally.
   - **Renunciation/disclaimer**: allowed? **Deadline?**
   - **Tax**: inheritance/estate tax, transfer fees, and my own country-of-residence exposure.
3. **Lay out my realistic options** for the decision I face, as **parallel paths**. For each:
   what it **depends on**, its **advantages**, its **costs/risks**, and any **deadline**.
   Present them **neutrally** — do not choose for me. Where relevant, include options such as:
   waiting for the insurer vs paying then reclaiming vs letting the estate pay vs negotiating
   forbearance; and accept vs renounce vs accept-with-benefit-of-inventory.
4. **Flag the traps** — places where the assumptions natural in **[COUNTRY A]** do **not**
   carry over to **[COUNTRY B]** (or vice versa), e.g. about citizenship deciding the law, the
   administrator's loyalties, frozen-asset protection, or which country is the "strict" one.

## How to answer
- **Verify against current law and cite your sources**; prefer official/statutory or reputable
  local-firm sources. Where you are unsure or the rule may have changed, **say so** rather than
  guessing, and tell me what to confirm.
- **State any assumptions** you make, and **list the missing facts** that would change the
  answer.
- Treat this as **general information, not legal or financial advice**; recommend I confirm
  with a lawyer qualified in the relevant country (and an accountant for money-timing/tax), and
  **highlight any deadlines** prominently.
- **Format**: clear sections; a **comparison table** for [COUNTRY A] vs [COUNTRY B]; an
  **options table** (option / depends on / pros / risks / deadline) if I face a decision; and a
  final **"facts to confirm"** checklist.
- Answer in **[LANGUAGE]**.

---

## Builder notes (do not include in the output prompt)
- Drop dimensions in section 2 that are clearly irrelevant to the user's question, to keep the
  prompt focused — but keep "which law applies" and "debts" unless plainly moot.
- If the user's decision isn't the insurance one, replace the examples in section 3 with their
  actual fork.
- If the user wants a **generic reusable** template, leave all `[BRACKETED]` fields as
  placeholders and keep every dimension.


---

# Filled example

Demonstrates the template filled for a realistic case — an Israeli heir, a bank loan with
insurance, and assets in Cyprus — and rendered in the user's language (Russian here). Note how
unknown decisive facts are kept as labelled placeholders rather than guessed. This whole block
is what the user copies into another LLM.

---

Ты — эксперт по трансграничному наследственному праву. Помоги мне детально разобраться в моей
ситуации. В ней участвует больше одной страны, поэтому сначала аккуратно определи, право какой
страны вообще применяется, и только потом рассуждай о последствиях.

## Моя ситуация
- Страны: **Кипр** и **Израиль**.
- Умерший: **[кем приходится — напр. отец]**; дата смерти — **[ДАТА]**.
- **Обычное место жительства / домициль** умершего на момент смерти: **[МЕСТО — уточнить]**
  (это ключевой факт, не путать с гражданством).
- Гражданство умершего: **Израиль**.
- **Завещание?** **[да/нет; где составлено — уточнить]**. Есть ли в нём **оговорка о выборе
  права** в пользу какой-либо страны? **[да/нет/неизвестно — приведи текст, если есть]**.
- **Активы и их местонахождение**: **[напр. недвижимость на Кипре (immovable); банковский счёт
  на Кипре (movable); банковская ссуда на Кипре, по которой есть страховка]**.
- **Стадия процесса**: **[напр. назначен администратор наследства]**.
- **Моя роль**: **наследник**.
- **Спор?** **[напр. да — с администратором наследства по поводу защиты моих интересов]**.
- **Мой конкретный вопрос / развилка**: по ссуде умершего есть страховка. Что выгоднее и
  безопаснее — **дождаться решения страховой и потом входить в наследство**, или **погасить
  долг самому, вступить в наследство, а потом взыскать сумму со страховой**? Разбери и иные
  возможные пути.

## Что нужно сделать
1. **Определи, право какой страны применяется** к каким активам, и объясни почему — через
   правильный привязочный фактор (обычное место жительства, домициль, гражданство или место
   нахождения недвижимости), любую оговорку о выборе права в завещании и Регламент ЕС 650/2012
   там, где он применим. Если правила Кипра и Израиля указывают на разное — скажи об этом.
2. **Сравни Кипр и Израиль** по релевантным пунктам:
   - обязательная доля против свободы завещания — с **точными зарезервированными долями** и кругом
     защищённых наследников;
   - **роль администратора наследства и её пределы** (чьи интересы он защищает; является ли он
     моим личным представителем);
   - **долги умершего**: гасятся ли из наследственной массы в первую очередь; могу ли я стать
     **лично ответственным** (напр. при раннем распределении или принятии без «описи»); могут ли
     активы быть проданы для расчёта с кредиторами; **замораживаются** ли счета до выдачи
     приказа/гранта;
   - **процедура**: какой приказ/грант нужен, кто его выдаёт, нужно ли **признавать/перезапечатывать
     (resealing)** иностранный грант для действий на месте;
   - **отказ от наследства**: возможен ли, и есть ли **срок**;
   - **налоги**: налог на наследство, сборы за переход права, и моя налоговая нагрузка по стране
     моего проживания.
3. **Разложи мои реальные варианты** по развилке со страховкой **параллельными путями**. Для
   каждого: **от чего зависит**, **плюсы**, **издержки/риски** и **сроки**. Подай их
   **нейтрально** — не выбирай за меня. Включи в том числе: ждать страховую; заплатить и потом
   взыскать; дать заплатить самой наследственной массе; договориться с банком об отсрочке; а также
   принять / отказаться / принять «с описью».
4. **Назови ловушки** — где интуиция, привычная для **Израиля**, **не переносится** на **Кипр** (и
   наоборот): про то, что гражданство якобы решает применимое право; про лояльность администратора;
   про «заморозку» как защиту; про то, какая страна «строгая» в вопросах завещания.

## Как отвечать
- **Сверяйся с действующим правом и указывай источники**; предпочитай официальные/нормативные и
  репутационные местные источники. Где не уверен или правило могло измениться — **прямо скажи это**,
  а не угадывай, и укажи, что мне нужно проверить.
- **Обозначь свои допущения** и **перечисли недостающие факты**, которые меняют ответ.
- Это **общая информация, а не юридический или финансовый совет**; порекомендуй подтвердить у
  адвоката, квалифицированного в соответствующей стране (и у бухгалтера — по налогам и срокам
  платежей), и **выдели все сроки** заметно.
- **Формат**: понятные разделы; **таблица сравнения** Кипр vs Израиль; **таблица вариантов**
  (вариант / от чего зависит / плюсы / риски / срок); и финальный чек-лист **«что нужно
  подтвердить»**.
- Отвечай **по-русски**.

---

End of example. In real use the builder fills the remaining `[...]` placeholders from the user's
answers, or leaves them labelled for the user/downstream LLM to resolve.
