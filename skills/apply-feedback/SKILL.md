---
name: apply-feedback
description: Make the next version of an aihops document from its review. Use when the person wants to act on feedback, address comments, "make the changes", revise a document after review, or upload a new version to aihops.
---

# Make the next version from the review

The person owns the document and decides what changes. Your job is to gather everything, propose, and upload only what
they agree to.

## 1. Gather

- `get_document` for the versions and mode. This works on collaborations: a simple share's comments belong to the
  people it was shared with.
- `get_review_comments` for every open thread, with quotes and suggested wording.
- `get_proposals`: if aihops has already consolidated the mark-up, start from its proposal.
- `read_document` for the current text.

## 2. Propose

List the changes you'd make, each with the thread it answers. Group them by section. Say plainly which comments you'd
leave alone and why, such as a question for the owner, or two reviewers who disagree.

Ask the person to confirm, change or drop items before you touch the file.

## 3. Make it

Two ways:

- **With aihops's own consolidation** (HTML collaborations): if a proposal exists or the person asks for one,
  `consolidate` (it counts towards their AI allowance and takes a few minutes), then `implement_proposal` with the
  numbers they keep and reasons for the ones they decline. aihops adds a note to every thread a kept change answers.
- **By editing the HTML yourself**: change only what was agreed, keep everything else byte for byte where you can, and
  `upload_version` with a note listing what it answers, such as "Fixes GST wording (Rita), adds the phase 3 date (Sam)".

Uploading emails everyone on the document, so say so before you do.

## 4. Close the loop

Offer to reply on each thread you answered, saying what changed, and to resolve it (`reply`, `resolve_thread`). Ask
first: replies are seen by everyone.
