---
name: news-fact-check
description: Verifies news stories, social media posts, viral claims, screenshots, forwarded messages, and AI-generated or manipulated media claims by decomposing them into checkable claims, tracing each to an original source, cross-checking independent reliable outlets and official or fact-checking sources, and rating each claim with stated confidence. Use when the user asks "is this true", "fact check this", "totoo ba ito", "verify this", "is this fake", or shares a headline, screenshot, video description, or message. Works for Philippine and international topics.
---

# News Fact Check

Determine what is confirmed, what is unconfirmed, and what is false, with the evidence behind each call. Calibrate confidence honestly. "Unconfirmed" is a legitimate and often the correct verdict. Never declare a claim false without evidence that contradicts it.

## Step 1: Decompose the claim

Split the content into individual statements. Each must be specific enough to check: who did what, when, where, how many, or what was said. Separate:

- Factual claims (checkable)
- Attributed claims (someone said X)
- Opinions and framing (not checked, but noted if they mislead)
- Implied claims (the post suggests Y without stating it)

Number the checkable claims. Work on the top five if there are many, and say which were skipped.

## Step 2: Check the media, if any

For images or video, do these before relying on any content:

- Reverse image search or keyframe search to find earlier appearances. A real photo from another event is the most common form of misinformation.
- Look for date and location inconsistencies, such as weather, signage language, or vehicle plates that do not match the stated place.
- Check for signs of editing or AI generation, but treat these as indicators, not proof. Say what you observed.
- Look for the original upload. The first upload often has more context than reposts.

Note that you can describe what you see but cannot verify a video's authenticity with certainty from a description alone. Say that.

## Step 3: Trace each claim to its origin

For each numbered claim, identify the earliest verifiable source: the official statement, the court document, the data release, the press release, the original reporting. If the claim cannot be traced to any source, record "no source found" as a finding in itself.

Search with specific terms: names, exact figures, dates, agency names. Use web search and fetch the actual pages where possible, not only snippets.

## Step 4: Cross-check

For each claim, look for at least two independent reliable sources plus the relevant official or fact-check source. "Independent" means not reposting each other. Check, where relevant:

- Official government or agency sites (for example PNA, DOH, PAGASA, the relevant department or LGU)
- Established news outlets with corrections policies
- Local fact-checking organizations and international fact-checkers that cover the topic

Note the date of each source. Old coverage of a current claim is a red flag.

## Step 5: Rate each claim

Use one rating per claim, with one-line reasoning and a confidence level (high, medium, low):

- **Confirmed**: supported by the origin source and at least one independent source.
- **Partly true**: the core is accurate but a detail, number, or context is wrong.
- **Misleading**: technically accurate facts arranged to imply something false, or a real event with false context.
- **Unconfirmed**: no reliable source found either way. Not the same as false.
- **False**: contradicted by reliable evidence. Name the evidence.

## Step 6: Assess overall risk

Note if the content involves: a health claim that could cause harm if acted on, a fake emergency or evacuation notice, a financial scam or investment claim, a claim that targets a named individual, or an election-related claim. For these, state the risk up front and point to the official channel: for example the relevant agency's hotline or official page.

## Step 7: Explain the verdict

Start with a one-sentence overall verdict. Then the claim table. Then "What would change this verdict" for any Unconfirmed or Partly true rating. Then the sources list with dates.

## Rules

- Do not give a verdict on a claim you did not check. Say which claims were skipped.
- Be even-handed on political topics: rate the factual claim by the evidence, regardless of which side it helps.
- Do not repeat the false wording in full. Describe it: "the post claims a new tax on e-wallets" is enough.
- Do not reveal private information about people named in the content, and do not speculate about their motives.
- Do not cite a source you did not open or see in a search result. Cite only what you verified.
- Flag interested-party sources. A government agency verifying its own policy, or a bank or company describing its own product, is a primary source for what they said, but not independent proof of the claim. Label these as "official position" and look for an independent check as well.
- Satire and April Fools' content can look like news. Check whether the outlet is a satire site or a dated joke before rating it. Note the date of any source older than the claim.
- Viral claims often mix a real policy with a false detail. Split these into separate rows and rate them separately, for example "Partly true" when the policy exists but the claimed effect does not.
- If search results conflict, say so and explain which source has the stronger evidence and why.

## Output format

Overall verdict (one sentence). Claim table with columns: No., Claim, Rating, Confidence, Key evidence. Media notes if applicable. Risk note if applicable. Unresolved questions. Sources with dates. Keep it under a few short sections for a simple check; use the full structure for viral or high-stakes content.
