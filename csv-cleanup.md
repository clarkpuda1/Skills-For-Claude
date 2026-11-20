---
name: meeting-minutes
description: Converts meeting notes, transcripts, voice-note summaries, or chat logs into structured minutes with an agenda-based discussion summary, decisions, an action register with owners and deadlines, open issues, and a parking lot. Also drafts the follow-up email. Use when the user asks for minutes, MOM, meeting summary, action items, a recap, or a follow-up message after a meeting. Handles multiple meetings in one request by producing separate minutes for each.
---

# Meeting Minutes

Produce minutes that a person who missed the meeting can act on, and that a participant can check against memory. Record what was said and decided. Mark everything the source did not say as missing. Never fill a gap with a plausible guess.

## Step 1: Classify the source

Identify what was provided:

- **Structured notes**: bullets or headings written during the meeting. Light cleanup.
- **Raw transcript**: long, with filler and possibly speaker labels. Needs condensing.
- **Voice-note summary or chat log**: may be fragmented. Expect more gaps.

If the source is under about 100 words, or has no discernible topic, ask one question about the agenda or the main outcome before drafting.

## Step 2: Extract the header

Fill in: meeting title, date, time and timezone, location or platform, facilitator, attendees, absent, and the purpose in one sentence. Write "not stated" for anything missing. Do not assume the facilitator from who spoke first.

## Step 3: Summarize by agenda item

Use the agenda order if one was given, otherwise the order topics came up. For each item:

- Two to four sentences: the question, the main points raised, and any disagreement.
- Name the person who raised a concern only if the source makes that clear and it matters for follow-up.
- Note if the item was deferred.

## Step 4: Record decisions

One line per decision: what was decided, who decided (if stated), and the basis if it was stated. A decision needs an explicit agreement or a clear final statement. A suggestion that nobody confirmed goes under Open Issues, not Decisions. Tag each decision with "confirmed" or "unclear" if the source is ambiguous.

## Step 5: Build the action register

Table with these columns: No., Action, Owner, Due, Status, Source. Rules:

- Owner: the person who agreed to do it. If the source says "someone should", owner is "Unassigned" and goes to the top of the follow-up list.
- Due: the stated date, or "Not set". Do not invent a date. Convert relative dates only if the meeting date is known, and show the result as "Fri, 27 Nov (from 'this Friday')".
- Source: the line or timestamp reference, so it can be verified.

## Step 6: Open issues and parking lot

Open issues: questions raised without an answer, and decisions proposed but not confirmed. Parking lot: topics explicitly deferred to another meeting, with the suggested owner if stated.

## Step 7: Draft the follow-up message (if asked)

A short email or chat message: thanks, the three most important decisions, the action register in a compact form, and one line asking attendees to flag errors within a set period. Do not send anything yourself. Leave the subject line and recipient list for the user.

## Step 8: Sensitive content

If the discussion includes HR matters, complaints, health information, performance reviews, or legal risk, summarize in neutral terms, ask the user whether to include it, and never record personal details beyond what is needed for the action. Recommend that the user store such minutes with restricted access.

## Multiple meetings

If the input covers more than one meeting, produce a separate set of minutes for each, then one combined action register at the end sorted by owner.

## Rules

- No invented attendees, decisions, owners, or dates.
- Keep names exactly as written in the source. Do not correct spelling unless asked.
- Do not quote people verbatim unless the exact wording matters for a decision.
- Mark uncertainty explicitly with "(unclear)" rather than smoothing it over.

## Output format

Title, header block, Summary (three sentences max), Discussion by agenda item, Decisions, Action Register table, Open Issues, Parking Lot, Next Meeting. Add the follow-up message only if asked. Keep the whole thing scannable in a minute or two.
