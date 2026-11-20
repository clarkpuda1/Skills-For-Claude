# Output Density Profiles

Load this reference when the user switches modes explicitly (`--mode brief`, `--mode standard`, `--mode deep`, or plain-language equivalents like "keep it brief" / "go deep") or asks how Quota Guard formats different tasks.

## 1. `brief` Mode
- **Best for:** Quick lookups, yes/no checks, command snippets, definitions, and tight Free/Pro usage windows.
- **Target length:** Up to 120 words unless a code block or table strictly requires more.
- **Structure:**
  1. Direct answer in sentence 1.
  2. Up to 4 supporting bullets only if needed to prevent mistakes.
  3. Zero background history unless asked.

## 2. `standard` Mode (Configured Default)
- **Best for:** Daily writing, email/document edits, coding tasks, summaries, and planning.
- **Target length:** As short as possible while remaining 100% copy-paste ready.
- **Structure:**
  - Optional 1-line `Assumed:` note if minor defaults were chosen.
  - Complete deliverable (clean headings, bullets, or diff).
  - Critical caveats only (max 2 bullets if applicable).

## 3. `deep` Mode
- **Best for:** Architecture trade-offs, debugging tricky issues, decision reviews, and learning complex concepts.
- **Rule:** High depth, still zero filler. Every paragraph must introduce new facts, constraints, or concrete options—never paraphrase the same point twice.
- **Structure:**
  1. **Bottom Line** (2–3 sentences).
  2. **Key Trade-offs / Analysis** (structured table or numbered breakdown).
  3. **Concrete Next Action** (single clear recommendation).

## Mode Switching Examples
- "Keep it brief: explain OAuth PKCE" → 4-bullet tight explanation.
- "No questions, draft a polite rent extension email" → Uses sensible defaults, states them in 1 line, outputs ready-to-send email immediately.
- "Go deep: compare Postgres vs SQLite for a local desktop app" → Concise bottom line + comparison table + concrete recommendation.
