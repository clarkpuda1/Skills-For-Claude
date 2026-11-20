---
name: ats-resume
description: Rewrites, audits, and tailors resumes and cover letters for applicant tracking systems and a specific job posting. Use when the user asks to improve or review a resume or CV, make it ATS-friendly, tailor it to a job, match keywords, rewrite bullet points, or write a cover letter. Also use when the user shares a job posting and asks whether they are a fit. Works with pasted text or an uploaded file.
---

# ATS Resume Builder

Turn real experience into clear, keyword-matched, honest resume content. The single hard rule: never invent or inflate experience, skills, degrees, certifications, employers, dates, titles, or numbers. Every claim must trace back to something the user provided or confirmed.

## Step 1: Gather inputs

Needed: the current resume (text or file) and, for tailoring, the job posting. If the user gives a resume with no posting, run an "general ATS audit" instead of tailoring. If the user gives a posting with no resume, ask for the resume first. Ask only for what is missing, in one message.

If an uploaded file is given, read it fully before writing. Note the layout and any tables, columns, or text boxes.

## Step 2: Audit the format

Check and report on each:

- Layout: single column versus multi-column, tables, text boxes, icons, progress bars, and graphics. These can cause parsing errors. Recommend single column.
- Standard section headings: Summary or Profile, Experience (or Work Experience), Education, Skills, Certifications. Non-standard headings like "My Journey" should be renamed.
- Contact block: keep it in the body, not in a header or footer, because some parsers drop those.
- File type: recommend .docx or a text-based PDF. Image-based PDFs fail.
- Dates in one consistent format, such as "Jan 2022 - Mar 2024".

Report findings as a short list with the fix for each.

## Step 3: Extract and map keywords

From the posting, pull out three groups:

- Hard requirements: named tools, certifications, years of experience, degrees, licenses.
- Responsibilities: the verbs and tasks the role describes.
- Soft or context terms: "cross-functional", "stakeholder", "fast-paced". Use only where the user genuinely did this.

Create a table with columns: Keyword, Found in resume (yes, partial, no), Evidence location. Mark "no" items as gaps, not as things to add.

## Step 4: Rewrite bullets

Use this pattern for each experience bullet: strong past-tense verb, what was done, the tool or method, and the result or scope. Example shape:

"Led weekly reporting for a 6-person team using Excel and Power Query, cutting monthly close time from 5 days to 3."

Rules for bullets:

- A number must come from the user. If none exists, use scope instead ("for 3 branches", "across 2,000 monthly orders" only if true) or write "[add your result: ___]" as a visible placeholder. Never make up a figure.
- Start each bullet with a different verb.
- Put the most relevant bullets for the target role first.
- Keep to one line of context per bullet where possible.

## Step 5: Tailor honestly

For each gap, choose one honest action and label it:

- **Reword**: the user did this, but under different terms. Use the posting's term.
- **Surface**: the experience exists but is buried. Move it up.
- **Declare**: the user has a relevant course, training, or self-study. Add it with its real name and date.
- **Disclose in cover letter**: the user lacks the skill but is learning. Say so plainly in the letter, with a timeline if real.
- **Do not add**: the user does not have it. Do not list it as a skill.

## Step 6: Cover letter (if asked)

One page, three paragraphs. Paragraph 1: the specific role and why this company or team. Paragraph 2: one concrete example from the user's experience that matches the top requirement. Paragraph 3: a short close and availability. Avoid generic praise of the company unless the user supplies a real detail.

## Step 7: Fit score (if a posting was given)

Give an honest estimate: strong fit, partial fit, or stretch, with the count of hard requirements met versus missing. Explain the top two gaps. Do not inflate the score to make the user feel better.

## Rules

- Never fabricate. Show placeholders visibly.
- Do not promise interviews, offers, or hiring outcomes.
- Do not add photos, age, civil status, or religion unless the user asks, and say that these are not required by most employers.
- Do not copy phrases from the posting word for word into the resume if they do not describe the user's work.
- Keep personal contact details out of the chat summary. Use the user's own data only where it appears in the final resume they asked for.

## Output format

1. Format audit (short list with fixes)
2. Keyword table
3. Revised resume in plain text, ready to paste into a document
4. "What changed and why" as a short list, with each honest gap labeled (Reword, Surface, Declare, Disclose, Do not add)
5. Fit score, if a posting was given
6. Cover letter, if asked
