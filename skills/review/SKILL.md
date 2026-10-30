---
name: review
description: Review a document on aihops as the person, adding mark-up in their name. Use when they ask Claude to review, check, mark up or comment on a document shared with them on aihops, or to finish their review.
---

# Review a document on aihops, as the person

Everything you add appears under the person's name, marked as through Claude. Write as they would, and let them see it
first.

## 1. Read

- `get_document` for the mode, the current version and their role.
- `read_document` for the text, page by page if it is long. This also records that they opened it.
- On a collaboration, `get_review_comments` (owners) shows what others already said: don't repeat it.

## 2. Draft the mark-up

For each point, pick the type that fits:

| Type | For |
|---|---|
| `Q` | Something unclear, or a question for the author |
| `Edit` | Better wording: put the new words in `suggestion` |
| `Issue` | Something wrong: a fact, a risk, a promise the document can't keep |
| `Price` | Anything about money: totals, GST, rates, discounts |
| `Comment` | Anything else |

Quote the exact words each point is about, copied from `read_document`, at least four characters and no more than a
sentence or two. A quote aihops can't find is refused: copy it again, exactly.

Keep each comment short and specific. Prefer a few points that matter to many small ones.

## 3. Check with the person

Show the drafted mark-up, as a list with the quote and the comment for each. Add only what they approve, with
`add_comment`. If they want some kept to themselves, use `add_private_comment` instead: nobody else sees those.

A simple share takes plain comments only, which only the person sees.

## 4. Finish

On a collaboration, ask whether to tell the owners they've finished. If yes, `finish_review`. When everyone has finished,
the owners are emailed.

## An AI review instead

If the person would rather aihops reviewed it as a persona, such as their counsel or CFO, use `list_personas` and then
`request_ai_review`. It counts towards their AI allowance and sends the text to Anthropic. Its findings arrive as threads
marked AI, in a minute or two: check with `get_ai_review`.
