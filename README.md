# Cross-Border Inheritance Skills

A small set of [Agent Skills](https://docs.claude.com/en/docs/claude-code/skills) for
Claude Code (and any agent that supports the `SKILL.md` standard) that help people make
sense of **inheritance and succession situations that span more than one country** — where
the law of Country A and the mental model someone carries over from Country B quietly
contradict each other.

The skills don't just explain the law. They pin down *which* country's law actually applies,
compare the two systems on the points that matter, lay out the realistic decision options
with their trade-offs, and flag the assumptions that don't carry across borders.

---

## ⚠️ Important: this is information, not legal advice

These skills produce **general legal information only**. They are **not** a substitute for a
lawyer qualified in the relevant country, and nothing they generate should be relied on in a
live matter — especially where there is a dispute, a deadline, or money at stake. Succession
law changes often and turns on the specific facts of each estate. Every output ends by
pointing you to a qualified local lawyer (and, for money-timing questions, an accountant or
financial adviser). Use these skills to understand your situation and ask better questions —
not to make final decisions.

---

## What's in here

| Skill | What it does | Output |
|-------|--------------|--------|
| **`cross-border-inheritance-comparison`** | Compares succession law between any two (or more) countries you name, determines which law applies, lays out decision options, and flags cross-border "traps". | A structured analysis, in your language. |
| **`inheritance-prompt-builder`** | Turns your situation into a polished, ready-to-paste **prompt** you can give to any LLM to get a detailed answer. | A prompt (not the analysis itself). |

You name the countries; the skills supply the method. They work for **any** jurisdictions —
a fully worked **Cyprus ↔ Israel** case ships inside the comparison skill as a reference
example so you can see the level of detail to aim for.

---

## How a skill works

A skill is just a folder with a `SKILL.md` file: YAML frontmatter (a `name` and a
`description` that tells the agent *when* to use it) plus Markdown instructions. Optional
`references/` files hold deeper material the agent loads only when needed. The agent reads the
description and **loads the skill automatically** when your request matches — you don't have to
invoke it manually (though you can).

---

## Installation

Each skill is one folder. Drop the folders into your skills directory.

**Personal install** — available across all your projects:

```bash
cp -r cross-border-inheritance-comparison ~/.claude/skills/
cp -r inheritance-prompt-builder        ~/.claude/skills/
```

**Project install** — scoped to one repo and shareable with your team via git:

```bash
mkdir -p .claude/skills
cp -r cross-border-inheritance-comparison .claude/skills/
cp -r inheritance-prompt-builder        .claude/skills/
```

The final layout must be `<skills-dir>/<skill-name>/SKILL.md` — don't nest it a level deeper.
Then start (or restart) Claude Code and run `/skills` to confirm both loaded.

> The `SKILL.md` format is an open standard, so these folders also work in other agents that
> support it (e.g. Codex CLI, Cursor, Gemini CLI). Installation paths there differ — check
> that agent's docs.

---

## Usage

Just describe your situation in plain language. Examples that trigger the **comparison** skill:

- "My father died in Cyprus, he was an Israeli citizen — what's different about inheritance there?"
- "Compare succession law between France and Germany for an estate split across both."
- "I'm a US citizen who inherited an apartment in Spain. Do I inherit the debts?"
- "The estate administrator isn't protecting my interests — is that normal?"

Examples that trigger the **prompt-builder** skill:

- "Make me a prompt for another LLM about my cross-border inheritance case."
- "Generate a detailed query I can paste into ChatGPT comparing inheritance in X and Y."

The agent will ask a few short questions where a decisive fact is missing (e.g. the deceased's
habitual residence, whether the will has a choice-of-law clause), then produce the analysis or
the prompt in your language (Russian, Hebrew, English, …).

---

## What the skills actually compare

When relevant to your situation, the analysis covers:

1. **Which country's law applies** — by habitual residence, domicile, nationality, the situs of
   real estate, any choice-of-law clause in the will, and the EU Succession Regulation
   (Brussels IV) where it's in play.
2. **Forced heirship vs freedom of testation** — with the exact reserved shares and who is
   protected. (The intuition is often backwards; the skills check.)
3. **The estate administrator/executor's role and its limits** — they serve the estate under
   supervision, *not* any one heir personally. The most common source of grievance.
4. **The deceased's debts** — paid from the estate first; when heirs become personally liable;
   whether assets can be sold to creditors; whether accounts are frozen pending a grant/order.
5. **Procedure** — what grant/order is needed, who issues it, and whether a foreign grant must
   be resealed/recognised to act locally.
6. **Renunciation/disclaimer** — whether it's allowed and, crucially, the **deadline**.
7. **Tax** — inheritance/estate tax, transfer fees, and your own country-of-residence exposure.

It then lays out **decision options as parallel paths** (each with what it depends on, pros,
risks, and deadlines) — for example, when there's insurance on the deceased's loan: wait for
the insurer vs. pay the debt and reclaim later vs. let the estate pay vs. negotiate forbearance
vs. renounce. Options are presented **neutrally** — the skill never chooses for you.

A design principle worth knowing: the skills are told to **research current law rather than rely
on memory**, because succession rules are detail-heavy and change. Their usefulness is best with
an agent that has web/search access; without it, they flag uncertainty more strongly and lean
harder on "confirm with a local lawyer".

---

## Repository structure

```
.
├── README.md
├── cross-border-inheritance-comparison/
│   ├── SKILL.md
│   └── references/
│       ├── comparison-framework.md      # each fact & dimension: why it matters, what to ask
│       ├── legal-traditions.md          # civil vs common law, conflict-of-laws, Brussels IV
│       ├── decision-options.md          # common forks + how to build neutral option-sets
│       └── example-cyprus-israel.md     # fully worked Cyprus ↔ Israel comparison
└── inheritance-prompt-builder/
    ├── SKILL.md
    └── references/
        ├── prompt-template.md           # the master template the builder fills in
        └── filled-example.md            # a filled, ready-to-paste example prompt
```

---

## Customising and extending

- **Add more worked examples.** Drop a new `references/example-<a>-<b>.md` into the comparison
  skill following the Cyprus ↔ Israel structure; it raises output quality for that country pair.
- **Tune triggering.** The `description` in each `SKILL.md` decides when the skill loads. If it's
  firing too rarely or too often, edit the description's cues — most skill issues are description
  issues, not instruction issues.
- **Change defaults.** The prompt template supports answer-language and depth tweaks; edit
  `prompt-template.md` to set your preferred defaults.

---

## Limitations

- General information only — not legal or financial advice (see the disclaimer above).
- Output quality depends on the underlying model and on whether it can access current sources.
- Coverage is only as good as what the model can research for the specific countries; always
  verify figures, shares, and deadlines against primary sources or a qualified lawyer.
- The skills orient you and help you ask the right questions; they do not resolve your case.

---

## License

No license is included by default. If you publish this, add a `LICENSE` file (e.g. MIT) so others
know how they may use it.

