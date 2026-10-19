# LeakData Breach Response

![LeakData](assets/logo.png)

Understand a data breach and choose your next steps with LeakData in Claude.

Look up a company or website to see known breaches, the types of data exposed,
and practical first steps. Browse recent breaches in LeakData's public catalog
without connecting an account.

Connect your LeakData account to check its verified primary email, review
existing monitoring results, and work through your action plan. Ask Claude
to guide you through the most urgent steps. When you confirm that you finished
a specific step and want to record it, Claude can save it as done in LeakData,
or reopen it at your request.

For your company, learn what domain monitoring checks and how to verify
ownership. This plugin can show public catalog entries for a supplied domain.
It does not search staff email addresses or turn on monitoring.

## Get started

1. Add the plugin to Claude.
2. Open its **Connectors** tab and add or connect **LeakData**. If you already
   use the LeakData directory connector, the plugin uses the same server URL.
3. Sign in to LeakData through the connection flow when using account features.
   Never paste passwords, API keys, access tokens, or authentication codes into
   a conversation.
4. Ask a question, for example:
   - "Was Canva in a data breach? What data was exposed?"
   - "What are the latest breaches in LeakData's catalog?"
   - "Has my verified email been in a data breach?"
   - "Help me work through my breach action plan."
   - "What does monitoring my company's domain involve?"

The package contains a skill and a remote MCP connector for Claude chat,
Cowork, and Claude Code. Connector availability may depend on your Claude
plan and organization settings. Account features also depend on your
LeakData account's access. Interactive cards depend on the host; a text
answer remains available when cards are not supported.

## What the plugin can do

| Feature | Tool | Access |
| --- | --- | --- |
| Look up public breaches | `leakdata.breach_lookup` | Public |
| Browse recent breaches | `leakdata.recent_breaches` | Public |
| Explain company-domain monitoring | `leakdata.company_monitoring` | Public guidance and catalog information |
| Check your verified primary email | `leakdata.search` | Linked account |
| Review existing monitoring results | `leakdata.protection_summary` | Linked account |
| Read your action plan | `leakdata.action_plan` | Linked account |
| Save or reopen a confirmed step | `leakdata.mark_step_done` | Linked account with action-plan permission |

The first six tools are read-only. The last tool updates only the status of
the selected step in your LeakData action plan. It does not change passwords,
enable MFA, or modify settings on any other service. It requires your
confirmation for the specific step.

## Data and privacy

The plugin declares one service: **https://leakdata.io/mcp**. It contains no
local executable, install script, hook, background job, or separate analytics
client. It does not access local files or collect credentials.

For public lookups, the connector receives the company, service, or domain
you ask about and relevant tool arguments, such as a result limit. Account
features use the account you authorize through OAuth. They may return
minimized exposure findings, masked monitored addresses, monitoring summaries,
and action-plan steps to your Claude conversation. If you explicitly supply
your own email, it can be sent for verification against the linked account's
verified primary email; it cannot be used to search other people's accounts.

Saving progress sends a step identifier and its new completion state to
LeakData, which stores that change in your account. The plugin itself has no
separate datastore or retention schedule. The hosted service's processing and
retention are described in the [LeakData Privacy Policy](https://leakdata.io/privacy);
Claude's own conversation and retention settings also apply.

No raw leaked records or passwords are returned. Do not share passwords in
chat. Password-prefix checks are not part of this version.

## Understand the limits

Results cover the data LeakData holds. No match does not mean that an account
or company is safe. A public breach lookup does not determine whether your
email was affected. Some public breach records do not support email checks.
Recent results reflect LeakData's catalog, not every incident worldwide.
Company-monitoring guidance does not reveal employee data, verify domain
ownership, or activate a subscription.

You can ask questions in your preferred language. Card appearance and language
depend on the Claude surface and the languages supported by the hosted
connector.

## Publisher and support

Published by **CyberVisir Solutions Ltd**, the operator of LeakData.io.

- [Website](https://leakdata.io)
- [Claude integration](https://leakdata.io/integrations/claude)
- [Support](https://leakdata.io/contact)
- [Privacy policy](https://leakdata.io/privacy)
- [Service terms](https://leakdata.io/terms)

The MIT license covers the plugin's instructions and configuration. It does
not grant access to LeakData's hosted data or services, which remain governed
by their service terms. Product names and logos remain their owners' property.
