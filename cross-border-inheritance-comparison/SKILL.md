---
name: cross-border-inheritance-comparison
description: >
  A framework for comparing how inheritance and succession law works across two or more
  countries that the USER names, and for spotting where the systems differ in ways that
  trip up foreign heirs. Use this skill whenever someone is dealing with — or asking
  about — an estate, succession, probate, or inheritance that spans more than one
  country, OR explicitly wants to compare the inheritance rules of specific countries
  (e.g. "what's the difference between French and German inheritance law", "I'm a US
  citizen who inherited property in Spain", "compare succession in Israel vs Cyprus",
  "my mother had assets in two countries"). Trigger it even when the legal concept is
  not named precisely — cues like "my father died abroad and left a flat", "the
  administrator won't act in my interest", "do I inherit the debts", "the bank froze
  the account", or "can I be cut out of the will" all count. Also use it when the user
  wants to weigh their OPTIONS for handling a cross-border estate — e.g. whether to pay
  a debt now or wait for an insurer to decide, whether to accept or renounce, in which
  country to start proceedings, or whether to sell or keep an asset. The USER supplies
  the countries; this skill supplies the method. Respond in the user's language.
---

# Cross-border inheritance: country comparison

This skill helps a user compare succession/inheritance law between any countries they
name, and — most importantly — catch the places where reasoning about Country A using
the mental model of Country B leads them astray. That mental-model carry-over is what
hurts foreign heirs far more often than the law itself.

The user provides the jurisdictions. Your job is to (1) pin down the facts that decide
the outcome, (2) **research the actual current law of each named country rather than
trusting memory**, (3) compare along a fixed set of dimensions, flagging the traps, and
(4) where the user faces a decision, lay out the realistic options with their trade-offs
and risks — neutrally, without choosing for them.

## Hard rule before anything else

This skill produces **general legal information, not legal advice.** It is not a
substitute for a lawyer qualified in the relevant jurisdiction — especially where there
is an active dispute, a deadline, or money at stake. Always end substantive answers by
pointing the user to a qualified local lawyer and, where you can, naming the concrete
next step. Law and practice change constantly and vary by the facts of the specific
estate. When unsure, say so plainly instead of guessing.

## Why you must research, not recall

Inheritance law is jurisdiction-specific, detail-heavy, and frequently amended. Your
training data is an unreliable guide to the *current* statutory shares, time limits,
procedures, and tax rules of any given country, and disastrous as a guide to a pair of
countries at once. So:

- **Use web search (or any available legal-research tool) to verify each named country's
  rules before you state them.** Treat specific figures (percentages, deadlines, fees)
  and "which law applies" rules as things to look up every time.
- Prefer primary or high-quality secondary sources: government/justice-ministry pages,
  the actual statute, reputable local law firms, the EU e-Justice portal for EU states.
- If web access is unavailable, say so, give only the broad structural orientation you
  are confident about, mark it explicitly as general and possibly outdated, and lean
  harder on "confirm with a local lawyer."

## Workflow

### Step 1 — Identify the jurisdictions
If the user hasn't named them, ask which countries they want to compare (and which one
the assets / the deceased / the heirs are connected to). Don't proceed on assumptions.

### Step 2 — Establish the facts that decide the outcome
Before comparing anything, get the facts that actually change the answer. Ask, in the
user's language, only those that are missing:

1. **Habitual residence / domicile of the deceased at death** — often the single most
   decisive fact, and distinct from citizenship.
2. **Nationality / nationalities of the deceased.**
3. **Was there a will?** Where made? Does it contain a **choice-of-law clause** electing
   a particular country's law?
4. **Where are the assets, and what kind?** Per country; **movable** (accounts, shares,
   vehicles) vs **immovable** (real estate) — many systems treat these differently.
5. **Stage of the process** — nothing started / order or grant applied for / administrator
   appointed / collecting assets / distribution.
6. **The user's role** — heir, executor/administrator, creditor, spouse, guardian of a minor.
7. **Is there a dispute, and with whom?**

See `references/comparison-framework.md` for why each fact matters and what it unlocks.

### Step 3 — Research each named country
For each jurisdiction, look up the current position on the comparison dimensions below.
Note that "which law applies" is itself governed by private-international-law rules that
may point away from the country where the asset sits (see `references/legal-traditions.md`).

### Step 4 — Compare across these dimensions
Pick the ones that bear on the user's situation; don't dump all of them. Each is
explained in `references/comparison-framework.md`.

