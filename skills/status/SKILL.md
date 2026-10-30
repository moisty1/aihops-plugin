---
name: status
description: Report on the person's aihops documents and reviews. Use when they ask who has read or reviewed something, what's overdue, what's waiting for them, what changed, or "where are we at" with a document on aihops.
---

# Review status on aihops

Answer from aihops, not from memory: its numbers change by the minute.

## What to call

1. `list_documents` for the overview: what they own, what's shared with them, what's overdue, open threads, and how many
   reviewers have finished.
2. For one document they own, `get_review_progress`: each person's stage (invited, not opened, behind, reviewing,
   finished), opens and reading time.
3. For what was said, `get_review_comments` (owners, collaborations only). For what changed, `compare_versions`.
4. For who did what and when, `get_activity`, narrowed with `since`, `person` or `action`.

## How to report

- Lead with what needs the person: overdue reviews, people who haven't opened it, threads waiting on them.
- Name people. Give counts as "3 of 5 finished", and times in the person's own terms ("yesterday", "2 hours").
- A simple share has no comments for owners and no "finished": report opens and reading time only.
- Say when something was done through Claude: the history marks it.
- Don't chase anyone or change anything unless asked.

## Privacy

Never guess at private notes or a simple share's comments: aihops doesn't return them to owners, by design.
`get_private_comments` returns only the person's own.
