# The aihops plugin for Claude

Share the HTML Claude makes on aihops, follow its review, read everyone's mark-up and make the next version, all from
Claude, as you. The full guide, with every tool and every error, is at **https://aihops.com.au/claude**.

## Install

You need an aihops account (free, at https://app.aihops.com.au) and a Claude plan that allows plugins or custom
connectors.

**claude.ai, Claude Desktop and Cowork**

1. Download the plugin from https://aihops.com.au/claude.
2. In Claude, open **Customize › Plugins**, choose **Add**, then **Upload plugin**, and pick the zip.
3. On the plugin's **Connectors** tab, choose **Connect**, and sign in to aihops.
4. On aihops's page, tick **Let Claude make changes** if you want Claude to upload, share and comment as you, then
   choose **Connect**.

Claude mobile uses the connector on your claude.ai account: nothing more to do.

**Claude Code** (v2.1.224 or later)

```
/plugin marketplace add https://aihops.com.au/claude/marketplace.json
/plugin install aihops@aihops
```

The first time Claude uses aihops, run `/mcp`, choose **aihops** and **Authenticate**: your browser opens to sign in.
To get new versions automatically, open `/plugin`, choose **Marketplaces**, then **aihops**, then **Enable auto-update**.

**Only the tools?** Add `https://app.aihops.com.au/mcp` as a custom connector (claude.ai: **Customize › Connectors ›
Add custom connector**; Claude Code: `claude mcp add --transport http aihops https://app.aihops.com.au/mcp`).

## What's in it

- **The aihops connector**, served by aihops itself, so its tools are always the current ones. Ask the `about` tool which
  version you're on.
- **Four skills**:
  - `share`: make a document ready and put it on aihops, asking before anyone is emailed;
  - `status`: who has read and reviewed what, and what's overdue;
  - `apply-feedback`: turn the review into the next version;
  - `review`: mark up a document as you, with your approval.

## What Claude can do

Read what you can read in aihops. If you let it make changes, also: upload documents and versions, share as a reviewer,
comment, reply and resolve, add private notes, finish reviews, ask for AI reviews and consolidations (they count towards
your AI allowance), implement proposals, make copies, set priorities and file documents. Claude asks you before each one.

Only in the browser: deleting anything, owners and roles, a document's mode and copies setting, sharing private mark-up
with everyone, private groups, personas, email choices and billing.

Everything Claude does is recorded as you, through Claude, and owners see that. Disconnect any time from your aihops
Account page, under **Claude connections**.

## When something goes wrong

| What you see | What to do |
|---|---|
| Claude shows **Connect** for aihops | Sign in to aihops when Claude asks. |
| "This Claude connection can only read" | Disconnect aihops in Claude, connect again, and tick **Let Claude make changes**. |
| "has ended or run out" | Connect aihops to Claude again. You'll also see this after disconnecting it on your Account page. |
| "Not found, or you do not have access to it" | Check the document with `list_documents`. It may have been deleted, or not shared with you. |
| "Claude can't do that through aihops" | That one is in the browser only: open https://app.aihops.com.au. |
| A 402 about your AI allowance | Your free AI uses are used up. Your Account page says more. |
| A 429 | You've hit an hourly limit (uploads, shares, AI) or Claude made too many calls in a minute. Wait and try again. |

Still stuck? Email support@aihops.com.au: an AI agent replies, and passes anything it can't solve to a person.

## Data

The plugin stores nothing itself. Claude reads and changes your aihops documents through https://app.aihops.com.au/mcp,
as you, and aihops never sees your Claude conversations. How aihops handles your information:
https://aihops.com.au/privacy/. The terms for using it: https://aihops.com.au/terms/.
