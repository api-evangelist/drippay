---
name: Drip
description: Use when helping users set up customer conversation history, search customer context, draft replies, manage integrations, or configure follow-up workflows. Agents should reach for this skill when users need to connect communication tools, search customer history, review drafts before sending, or set up automated meeting follow-up.
metadata:
    mintlify-proj: drip
    version: "1.0"
---

# Drip (dripos) Skill

## Product summary

Drip (dripos) is a macOS app that centralizes customer conversation history from email, messaging, and calendar tools into a searchable local database. Agents use it to help users connect communication sources (iMessage, Gmail, Slack, LinkedIn, Stripe, meeting tools), search customer context, draft replies with AI assistance, and run background follow-up workflows. The app is local-first—customer history stays on the user's Mac. Key entry points: **Integrations** (connect sources), **Inbox** (search and view customer context), **Drafts** (review before sending), **Settings** (configure AI, meeting follow-up, AutoSend rules). Primary docs: https://docs.usedrip.ai

## When to use

Reach for this skill when:
- A user needs to connect a communication tool (iMessage, Gmail, Slack, LinkedIn, Stripe, Granola, Circleback, Cal.com, Calendly) to Drip
- A user wants to search customer history by name, company, email, phone, handle, or message text
- A user needs to review or edit AI-drafted replies before sending
- A user is setting up meeting follow-up (post-meeting Slack channels and email drafts)
- A user wants to enable background follow-up (Autopilot) with review rules
- A user needs to import leads from a CRM or external tool
- A user is troubleshooting LinkedIn connection issues or sync problems
- A user needs to understand what data stays local vs. what reaches cloud services

Do not use this skill for: account creation, billing, macOS system permissions (beyond explaining what Drip needs), or general AI/LLM configuration outside Drip's Settings.

## Quick reference

### Integration sources and what they add

| Source | Adds | Permissions needed |
|--------|------|-------------------|
| iMessage | local Messages history, approved text sends | Full Disk Access, Messages automation |
| Google | Gmail threads, Calendar meetings | Google sign-in consent |
| Slack | workspace messages, DMs, shared channels, drafts | Slack workspace consent |
| LinkedIn | DMs, group chats, media, history import, drafts | LinkedIn browser login |
| Stripe | customer and revenue signals | Stripe Connect consent |
| Granola | AI meeting notes, transcripts, attendees | Granola MCP OAuth |
| Circleback | meetings, transcripts, calendar, email, actions | Circleback MCP OAuth |
| Cal.com | scheduling context for booking actions | Cal.com MCP OAuth |
| Calendly | scheduling context for booking actions | Calendly MCP OAuth |

### Core workflows

| Task | Steps |
|------|-------|
| **Connect a source** | Open Integrations → click source card → follow auth flow → return to Integrations |
| **Sync all sources** | Open Integrations → click **Sync all** (first sync may take minutes) |
| **Search customer history** | Open Inbox → search by name, company, email, phone, handle, or message text |
| **Review a draft** | Open Drafts → review, edit, approve, reject, or send (never sent silently) |
| **Enable meeting follow-up** | Settings → Meeting follow-up → click **Enable** → optionally click **Run now** |
| **Import leads** | Open Leads → click **Set up lead import** → copy endpoint/header/body → configure webhook in external tool → send test lead → click **Import leads** |
| **Disconnect a source** | Open Integrations → choose source → click **Disconnect** |

### Copilot commands (plain English)

- "what needs my reply?"
- "draft replies for everyone waiting on me"
- "prep me for my call with [name]"
- "who went quiet?"
- "sync my inbox"
- "search wins for past similar deals"

### Lead import JSON schema

```json
{
  "leads": [
    {
      "externalId": "crm-contact-123",
      "name": "Ava Founder",
      "company": "Finch Pay",
      "email": "ava@finch.test",
      "linkedinUrl": "https://linkedin.com/in/ava",
      "painSignal": "visited pricing page twice"
    }
  ]
}
```

A lead needs at least `name` and one reachable channel (`email`, `phone`, or `linkedinUrl`) to be useful for outreach.

