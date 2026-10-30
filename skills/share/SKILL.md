---
name: share
description: Put an HTML document on aihops and share it for review. Use when the person wants to share, send, publish or get feedback on a page, report, one-pager or deck Claude made (or one they have), or says "put it on aihops" or "hop it over".
---

# Share a document on aihops

aihops is where people share HTML documents and mark them up together. This skill takes a document from here to
people's inboxes, with the person's say-so at each step that tells anyone.

## 1. Make it ready

aihops shows one self-contained HTML file in a sandbox, so:

- **One file.** Inline the CSS and scripts. Images go in as `data:` URIs or SVG. Nothing loads from the internet except
  what a browser can fetch on its own (web fonts from Google Fonts or a CDN are fine; the person's own files aren't).
- **A real `<title>`.** It becomes the document's name on aihops. Ask if it isn't obvious.
- **Text people can quote.** Mark-up pins to words, so headings and paragraphs should be real text, not pictures of text.
- **Up to 5 MB here.** Larger documents, PDFs and Word documents are uploaded in the browser at https://app.aihops.com.au.

## 2. Choose how it's used

Ask the person, unless they've said:

- **Share it** (`mode: share`): everyone gets their own copy, and their comments are theirs alone. The person sees who
  opened it and for how long. Best for sending something out.
- **Collaborate** (`mode: collaborate`): one copy, everyone on it, with questions, suggested edits, AI review and
  consolidation into the next version. Best for getting a document right together.

Also ask whether the people it's shared with may make their own copy (`copies`, on by default).

## 3. Upload

Call `upload_document` with the HTML, the mode and the title. Give the person the link it returns. Nobody else can see it
yet.

## 4. Share, after asking

Say exactly who will be emailed, then call `share_document` with their addresses. People join as reviewers.

- If it answers with `outsideYourDomain`, nothing was shared: name those addresses to the person and ask them to confirm.
  Call again with the confirmed ones in `confirm_outside`.
- Report who was added and who already had it.
- Making someone an owner, or removing someone, is done in the browser.

## If something fails

Every tool error says what to do. The common ones:

- **"This Claude connection can only read"**: the person connected without "Let Claude make changes". They disconnect
  aihops in Claude and connect again, ticking it.
- **"has ended or run out"**: connect aihops to Claude again.
- **429**: aihops limits uploads and shares per hour. Wait and try again.
