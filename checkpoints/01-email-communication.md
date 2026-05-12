# Email & Communication - Curation Checkpoint
## Stage 1: Discover
- Status: done
- Candidates found: 20
- Sources searched:
  - VoltAgent/awesome-openclaw-skills README.md
  - VoltAgent/awesome-openclaw-skills categories/communication.md
  - hermes-agent.nousresearch.com/docs/skills/
  - GitHub search: "openclaw skill email newsletter slack communication"
  - GitHub search: "hermes skill email newsletter slack messaging agent"
  - GitHub search: "openclaw skill gmail email triage inbox agent SKILL.md"
  - GitHub search: "hermes agent skills list email calendar communication"
  - clawskills.sh individual skill pages
  - Andrew-Girgis/microsoft-workspace-skill repo
  - NousResearch/hermes-agent repo

### Candidates:
1. gmail-secretary (openclaw) - Gmail triage via Haiku LLM, label application, draft replies
2. expanso-email-triage (openclaw) - AI-powered email triage with calendar sync and response drafting
3. email-manager-lite (openclaw) - Lightweight IMAP/SMTP email management
4. email-autoreply (openclaw) - Context-aware email reply generation
5. slack (openclaw, built-in) - Slack messaging, reactions, pins, member info
6. microsoft365 (openclaw) - Microsoft 365 Outlook, Calendar, Contacts, OneDrive
7. postwall (openclaw) - Secure email gateway with human-in-the-loop approval
8. coordinate-meeting (openclaw) - Group scheduling via meetlark.ai polls
9. meeting-coordinator (openclaw) - Executive scheduling with email and calendar
10. daily-brief-digest (openclaw) - Morning briefing: emails, calendar, news
11. rocketchat (openclaw) - Rocket.Chat team messaging via REST API
12. google-workspace (hermes) - Gmail, Calendar, Drive, Docs, Sheets via OAuth
13. microsoft-workspace (hermes) - Outlook Calendar, Mail, Contacts via Graph API
14. clawemail (openclaw) - Google Workspace access (Gmail, Drive, Docs, Sheets)
15. agent-mail (openclaw) - Email inbox for AI agents
16. agenticmail (openclaw) - Full email, SMS, storage, multi-agent coordination
17. custom-smtp-sender (openclaw) - Send emails with markdown/HTML support
18. voice-email (openclaw) - Send emails via voice commands
19. sixel-email (openclaw) - 1:1 email channel for agents
20. donotify-voice-call-reminder (openclaw) - Voice call reminders via DoNotify

## Stage 2: Evaluate Relevance
- Status: done
- Candidates after filter: 9
- Rejected (with reasons):
  - expanso-email-triage: Requires "Expanso Edge binary" (niche infrastructure dependency, not accessible for business owners)
  - email-manager-lite: Could not verify page (404), insufficient documentation
  - agent-mail: Primarily developer-focused (API-first email inboxes for AI agents, not for business owners)
  - agenticmail: 63 tools, too complex/developer-oriented (multi-agent coordination)
  - custom-smtp-sender: Basic SMTP sending utility, too low-level for business owners
  - voice-email: Niche accessibility tool, limited adoption (unclear production status)
  - sixel-email: Very limited (1:1 only), niche agent-to-agent channel
  - donotify-voice-call-reminder: Niche notification tool, requires DoNotify service
  - clawemail: Overlaps with google-workspace (hermes) which is better documented
  - daily-brief-digest: Marked "Suspicious" by OpenClaw, depends on multiple CLIs
  - postwall: Historical "Suspicious" flags (v1.2-1.5), recently cleared but limited adoption

### Remaining 9 candidates:
1. gmail-secretary (openclaw)
2. email-autoreply (openclaw)
3. slack (openclaw built-in)
4. microsoft365 (openclaw)
5. coordinate-meeting (openclaw)
6. meeting-coordinator (openclaw)
7. rocketchat (openclaw)
8. google-workspace (hermes)
9. microsoft-workspace (hermes)

## Stage 3: Safety Audit
- Status: done
- Passed: 7
- Failed (with reasons):
  - gmail-secretary: FAILED - OpenClaw flags "suspicious.dangerous_exec, suspicious.llm_suspicious" (HIGH confidence). Uses shell scripts (triage-and-draft.sh, apply-labels.sh) that constitute dangerous exec patterns. Despite VirusTotal "Benign", the persistent Suspicious flag across 22+ versions is a concern.
  - microsoft365 (openclaw): FAILED - VirusTotal flags as "Suspicious". While OpenClaw says "Benign", the VirusTotal flag combined with limited adoption (622 downloads, 3 installs) makes this a risk. The hermes microsoft-workspace skill covers the same use case with cleaner security posture.