## Decision guidance

### When to use which integration first

| Scenario | Recommended order |
|----------|-------------------|
| Sales team, mostly email | Google → Slack → LinkedIn |
| Customer success, mixed channels | iMessage → Google → Slack → Stripe |
| Enterprise, Slack-heavy | Slack → Google → LinkedIn |
| Revenue-focused | Stripe (early) + conversation sources |
| Meeting-heavy | Google + Granola or Circleback |

### When to enable meeting follow-up

| Condition | Enable? | Why |
|-----------|---------|-----|
| Team uses Slack Connect with customers | Yes | Channels are expected, approval is predictable |
| First meetings don't warrant Slack channels | No | Creates noise, low adoption |
| Slack Connect approval blocks most invites | No | Gmail draft fallback is not enough |
| Need guaranteed instant external access | No | Slack Connect acceptance still required |
| Only need email follow-up drafts | No | Use Gmail drafts without automation |
| Need verified meeting attendance | No | Drip cannot verify Google Meet/Zoom attendance yet |

### When to use Autopilot (background follow-up)

| Condition | Use Autopilot? | Why |
|-----------|----------------|-----|
| Team has clear, approved follow-up rules | Yes | Reduces manual work, respects review settings |
| Follow-up is sensitive or variable | No | Keep manual review for each message |
| Need to respect channel permissions | Yes | Autopilot still follows channel auth rules |
| Want to send without review | No | Drip requires review/approval rules even with Autopilot |

## Workflow

### Typical setup and usage flow

1. **Install and sign in**
   - Download dripos for Mac from usedrip.ai/download/mac
   - Open the app, sign in with email or Google
   - Allow macOS to open dripos from browser if prompted

2. **Connect sources**
   - Open **Integrations**
   - Start with 1–2 sources where customer conversations already happen (e.g., Google for email, Slack for workspace)
   - Click each source card, complete the auth flow, return to Integrations
   - Do not connect everything at once; add more sources later as needed

3. **Run first sync**
   - Click **Sync all** in Integrations
   - Wait for sync to complete (may take several minutes depending on history volume)
   - User can continue using the app while sync runs

4. **Search and review customer context**
   - Open **Inbox**
   - Search by person name, company, email, phone, handle, or message text
   - Review person pages: recent conversations, timeline, meeting notes, revenue signals, reply drafts
   - Use Copilot to ask questions about customer status or prep for calls

5. **Review and send drafts**
   - Open **Drafts**
   - Review AI-drafted replies (Gmail, Slack, iMessage, LinkedIn)
   - Edit, approve, reject, or send
   - Drafts are never sent silently

6. **Optional: Set up meeting follow-up**
   - Open **Settings** → **Meeting follow-up**
   - Click **Enable** to create post-meeting Slack channels and email drafts
   - Optionally click **Run now** to scan recent meetings
   - Monitor Slack Connect invites for external attendees

7. **Optional: Import leads**
   - Open **Leads** → **Set up lead import**
   - Copy the endpoint, Authorization header, and JSON body
   - In the external tool (CRM, form, Zapier, etc.), create a webhook/HTTP POST action
   - Paste the copied values, send a test lead, return to dripos, click **Import leads**

### Troubleshooting a specific issue

1. **LinkedIn shows "local bridge session is missing"**
   - Reconnect LinkedIn from Integrations
   - This refreshes the browser bridge session dripos needs for sync and send

2. **LinkedIn shows "Cooling down"**
   - Wait and try again later
   - Do not repeatedly reconnect; throttling gets worse
   - LinkedIn rate-limits aggressive reconnect attempts

3. **Sync is slow or incomplete**
   - Check that all sources are connected in Integrations
   - Verify network connectivity
   - For LinkedIn, ensure the bridge session is active (not "missing")
   - Run **Sync all** again

4. **Slack Connect invite fails for external attendees**
   - Check Slack workspace policy and admin permissions
   - Verify Slack plan supports Slack Connect
   - Check for Slack errors: `missing_scope`, `not_allowed_token_type`, `no_external_invite_permission`, `restricted_action`, `not_paid`
   - If blocked, use the Gmail draft fallback or complete the invite manually
   - Reconnect Slack to refresh the session (does not grant new bot scopes in current desktop path)