1. **Which country's law applies** (the conflict-of-laws / choice-of-law question) — and
   whether a will's choice-of-law clause changes it. Often decided by habitual residence,
   domicile, or nationality, sometimes split by movable vs immovable property.
2. **Forced heirship vs testamentary freedom** — must a fixed share go to spouse/children
   (civil-law style), or can the deceased will assets freely (common-law style)? What are
   the exact reserved shares, and to whom?
3. **The estate administrator/executor's role and its limits** — in most systems they
   serve the estate under court/registry supervision, NOT as any one heir's personal
   advocate. This misunderstanding is the most common source of grievance.
4. **The deceased's debts** — paid from the estate before distribution? Can heirs become
   personally liable (e.g. if they distribute early, or if they accept without benefit of
   inventory)? Can the estate be sold to satisfy creditors? Are accounts frozen pending a
   grant/order?
5. **Procedure** — what order/grant is needed (probate, letters of administration,
   inheritance order, certificate of succession), which authority issues it, and whether a
   foreign grant must be resealed/recognised to act locally.
6. **Renouncing / disclaiming** — is it allowed, and is there a deadline (these are easy to
   miss and unforgiving)?
7. **Tax** — inheritance/estate tax, plus transfer fees and the heir's own country-of-
   residence exposure. Never say "no tax" flatly.

### Step 5 — Surface the mental-model traps
The recurring failure mode is assuming Country A behaves like Country B. After comparing,
explicitly name any place where the user's stated assumption (or the natural assumption
from the other country) does not carry over — and explain why. The classic ones:

- "I'm a citizen of X, so X's law / my rights as I know them apply." (Usually false —
  residence/domicile or a will's choice-of-law clause decides.)
- "The administrator works for me." (No — they serve the estate under supervision.)
- "Everything's frozen and safe until I accept, so creditors can't act." (Country-specific.)
- "Country A is the strict one and Country B the free one." (Often reversed — verify.)
- "A foreign court order is enough to release the local asset." (Often needs local
  recognition/resealing or a separate local order.)
- "I have plenty of time." (Watch disclaimer windows and filing deadlines.)

### Step 6 — Lay out the decision options (when the user faces a choice)
Comparing the law is not enough when the user actually has a decision to make. Where there
is a fork in the road, set out the **realistic options as parallel paths**, each with what
it depends on, its advantages, its costs/risks, and the deadlines that bear on it — then let
the user choose. Do **not** pick one for them, and do **not** present it as the "right"
answer; this is orientation, not legal or financial advice.

A worked illustration the user themselves raised — a loan with insurance on the deceased's
debt:
- **Wait for the insurer's decision first**, then deal with the inheritance. Upside: you may
  never lay out your own money if the policy clears the debt. Risks: delay (assets may stay
  frozen), interest/penalties may accrue meanwhile, the insurer may deny, and any
  accept/renounce **deadline** could be pressured by the wait.
- **Pay the debt yourself, take the inheritance, then reclaim from the insurer.** Upside:
  unblocks the estate sooner, stops interest/penalties. Risks: out-of-pocket cash-flow,
  the insurer may deny (then you're not reimbursed), and you need standing to claim (who is
  the policy's beneficiary — you, the heirs, or the estate?).
- **Other paths to test per jurisdiction:** let the **estate** (not you personally) pay from
  its own liquidity; **negotiate forbearance** with the bank pending the insurer; **accept
  with benefit of inventory** where that exists (caps liability to estate assets); or
  **renounce** if the estate is net-negative.

Generate options like this for whatever decision the user faces (see
`references/decision-options.md` for the common decision points and how to build the
options). For each option, tie the advantages/risks to the **facts and the researched law**
— e.g. whether "benefit of inventory" or a given disclaimer deadline actually exists in that
country — rather than to generic intuition. Flag any **deadline** loudly, since several of
these choices are time-barred.

### Step 7 — Respond
- In the user's language (e.g. Russian, Hebrew, English).
- Lead with the decisive fact-finding question(s) if still unknown.
- Give the relevant comparison points, grounded in what you researched, with sources.
- Name the specific trap if the user is operating under one.
- Where there's a decision, present the options as parallel paths with trade-offs — neutrally.
- End with: recommend a jurisdiction-qualified lawyer (and, for money-flow decisions, note
  it isn't financial advice), plus the concrete next step.
- Don't overstate certainty. This skill orients the user and helps them ask the right
  questions; it does not replace advice on their specific file.

## Reference files

- `references/comparison-framework.md` — each fact and each comparison dimension explained:
  why it matters, what to ask, what to look up.
- `references/legal-traditions.md` — orientation on legal families (civil-law forced
  heirship vs common-law testamentary freedom vs religious-law systems), how conflict-of-
  laws / choice-of-law works, the EU Succession Regulation (Brussels IV), and the movable
  vs immovable split.
- `references/decision-options.md` — the common decision points in a cross-border estate
  (accept vs renounce, debt/insurance sequencing, where to start proceedings, sell vs keep,
  etc.) and how to build neutral option-sets with their trade-offs, risks, and deadlines.
- `references/example-cyprus-israel.md` — a fully worked Cyprus ↔ Israel comparison that
  demonstrates the method end to end. Read it to see the level of specificity to aim for.


---

# Appendix — inlined reference material

*(Consolidated into this single file for phone/web install. On a computer you can instead split these back into `references/` files.)*


---

# Comparison framework — facts and dimensions explained

Use this to understand *why* each fact and each dimension matters, what to ask the user,
and what to look up for each named country. Always confirm country-specific figures by
research, not memory.

## Part A — The facts that decide the outcome

### Habitual residence / domicile of the deceased
Often the single most decisive fact, and routinely confused with citizenship. Many systems
(and the EU Succession Regulation) point to the law of the deceased's last **habitual
residence** to govern the whole succession; older common-law systems use **domicile** (the
place treated as one's permanent home), which is a legal concept distinct from both
residence and nationality. Pin this down first — it frequently determines *which country's
law even applies*, which in turn determines everything else.

### Nationality / nationalities
Matters mainly because many systems let a person **choose the law of their nationality** to
govern their estate (via a will), overriding the default. Dual nationals may have more than
one option. Nationality alone rarely decides the governing law by default.

### Will + choice-of-law clause
The existence of a will, where it was executed, and whether it contains an **express
choice-of-law clause** can flip the entire analysis. In many systems the choice is valid
only if stated expressly in the will; absent it, the default (residence/domicile) applies.
Also check whether the will is formally valid under the relevant country's rules.

### Asset location + movable vs immovable
Where each asset sits, and whether it is movable (bank accounts, securities, vehicles,
personal property) or immovable (land, buildings), can change both which law applies and
which procedure is needed. A recurring pattern: a chosen national law governs movables, but
the country where real estate sits insists its own rules apply to that **immovable
property** (the *lex rei sitae* pull). Treat real estate as the trickiest category.

### Stage of the process
Determines what is still possible. Renunciation deadlines may still be open or already
blown; assets may be frozen pending a grant; distribution may have happened (raising
clawback / personal-liability questions). Calibrate advice to the stage.

### The user's role
An heir, an executor/administrator, a creditor, a spouse, and a minor's guardian each have
different rights, duties, and exposures. Don't give "heir" advice to someone who is actually
acting as administrator (their personal-liability picture is different).

### Dispute and counterparty
Whether there's a fight, and with whom (other heirs, the administrator, a bank, a creditor),
changes the practical recommendation — often toward retaining the user's **own independent
lawyer**, separate from any estate administrator.

## Part B — The comparison dimensions

For each named country, research and then compare:

### 1. Which country's law applies (conflict of laws / choice of law)
The threshold question. Look up the country's private-international-law rule for succession:
does it use habitual residence, domicile, or nationality? Does it allow a testator to elect
their national law in the will? Does it split movable vs immovable property? Does it apply
*renvoi* (referring onward to another country's law)? Two countries can each claim their own
law applies, or each point at the other — surface that tension rather than assuming the
country where the asset sits governs.

### 2. Forced heirship vs testamentary freedom
The biggest substantive divide between legal families.
- **Forced-heirship systems** (typical of civil-law countries) reserve a fixed share — a
  "reserved portion" / "statutory portion" / "légitime" — for certain heirs (often spouse
  and children), which a will cannot override. Look up the **exact shares**, who counts as a
  protected heir, and how the reserved portion is divided.
- **Testamentary-freedom systems** (typical of common-law countries) let a person leave
  assets as they wish, sometimes with a safety net (e.g. family-provision/maintenance claims
  by dependents). Look up what carve-outs exist.
- Don't assume which country is which — verify. The intuition is often backwards.

### 3. The administrator/executor's role and its limits
In most systems the executor (named in a will) or administrator (appointed where there's no
will) administers the estate **under court or registry supervision** and is often
**personally liable** for doing it properly. Their duty runs to the **estate as a whole**
and the court — collect assets, value them, settle debts and taxes, then distribute. They
are **not** the personal advocate of any single heir. Confirm the specific country's rules,
but flag this clearly: a foreign heir who expects the administrator to fight for their
individual interests has misread the role and usually needs their own lawyer.

### 4. The deceased's debts
Research, per country: Are debts paid from the **estate** before heirs receive anything (the
usual rule)? Can heirs become **personally liable** — e.g. by distributing before settling
debts, or by accepting the inheritance without a protective "benefit of inventory" where
that exists? Can the administrator **sell estate assets to satisfy creditors**? Are the
deceased's **bank accounts/assets frozen** pending the grant or order, and what unlocks
them? The principle ("debts off the top") is common; the mechanics and personal-liability
triggers differ sharply and are where people get burned.

### 5. Procedure
What instrument is required to act — probate, letters of administration, an inheritance
order, a European Certificate of Succession, etc.? Which authority issues it (court,
registry, notary)? Crucially for cross-border cases: must a **foreign grant be resealed or
recognised** before it can move local assets, or is a **separate local order** required
regardless of foreign proceedings? Look up typical timelines, but be wary — published
estimates vary widely.

### 6. Renouncing / disclaiming
Can an heir refuse the inheritance (e.g. to avoid debts), and is there a **deadline**?
Disclaimer windows are often short and unforgiving, and missing one can be costly. If
renunciation is even possibly relevant, flag any deadline loudly and tell the user to
confirm it immediately with a local lawyer.

### 7. Tax
Look up: is there **inheritance/estate tax** in each country, and at what rates/thresholds?
Then widen the lens — **property transfer fees**, **capital gains** on later sale, and the
**heir's own country-of-residence tax exposure** (some countries tax their residents on
foreign inheritances or on later disposal). Never tell a user "there's no tax" without these
caveats; "no inheritance tax, but check transfer fees and your home-country exposure" is the
safer frame.

## Part C — Putting it together for the user

1. State which law you believe applies to which assets, and why (with the fact it turns on).
2. Compare only the dimensions that matter to their situation.
3. Name any mental-model trap they're operating under.
4. Give the concrete next step (check the will for a choice-of-law clause; apply to reseal
   the grant; watch the X-day disclaimer deadline; get an inventory; retain own counsel).
5. Recommend a lawyer qualified in the relevant jurisdiction(s). Keep certainty honest.


---

# Legal traditions and how "which law applies" works

Orientation only — always verify the current rule for the specific countries by research.
This explains the patterns so you know what to look for and what questions to ask.

## Legal families (very broad strokes)

Inheritance rules cluster by legal tradition, which is a useful first guess (to be
confirmed, never asserted blind):

- **Civil-law systems** (most of continental Europe, Latin America, much of the
  francophone/Hispanophone world) typically have **forced heirship**: a reserved portion
  for spouse and/or children that a will cannot defeat. Look up the exact reserved shares.
- **Common-law systems** (England & Wales, Ireland, most of the US, and many former British
  territories) typically uphold **testamentary freedom**, often with a **family-provision**
  safety net letting dependents claim reasonable provision. Note that some "common-law"
  jurisdictions have grafted on statutory forced-heirship-like rules — verify each one.
- **Mixed systems** blend both (e.g. some jurisdictions combine English-style will rules
  with continental-style intestacy and a reserved portion).
- **Religious-law influence**: some countries apply religious personal law to succession
  (e.g. Sharia-based fixed shares for Muslim estates in various jurisdictions; community-
  specific rules elsewhere). Where relevant, this changes both shares and procedure — flag
  it and research the specific country and the deceased's status.

Heuristic, not a rule: people often assume the *civil-law* country is the "free" one and the
common-law country the "strict" one. It is frequently the reverse. Always check.

## How "which country's law applies" is decided (conflict of laws)

This is the hinge of every cross-border case. Each country has private-international-law
(PIL) rules that decide which law governs a succession. Common connecting factors:

- **Habitual residence** of the deceased at death (the modern EU approach).
- **Domicile** (a common-law concept: one's permanent-home jurisdiction; sticky and
  fact-heavy).
- **Nationality** (used by some civil-law systems, and available as an elective choice in
  many).
- **Situs of the asset (lex rei sitae)** — especially for **immovable property**: the
  country where land sits very often insists its own law governs that land regardless of
  anything else. This is why estates frequently fracture: one law for movables, another for
  each piece of real estate.

Two complications to watch for:

- **Choice of law in a will.** Many systems let the testator elect a particular country's
  law (often their nationality's) to govern the whole estate — but typically **only if
  stated expressly** in the will. No clause ⇒ the default connecting factor applies.
- **Renvoi.** Country A's PIL may point to Country B's law, whose own PIL points back to
  Country A (or onward to Country C). Whether a court "accepts the renvoi" varies. Don't try
  to resolve this from memory; flag it as a question for a PIL-literate local lawyer.

## The EU Succession Regulation (Brussels IV) — Regulation (EU) 650/2012

Relevant whenever any named country is an EU member bound by it (note: Denmark and Ireland
are not bound; the UK never was). Key features to apply when in scope:

- **Default:** the law of the deceased's **last habitual residence** governs the succession
  **as a whole** — even if that is the law of a **non-EU country** (the Regulation is of
  "universal application").
- **Choice of law:** a person may instead elect the law of a country of their **nationality**
  to govern the whole succession, **expressly** in a disposition (will). Dual nationals may
  pick either nationality.
- **One law, one estate** in principle — designed to avoid the movable/immovable fracture,
  though practical frictions remain, especially with non-member states and with local land
  registries.
- **European Certificate of Succession (ECS):** a document recognised across participating
  member states letting heirs/administrators prove their status without re-litigating in
  each country.
- A non-EU country involved in the same estate will apply **its own** PIL, which may not
  match Brussels IV — so the two analyses can diverge and must be run separately, then
  reconciled.

When a named country is **not** in the EU regime, do not assume Brussels IV logic. Research
that country's own PIL rule for succession (residence? domicile? nationality? situs split?).

## Practical mental checklist for the cross-border layer

1. For each asset, which country's law does each involved country *think* governs it?
2. Do those answers agree, or conflict (each claiming its own law, or pointing at the other)?
3. Is there a will, and does it make an express choice of law? Is that choice valid in each
   relevant country?
4. Is real estate involved? Expect the situs country to assert control over it.
5. Is any involved country in the EU Brussels IV regime, and does that change the default?
6. What instrument must be obtained in each country to actually move the assets there?

Resolve as much as research allows, name the open questions honestly, and route the genuinely
contested PIL points to a qualified lawyer in the relevant jurisdiction(s).


---

# Decision options — building neutral, fact-tied choices

When the user faces a fork, don't just explain the law — lay out the realistic **options as
parallel paths**. For each option give: what it **depends on**, its **advantages**, its
**costs/risks**, and any **deadline**. Then stop and let the user decide.

## Ground rules for generating options

- **Stay neutral.** Present the paths side by side; do not pick one or imply which is
  "correct". The best choice depends on facts you may not have (the user's cash position,
  risk tolerance, family dynamics) and on advice from a professional.
- **This is not legal or financial advice.** Several of these choices are money-flow
  decisions (pay now vs wait, sell vs keep). Say so, and route to a lawyer and, where money
  timing/risk is central, a financial adviser/accountant.
- **Tie every pro and con to the researched law and the facts**, not to generic intuition.
  Whether an option even exists (e.g. "benefit of inventory", a given disclaimer window,
  who may claim on a policy) is jurisdiction-specific — verify it.
- **Surface deadlines loudly.** Many options are time-barred; a missed window can remove a
  path entirely. If a deadline is unknown, say it must be confirmed immediately.
- **Note cross-border interaction.** An option that works for assets in Country A may not for
  assets in Country B; sometimes the option must be exercised per country.

## Worked example — loan with insurance on the deceased's debt

The decision: how to sequence paying the debt, recovering from the insurer, and entering the
inheritance. Build the paths like this:

**Option 1 — Wait for the insurer's decision, then proceed.**
- Depends on: whether a valid policy (e.g. credit-life / payment-protection) covers this
  debt, who the policy pays (lender directly, estate, or heirs), and the insurer's timeline.
- Advantages: you may never spend your own money; the debt could be extinguished before it
  ever burdens the estate.
- Risks/costs: delay (assets may stay frozen and unusable); interest/penalties may keep
  accruing on the loan in the meantime; the insurer may deny the claim; the wait can collide
  with any **accept-or-renounce deadline**.

**Option 2 — Pay the debt yourself, take the inheritance, then reclaim from the insurer.**
- Depends on: your available cash; whether you (vs the estate) have **standing to claim** on
  the policy after paying; subrogation/assignment rules.
- Advantages: unblocks the estate sooner; stops further interest/penalties; you take control
  of assets faster.
- Risks/costs: out-of-pocket cash-flow; if the insurer denies, you may not be reimbursed;
  you must be sure you'll have the right to claim before you pay.

**Option 3 — Let the estate pay from its own liquidity.**
- Depends on: whether the estate has accessible cash, and whether a grant/order is in place
  to access it. Keeps the payment off your personal balance sheet.

**Option 4 — Negotiate forbearance with the lender** pending the insurer's decision (pause or
freeze interest), buying time without anyone paying yet.

**Option 5 — Renounce, or accept with benefit of inventory** (where it exists) if the estate
might be net-negative — capping or avoiding exposure to the debt altogether. Watch the
renunciation deadline.

Present whichever of these the facts make realistic, with the trade-offs, and let the user
choose with their lawyer.

## Common decision points (build option-sets the same way)

### Accept vs renounce vs accept-with-benefit-of-inventory
- Driven by whether the estate is net-positive or possibly net-negative, and by debt
  uncertainty. **Benefit of inventory** (common in civil-law systems, absent in many
  common-law ones) lets an heir accept while capping liability to estate assets — verify
  availability and procedure. Renunciation usually has a **hard deadline**. Flag both.

### Where to open / centralise proceedings (forum) and order of operations
- When more than one country could take the matter, options differ in cost, speed, language,
  and which law the forum will apply. Often the practical path is: obtain the primary
  grant/order where the deceased was resident, then **reseal/recognise** it where other
  assets sit. Lay out the sequencing options and their dependencies.

### Rely on a will's choice-of-law clause vs the default law
- If a will elects a particular country's law, one path is to rely on it (e.g. to escape
  forced heirship); another is that an heir disadvantaged by it may test its validity.
  Options here depend on whether the clause is express and valid in each relevant country.

### Funding debts/taxes while assets are frozen (liquidity)
- Options: wait for the grant/order to unlock accounts; use other estate liquidity; advance
  personal funds (with reimbursement from the estate later); or arrange short-term lending.
  Trade-offs are speed vs personal exposure.

### Sell vs keep an asset (especially real estate)
- To cover debts/taxes or to simplify a split, the estate may sell assets, or heirs may keep
  them and settle obligations another way. Depends on liquidity, market, the situs country's
  rules on the asset, and whether co-heirs agree. Note tax (capital gains, transfer fees) and
  that real estate is usually governed by the country where it sits.

### Distribution agreement among heirs vs strict statutory/will split
- Heirs can often agree to redistribute (one takes the local property, another the foreign
  assets, etc.) instead of dividing every asset by the default shares — sometimes needing
  court/registry approval. Option trades flexibility for the need for consensus and approval.

### Use the estate administrator vs seek your own role / own counsel
- In a contested estate, options include: rely on the appointed administrator; seek to be
  appointed administrator yourself (where the user qualifies); or retain **independent
  counsel** to protect the user's individual interests alongside the administration. Remember
  the administrator serves the estate, not any one heir.

## Closing each option-set
End by reminding the user that the listed options are a map of possibilities, not a
recommendation; the right path turns on facts and professional advice; and the immediate
next step is usually to confirm the **deadlines** and the **availability of each option** in
the relevant country with a qualified local lawyer (and, for money-timing/risk, an
accountant or financial adviser).


---

# Worked example — Cyprus ↔ Israel

A fully worked comparison showing the level of specificity to aim for. Treat the figures as
*illustrative and verify them by research before relying on them in a live matter* — they can
change, and much turns on the facts of the estate. This example also illustrates the classic
"reverse" trap (people guess the wrong way round on forced heirship).

## Which law applies

- **Cyprus** gives effect to the logic of the **EU Succession Regulation 650/2012**: by
  default the law of the deceased's **last habitual residence** governs the whole succession
  (even if non-EU), unless the deceased **expressly chose** the law of their nationality in a
  will. For Cyprus **immovable property**, there is a stronger pull toward Cypriot rules and
  the treatment of choice of law is contested — the trickiest point, for a lawyer.
- **Israel**: section 137 of the Succession Law points to the law of the deceased's **country
  of residence** for distribution. Separately, to move assets physically in Israel, an
  **Israeli inheritance order ("Tzav Yerusha")** or **probate order ("Tzav Kiyum Tzava'a")**
  from the Registrar for Matters of Succession (or Family Court) is required **regardless of
  any foreign proceedings**.
- **Trap:** "I'm an Israeli citizen, so Israeli law applies in Cyprus." Citizenship alone
  doesn't decide it — habitual residence and any choice-of-law clause usually do.

## Forced heirship — OPPOSITE between the two

- **Cyprus: yes (Wills and Succession Law, Cap. 195).** The net estate splits into a
  **disposable portion** and a reserved **statutory portion**. The split depends on survivors:
  - Spouse + child/descendant, OR child/descendant with no spouse → disposable **≤ 1/4**
    (statutory ≈ **75%**).
  - Spouse, or parent(s), but no child/descendant → disposable **≤ 1/2** (statutory **50%**).
  - No spouse, no child/descendant, no parents → **100% free** to will.
  Example: estate €4M, survived by wife + one child → statutory 3/4 (€3M) split between wife
  and child; €1M disposable by will. Applies to anyone **domiciled** in Cyprus regardless of
  nationality (the old UK/Commonwealth-origin exemption was abolished by Law 96(I)/2015). A
  will breaching these rules is void only **to the extent** it conflicts, not entirely.
- **Israel: no forced heirship.** Freedom of testation; the only carve-out is **maintenance
  for dependents** (spouse, minor/disabled child, dependent parents) who prove dependency.
- **Trap:** most people assume Israel is the rigid one and Cyprus the free one. **Reversed.**

## Administrator's role and its limits

Both countries: the executor/administrator administers the estate **under court (Israel:
Registrar) supervision**, is **personally liable** for doing it properly, and serves the
**estate as a whole** — collect, value, pay taxes and debts, then distribute. **Not** any one
heir's personal advocate. In Cyprus the administrator may even **sell estate assets to satisfy
creditors** before heirs receive anything. A foreign heir in a contested estate usually needs
their **own independent lawyer**.

## Debts

- Common to both: debts are paid from the **estate** before heirs receive anything; heirs
  don't personally "inherit" the debts as such.
- **Cyprus:** administrator settles debts/taxes first and may liquidate estate assets to do so.
- **Israel:** debts cleared before distribution; if heirs distribute to themselves **before**
  settling debts they can be **personally liable** to creditors. Pending the order, Israeli
  **banks typically freeze** the deceased's accounts; the order (sent to banks and insurers)
  unlocks them.
- **Trap:** "everything's frozen and protected until I accept, so the bank can't touch the
  loan." That reflects Israeli procedure; Cyprus realises assets and handles creditor claims on
  its own court-supervised track and timeline.

## Procedure

- **Cyprus:** with a will → **Grant of Probate** from the District Court; no will → **Letters
  of Administration**. A **foreign grant can often be resealed** in Cyprus (Probates
  (Re-Sealing) Law, Cap. 192) to be acted on locally. Statutes: Cap. 195 (wills/intestacy),
  Cap. 189 (administration).
- **Israel:** apply to the **Registrar for Matters of Succession**; escalates to **Family
  Court** on dispute or where a minor/guardian is involved. An Israeli order is needed to move
  Israeli-situated assets even with a foreign judgment in hand.

## Renouncing / disclaiming

- **Cyprus:** an heir may disclaim, but within **3 months** of becoming aware of the death —
  flag this deadline loudly if renunciation is even possible.
- **Israel:** renunciation (whole or part) is possible before distribution; heirs may also
  redistribute among themselves via a **distribution agreement ("Heskem Haluka")**, subject to
  approval where required.

## Tax

Neither country currently levies **inheritance/estate tax** (Cyprus abolished it in 2000;
Israel in 1981). But watch **capital gains**, **property transfer fees**, and the **heir's own
country-of-residence** exposure. Don't say "no tax" flatly.

## One-line takeaways to reuse

- Citizenship rarely decides the governing law; residence/domicile + a will's choice-of-law
  clause usually do.
- Cyprus = forced heirship; Israel = testamentary freedom (the reverse of the common guess).
- The administrator serves the estate, not you personally.
- Israeli assets need an Israeli order; a Cyprus-bound foreign grant usually needs resealing.
- Mind the Cyprus 3-month disclaimer window.

