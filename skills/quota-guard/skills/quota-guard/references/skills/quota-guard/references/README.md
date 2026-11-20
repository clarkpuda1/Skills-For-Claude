# quota-guard

A lightweight Claude **Agent Skill & Plugin** that enforces high-signal, zero-filler responses, clarify-once gating, and targeted edits—helping everyday Claude users stretch message and context limits without losing accuracy.

## Before vs. After

**Prompt:** *"Write a proposal for my freelance client."*

| Default Claude | With `quota-guard` |
| :--- | :--- |
| Writes a 500-word generic template with wrong scope, currency, and pricing—forcing 2 extra redo turns. | Stops and asks 3 short numbered questions with `[default]` options, then writes the exact final draft on the next turn. |

**Prompt:** *"How do I undo my last git commit without losing changes?"*

| Default Claude | With `quota-guard` |
| :--- | :--- |
| Opens with *"Great question!"*, explains Git history theory for 3 paragraphs, and closes with a recap. | Starts on line 1 with `git reset --soft HEAD~1` plus 3 tight safety bullets (`--mixed`, avoid `--hard`, use `git revert` if pushed). |

---

## What This Skill Actually Does (And Doesn't Do)

**What it does:**
- Removes conversational filler around answers while preserving natural human warmth inside personal, creative, or sensitive drafts.
- Prevents wasted redo turns by asking at most **3 short clarifying questions** (with `[default]` options) before generating long drafts (over 300 words).
- Uses **diff-first edits** so Claude does not reprint entire unchanged documents or files on every revision.
- Supports three density modes: `brief`, `standard` (default), `deep`.
- Follows the strict **Agent Skills / Claude.ai YAML frontmatter whitelist** (single-line `description` under 1,024 chars, valid `metadata` block, zero illegal keys) so the same `SKILL.md` works cleanly in Claude.ai, Claude Desktop, and Claude Code.

**Honest limitations:**
- This skill **cannot bypass or increase** Anthropic's backend rate limits. It stretches your existing quota by reducing wasted output tokens and unnecessary back-and-forth turns.
- Like any instruction-based skill, adherence is high across typical sessions but can drift in very long threads (30+ turns); re-invoking `/quota-guard` or reminding Claude refreshes the rules.

---

## Installation

### Option 1: Claude.ai / Claude Desktop (Upload Custom Skill ZIP)
1. Enable **Settings → Capabilities → Code execution and file creation**.
2. Zip the `skills/quota-guard/` folder so the archive root contains `quota-guard/SKILL.md`.
3. Open **Customize → Skills → Upload a skill**, upload the ZIP, and toggle it ON.

*(On a Free plan without Skill Uploads: copy the contents of `skills/quota-guard/SKILL.md` into a Claude Project instruction box or the start of a chat.)*

### Option 2: Claude Code (Plugin Install from GitHub)
```bash
claude plugin install clarkpuda1/quota-guard
```

Or test locally after cloning:
```bash
git clone https://github.com/clarkpuda1/quota-guard.git
claude --plugin-dir ./quota-guard
```

Raw `SKILL.md` URL:
```text
https://raw.githubusercontent.com/clarkpuda1/quota-guard/main/skills/quota-guard/SKILL.md
```

---

## Usage

Once enabled, Claude activates `quota-guard` automatically when you ask to save quota, save tokens, be brief/concise, give a tl;dr, skip fluff, or avoid wasted turns. You can also steer it explicitly:

```text
/quota-guard Summarize this 10-page contract into key deadlines and risks
/quota-guard --mode brief Fix this TypeScript union type error
/quota-guard --no-questions Draft a polite follow-up email for an unpaid invoice
/quota-guard --mode deep Compare Redis vs Postgres for session storage
```

---

## Repository Structure

```text
quota-guard/
├── .claude-plugin/
│   └── plugin.json                        # Claude Code plugin manifest
├── skills/
│   └── quota-guard/
│       ├── SKILL.md                       # Core skill instructions (progressive disclosure)
│       └── references/
│           ├── output-modes.md            # Detailed brief / standard / deep templates
│           └── before-after-examples.md   # Concrete input/output examples
├── LICENSE
└── README.md
```

---

## Local Validation

Before pushing changes to GitHub, validate the plugin manifest and structure:

```bash
claude plugin validate .
```

## License

MIT — see [LICENSE](./LICENSE).