5. **iMessage sync not working**
   - Verify Full Disk Access is granted: System Settings → Privacy & Security → Full Disk Access → check dripos
   - For sending texts, also grant Messages automation permission
   - Reconnect iMessage from Integrations

## Common gotchas

- **Drafts are never sent silently.** All AI-drafted replies require explicit approval before sending. This is by design; always review before approving.

- **LinkedIn history import is conservative.** Drip does not aggressively fetch LinkedIn profile pictures or history. It prefers names, initials, handles, and already-available contact metadata. Reconnect LinkedIn if the bridge session is missing.

- **Slack Connect invites are best-effort.** External attendees may need to accept the invite, their admin may need to approve it, and your workspace admin may need to approve it. Slack workspace policy can block the invite entirely. The current desktop path does not have bot-scoped Slack Connect permissions, so reconnecting Slack does not grant new `conversations.inviteShared` scope.

- **Lead import requires a reachable channel.** A lead needs at least `name` and one of `email`, `phone`, or `linkedinUrl` to be useful for outreach. Importing leads does not send messages by itself; outreach still follows review and AutoSend settings.

- **Disconnecting a source stops new sync but may not delete local history.** Local history already synced on the Mac may remain until local app data is removed. Signing out removes the app session but does not delete local history.

- **Meeting follow-up runs after a grace window.** Drip does not create Slack channels live during the meeting; it waits for the meeting to end, then creates the channel and drafts. No-show drafts only run when there is clear evidence (attendee declined, calendar shows "no show").

- **Copilot uses the selected AI provider.** If you use Anthropic or OpenAI, Drip sends context to that provider. If you use Ollama, the request stays on your Mac. Check Settings → AI to see which provider is active.

- **iMessage requires macOS permissions.** Full Disk Access is required to read local Messages history. Sending texts also requires Messages automation permission. Users can revoke both in System Settings → Privacy & Security.

- **Group conversations are separate from person threads.** Slack channels, Slack threads, iMessage groups, and LinkedIn group chats appear as their own rows in Inbox, not as one-person threads. This prevents misreading a shared channel as a single-person conversation.

- **Fathom, Pocket AI, and Google Messages are secondary.** These sources have backend plumbing but are not normal first-class Integrations cards in the current Mac app. Only use them if the app shows an explicit control for that source.

## Verification checklist

Before confirming a setup or workflow is complete:

- [ ] All required sources are connected in **Integrations** (at least 2–3 for useful context)
- [ ] **Sync all** has completed at least once (check Integrations for sync status)
- [ ] **Inbox** search returns results for a known customer or contact
- [ ] Person page shows timeline, recent conversations, or meeting notes (depending on sources connected)
- [ ] **Drafts** queue is visible and shows any pending AI-drafted replies
- [ ] If using meeting follow-up: **Settings** → **Meeting follow-up** is enabled and shows automation rules
- [ ] If importing leads: lead JSON includes `name` and at least one reachable channel (`email`, `phone`, or `linkedinUrl`)
- [ ] If using Copilot: **Settings** → **AI** shows the selected provider (Anthropic, OpenAI, or Ollama)
- [ ] If using iMessage: Full Disk Access is granted in System Settings → Privacy & Security
- [ ] If using LinkedIn: bridge session is active (not showing "local bridge session is missing")
- [ ] No drafts are pending review if the user expects them to be sent

## Resources

Comprehensive page-by-page navigation: https://docs.usedrip.ai/llms.txt

Critical documentation pages:
- [Quickstart](https://docs.usedrip.ai/quickstart) — installation, sign-in, connecting sources, first sync, using Inbox
- [Integrations](https://docs.usedrip.ai/integrations) — detailed source setup, lead import, sync behavior, disconnect
- [Features](https://docs.usedrip.ai/features) — Inbox search, timelines, drafts, Copilot, Account Signals, background follow-up

---

> For additional documentation and navigation, see: https://docs.usedrip.ai/llms.txt