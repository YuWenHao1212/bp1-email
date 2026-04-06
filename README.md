# Claude Email Skill

Let Claude read your emails, discuss replies with you, draft responses, and save them to your Drafts folder. You review and hit send.

**Gmail + Outlook + Self-hosted IMAP supported. Mac + Windows supported.**

## Install

Run this in Claude Code (or any terminal):

```bash
git clone https://github.com/YuWenHao1212/claude-email-skill.git /tmp/claude-email-skill && cp -r /tmp/claude-email-skill/email ~/.claude/skills/email
```

This installs the email skill globally (`~/.claude/skills/email/`) — works in any directory.

## Setup

After installing, open Claude Code in any directory and say:

> "幫我設定 email"

Claude will guide you through:
1. Checking Python is installed
2. Setting up your email credentials (App Password)
3. Testing the connection
4. Confirming your Drafts folder

**You fill in your own password using a text editor. Claude never sees it.**

## After Setup

Just talk to Claude:

> "幫我看這封信在說什麼，然後我們討論怎麼回。"

> "幫我查有沒有 David 寄來的信。"

> "幫我批次產出這 10 封報價信的草稿。"

## What It Can Do

| Feature | Description |
|---------|-------------|
| Read & summarize | Extract key points from emails |
| List recent | Show latest N emails (read + unread) |
| Discuss & draft | Talk through your reply, Claude writes it |
| Refine | Adjust tone, add details, iterate |
| Reply with threading | Keeps the conversation thread intact |
| Attachments | Attach local files (PDF, Excel, etc.) |
| HTML theme | `--html --theme` wraps email in mobile-safe template |
| Batch templates | Same template × multiple recipients |
| Search | Find emails by subject or sender (supports CJK) |
| Gmail + Outlook | Standard IMAP, works with both |

## Security

| Rule | How it's enforced |
|------|-------------------|
| Never sends email | **Code-level** — `email_ops.py` has no `send` command |
| Never deletes email | **Code-level** — `email_ops.py` has no `delete` command |
| Draft-first | All output goes to your Drafts folder |
| Password protected | Claude guides you to edit credentials yourself, never reads them |

## Requirements

- Python 3.8+
- Claude Pro (Claude Code or Cowork)
- Gmail / Google Workspace / Outlook / Microsoft 365 / Self-hosted IMAP (STARTTLS)
- App Password ([Gmail](https://myaccount.google.com/apppasswords) · [Outlook](https://account.live.com/proofs/AppPassword))

## Related

Part of the [Enterprise AI Breakpoint Framework](https://github.com/YuWenHao1212?tab=repositories&q=bp&type=&language=&sort=) — 9 universal patterns for AI-powered enterprise workflows.

## License

MIT
