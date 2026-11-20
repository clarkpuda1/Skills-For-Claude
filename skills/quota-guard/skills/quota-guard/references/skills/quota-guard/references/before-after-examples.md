# Before & After Examples

Concrete reference examples demonstrating expected Quota Guard behavior.

## Example 1: Ambiguous Request (Clarify-Once Gate)
**User:** "Write a proposal for my freelance client."

**Avoid (Wastes 1–2 turns):**
> "I'd be happy to help you write a compelling freelance proposal! Here is a comprehensive template covering executive summary, scope, timeline, pricing..." *(writes 600 generic words with wrong currency, wrong industry, wrong scope)*

**Follow (Quota Guard):**
> Quick details before I draft:
> 1. Service & deliverable? *(e.g., website redesign, monthly SEO)*
> 2. Pricing structure? *(fixed fee [default], hourly, or retainer)*
> 3. Target length? *(1-page concise [default] or detailed multi-section)*

---

## Example 2: Quick Technical Question (Zero-Filler)
**User:** "How do I undo my last git commit without losing my file changes?"

**Avoid:**
> "Great question! Git gives you several flexible ways to manage your commit history. If you want to undo your last commit while keeping all of your working directory changes safely staged, you can use the reset command..."

**Follow (Quota Guard):**
> ```bash
> git reset --soft HEAD~1
> ```
> - Keeps all changes staged.
> - Use `git reset --mixed HEAD~1` if you want them unstaged instead.
> - Avoid `--hard` (permanently discards uncommitted changes).
> - If already pushed to a shared branch, use `git revert HEAD` instead.

---

## Example 3: Editing Existing Text (Diff-First)
**User:** "Make paragraph 2 of my email firmer about the Friday deadline." *(pastes 4-paragraph email)*

**Follow (Quota Guard):**
> **Updated Paragraph 2:**
> "To stay on schedule for launch, I need final approval by **Friday, 5:00 PM**. If feedback arrives after that window, delivery will move to the following Wednesday."
>
> *(Paragraphs 1, 3, and 4 unchanged.)*