### Safety Audit Details for Passed Skills:

#### 1. slack (openclaw built-in)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys, tokens, or credentials (uses bot token from OpenClaw config)
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description

#### 2. google-workspace (hermes)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (uses OAuth2 with user-provided credentials)
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands (requires user confirmation for sends/deletes)
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name, description, version, author, license

#### 3. microsoft-workspace (hermes)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (OAuth2 via Azure Portal)
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands (calendar delete exists but uses standard API)
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name, description, version, author, license

#### 4. coordinate-meeting (openclaw)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls (uses meetlark.ai API legitimately)
- [x] Has valid YAML frontmatter with name and description
- Security: VirusTotal Benign, OpenClaw Benign (HIGH confidence)

#### 5. email-autoreply (openclaw)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- Security: VirusTotal Benign, OpenClaw Benign

#### 6. meeting-coordinator (openclaw)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (uses env vars for credentials)
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands (requires human approval for all outbound actions)
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- Security: VirusTotal Benign, OpenClaw Benign

#### 7. rocketchat (openclaw)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (uses RC_* environment variables)
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls (standard REST API to user's own Rocket.Chat instance)
- [x] Has valid YAML frontmatter with name and description
- Security: VirusTotal Benign, OpenClaw Benign

## Stage 4: Final Selection
- Status: done
- Selected: 5

### Ranking Criteria Applied:
1. Business value: How useful is this for a non-technical business owner managing communication?
2. Documentation quality: Is the skill well-documented with clear setup and usage?
3. Community signal: Downloads, installs, stars, recency of updates

### Final Ranking:
1. **google-workspace (hermes)** - Top pick. Covers Gmail + Calendar + Drive in one skill. 1.1k+ version, MIT licensed, authored by Nous Research. Excellent documentation with 5-step OAuth setup, comprehensive command reference, and safety rules requiring user confirmation. Most complete communication suite.
2. **slack (openclaw)** - Built-in skill, mature and battle-tested. Covers all essential Slack operations (messages, reactions, pins, member info). No external dependencies. Valid frontmatter, clean security.
3. **microsoft-workspace (hermes)** - Covers Outlook email, calendar, contacts via Microsoft Graph API. MIT licensed, community-authored. Clean security with OAuth2 and safe_mail_send.sh helper. Good documentation.
4. **coordinate-meeting (openclaw)** - Practical scheduling tool with 1,415 downloads. Benign on both security scans (HIGH confidence). Unique value: enables both human and AI agent participation in scheduling polls.
5. **rocketchat (openclaw)** - Self-hosted team messaging integration. 482 downloads, Benign on both scans. Valuable for businesses running their own Rocket.Chat instance for internal communication.

### Runners-up (not selected):
- email-autoreply: 0 downloads/installs, no community adoption yet
- meeting-coordinator: 0 downloads/installs, overlaps with coordinate-meeting and google-workspace

## Final Output

- **[Google Workspace](https://github.com/NousResearch/hermes-agent/blob/main/skills/productivity/google-workspace/SKILL.md)** - Manage Gmail, Google Calendar, Drive, Docs, and Sheets through a single OAuth-authenticated skill. Lets your agent read and draft emails, schedule meetings, and organize documents with built-in safety rules that require your approval before sending anything. `hermes`
- **[Slack](https://github.com/openclaw/openclaw/blob/main/skills/slack/SKILL.md)** - Send, read, edit, and pin messages in Slack channels and DMs, add emoji reactions, and look up team member profiles. A built-in skill that turns your agent into a full Slack participant for team communication. `openclaw`
- **[Microsoft Workspace](https://github.com/Andrew-Girgis/microsoft-workspace-skill)** - Access Outlook email, calendar, and contacts via Microsoft Graph API for Hotmail, Outlook.com, and Microsoft 365 accounts. Supports reading, sending, and searching email plus scheduling meetings with Teams links. `hermes`
- **[Coordinate Meeting](https://clawskills.sh/skills/mkelk-coordinate-meeting)** - Automate group scheduling by creating availability polls, collecting votes from both humans and AI agents, and identifying the best meeting time. Works like a smart Doodle alternative powered by your agent. `openclaw`
- **[Rocket.Chat](https://clawskills.sh/skills/zenjabba-rocketchat)** - Integrate with your self-hosted Rocket.Chat server to manage channels, send and read messages, look up users, and configure integrations via REST API. Ideal for businesses that run their own team messaging platform. `openclaw`
