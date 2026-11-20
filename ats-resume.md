---
name: csv-cleanup
description: Profiles, audits, and cleans messy tabular data (CSV, TSV, or Excel exports) including header problems, duplicate and near-duplicate rows, inconsistent categories, mixed date and number formats, encoding errors, stray whitespace, totals and subtotal rows, merged-cell artifacts, and unreliable IDs. Produces a cleaned file, a row-by-row change log, and a data quality report. Use when the user has a messy file, wants data standardized, asks what is wrong with their spreadsheet, or needs data ready for analysis or import.
---

# CSV Cleanup

Clean data without destroying information, and make every change traceable. The original file is never modified. Every transformation is reported with counts. Ambiguous cases are flagged for the user rather than guessed.

## Step 1: Profile before touching anything

Run a profile of the file and report:

- Encoding and delimiter (UTF-8, Windows-1252, or UTF-8 with BOM; comma, semicolon, or tab). Check for a BOM on the first header.
- Row count, column count, and whether every row has the same number of fields.
- Header row: is it on line 1? Are there title rows or blank rows above it?
- Per column: inferred type, null count, distinct count, min and max for numbers and dates, and the top 10 values for text columns.
- Structural issues: totals rows, subtotal rows, repeated header rows mid-file, merged-cell fill-down artifacts, and footer notes.

Use a script for this when the file is more than a few hundred rows. Show the profile as a compact table.

## Step 2: Build the issue list

Classify each issue with severity:

- **Blocking**: the file cannot be parsed correctly (wrong delimiter, broken quoting, ragged rows).
- **Corrupting**: a fix would change meaning if done wrong (ambiguous dates, duplicate definition unclear, numbers with unclear decimal separator).
- **Cosmetic**: whitespace, casing, inconsistent labels.

Present blocking and corrupting issues to the user with a recommended action and wait for confirmation before fixing them. Apply cosmetic fixes automatically, but log them.

## Step 3: Apply the fixes

Order matters. Do these in sequence:

1. Fix encoding and delimiter. Re-read and confirm row and column counts match the profile.
2. Remove title rows above the header, and totals or subtotal rows, but move them to a separate "excluded_rows" sheet or file so nothing is lost.
3. Remove repeated header rows, after confirming they match the header exactly.
4. Trim leading and trailing whitespace in all text cells. Collapse internal runs of spaces only where the column is categorical.
5. Standardize categories with a mapping table. Show the proposed mapping (for example "Mkt", "marketing", "Marketing Dept" to "Marketing") and get confirmation. Do not merge categories that could mean different things.
6. Normalize dates to ISO 8601 (YYYY-MM-DD). If a date is ambiguous (for example 03/04/2026 with day and month both at most 12), do not convert it. Flag it.
7. Convert numeric text: remove thousand separators only when the decimal separator is unambiguous. Store unconvertible values as blank and list them in the change log.
8. Handle duplicates after the key is confirmed. Show: the candidate key columns, the count of exact duplicates, and the count of duplicates on the key only. Keep the first occurrence by default, but list every removed row in the log.
9. Fill-down only for merged-cell artifacts where the column is clearly a group label. Log each fill.

## Step 4: Validate

After cleaning, run these checks and report pass or fail for each:

- Row count reconciliation: original rows minus removed rows equals output rows.
- No column changed type unexpectedly.
- Key columns have no nulls, or the nulls are listed.
- Numeric totals in the output match the numeric totals in the original, excluding any excluded rows. Report the difference if any.
- Date range is plausible.

## Step 5: Deliver

Output three files:

- The cleaned data file, named with a suffix such as `_cleaned.csv`.
- A change log (CSV or Markdown) with columns: step, column, rows affected, action, example before and after.
- An excluded-rows file, if any rows were removed.

Then a short report: the blocking and corrupting issues the user still needs to decide, the validation results, and what was not done.

## Rules

- Never overwrite the original.
- Never guess missing values, ambiguous dates, or category merges.
- Do not drop a column unless the user asks, even if it looks empty. Report it instead.
- Personal data (names, IDs, phone numbers, addresses, account numbers): do not echo full values in chat. Show masked examples. Ask the user before exporting a file that contains them to any shared location.
- For files too large to show in chat, report summaries and sample rows only.

## Output format

Profile table, issue list grouped by severity with the questions that need answers, then the delivered files, the validation table, and a one-paragraph summary of what changed.
