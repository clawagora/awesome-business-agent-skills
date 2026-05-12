# Operations & Admin - Curation Checkpoint
## Stage 1: Discover
- Status: done
- Candidates found: 20
- Sources searched: [VoltAgent/awesome-openclaw-skills README, Hermes Skills Hub (hermes-agent.nousresearch.com), GitHub search for openclaw/hermes skills, 0xNyk/awesome-hermes-agent, openclaw/skills registry, NousResearch/hermes-agent repo, playbooks.com, lobehub.com marketplace]

### Candidate List
1. asana (openclaw) - Manage Asana projects/tasks via REST API
2. better-notion (openclaw) - Full CRUD for Notion pages/databases
3. todoist-task-manager (openclaw) - Manage Todoist tasks from CLI
4. advanced-calendar (openclaw) - Natural language calendar management
5. calctl (openclaw) - Apple Calendar via CLI
6. ai-meeting-scheduling (openclaw) - Automate meeting booking workflows
7. bookameeting (openclaw) - Meeting booking system connector
8. automation-workflows (openclaw) - Workflow templates for ops tasks
9. apple-notes (openclaw) - Manage Apple Notes via CLI
10. bear-notes (openclaw) - Create/search Bear notes
11. agent-audit-trail (openclaw) - Tamper-evident audit logging
12. google-workspace (hermes) - Gmail, Calendar, Drive, Docs, Sheets
13. ocr-and-documents (hermes) - Extract text from PDFs/scans
14. microsoft-workspace-skill (hermes) - M365 email, calendar, contacts
15. cognify-skills (hermes) - CRM, invoicing, project management
16. hermes-plugins (hermes) - Goal management, inter-agent bridge
17. 4todo (openclaw) - Manage 4todo task lists
18. agent-task-manager (openclaw) - Multi-step stateful workflows
19. caldav-calendar (openclaw) - CalDAV calendar integration
20. project-management-skills (openclaw) - PM orchestration OS

## Stage 2: Evaluate Relevance
- Status: done
- Candidates after filter: 8
- Rejected (with reasons):
  - advanced-calendar: Requires Python venv setup, more technical than business-owner friendly
  - calctl: macOS-only, very limited scope
  - ai-meeting-scheduling: Insufficient documentation to verify production-readiness
  - bookameeting: Insufficient documentation to verify production-readiness
  - automation-workflows: Template/guidance document, not a concrete operational tool
  - apple-notes: macOS-only, niche app
  - bear-notes: macOS-only, niche third-party app
  - agent-audit-trail: Developer/governance tool, not business-owner facing
  - cognify-skills: Repository returned 404, cannot verify existence or quality
  - hermes-plugins: 23 technical plugins, AGPL license concern, infrastructure-focused not business-owner facing
  - 4todo: Niche task app with limited community signal
  - agent-task-manager: Agent orchestration tool, developer-facing not business-owner facing
  - caldav-calendar: Technical CalDAV setup, niche use case
  - project-management-skills: Meta-orchestrator, overly complex for non-technical users
  - ocr-and-documents: Useful but more of a utility than an operations/admin skill

### Remaining Candidates (8)
1. asana (openclaw) - Project/task management via Asana API
2. todoist-task-manager (openclaw) - Task management via Todoist CLI
3. better-notion (openclaw) - Notion workspace management
4. google-workspace (hermes) - Full Google Workspace suite
5. microsoft-workspace-skill (hermes) - Microsoft 365 integration
6. notion (hermes) - Hermes built-in Notion skill
7. linear (hermes) - Issue/project tracking
8. teams-meeting-pipeline (hermes) - Meeting notes extraction from Teams

## Stage 3: Safety Audit
- Status: done
- Passed: 8
- Failed (with reasons): none

### Audit Details

1. **asana (openclaw)** - PASSED
   - [x] No curl|bash or remote code execution
   - [x] No hardcoded API keys (uses ASANA_PAT env var, config files)
   - [x] No data exfiltration
   - [x] No prompt injection
   - [x] No destructive commands
   - [x] No obfuscated payloads
   - [x] No unauthorized network calls (Asana API only)
   - [x] Has valid YAML frontmatter with name and description

2. **todoist-task-manager (openclaw)** - PASSED
   - [x] No curl|bash or remote code execution
   - [x] No hardcoded API keys (token in config file)
   - [x] No data exfiltration
   - [x] No prompt injection
   - [x] No destructive commands (delete is legitimate task management)
   - [x] No obfuscated payloads
   - [x] No unauthorized network calls (Todoist API only)
   - [x] Has valid YAML frontmatter with name and description

3. **better-notion (openclaw)** - PASSED
   - [x] No curl|bash piping (curl used for Notion API, legitimate)
   - [x] No hardcoded API keys (stored in ~/.config/notion/api_key)
   - [x] No data exfiltration
   - [x] No prompt injection
   - [x] No destructive commands (delete moves to trash, reversible)
   - [x] No obfuscated payloads
   - [x] No unauthorized network calls (api.notion.com only)
   - [x] Has valid YAML frontmatter with name and description
   - Note: Health score D (69/100) is a minor concern

4. **google-workspace (hermes)** - PASSED
   - [x] No curl|bash or remote code execution
   - [x] No hardcoded API keys (OAuth2 token in local file)
   - [x] No data exfiltration
   - [x] No prompt injection
   - [x] No destructive commands (requires user confirmation)
   - [x] No obfuscated payloads
   - [x] No unauthorized network calls (Google APIs only)
   - [x] Has valid YAML frontmatter with name and description
   - Strong security: OAuth2 PKCE, user confirmation for all mutations

5. **microsoft-workspace-skill (hermes)** - PASSED
   - [x] No curl|bash or remote code execution
   - [x] No hardcoded API keys (OAuth2 via Azure, local token files)
   - [x] No data exfiltration
   - [x] No prompt injection (safe_mail_send.sh prevents shell injection)
   - [x] No destructive commands
   - [x] No obfuscated payloads
   - [x] No unauthorized network calls (Microsoft Graph API only)
   - [x] Has valid YAML frontmatter with name and description

6. **notion (hermes)** - PASSED
   - [x] No curl|bash or remote code execution
   - [x] No hardcoded API keys (NOTION_API_KEY env var)
   - [x] No data exfiltration
   - [x] No prompt injection
   - [x] No destructive commands
   - [x] No obfuscated payloads
   - [x] No unauthorized network calls (api.notion.com only)
   - [x] Has valid YAML frontmatter with name and description

7. **linear (hermes)** - PASSED
   - [x] No curl|bash or remote code execution
   - [x] No hardcoded API keys (LINEAR_API_KEY env var)
   - [x] No data exfiltration
   - [x] No prompt injection
   - [x] No destructive commands
   - [x] No obfuscated payloads
   - [x] No unauthorized network calls (Linear GraphQL API only)
   - [x] Has valid YAML frontmatter with name and description

8. **teams-meeting-pipeline (hermes)** - PASSED
   - [x] No curl|bash or remote code execution
   - [x] No hardcoded API keys (env vars for MSGRAPH credentials)
   - [x] No data exfiltration
   - [x] No prompt injection
   - [x] No destructive commands (delete-subscription requires explicit ID)
   - [x] No obfuscated payloads
   - [x] No unauthorized network calls (Microsoft Graph API only)
   - [x] Has valid YAML frontmatter with name and description

## Stage 4: Final Selection
- Status: done
- Selected: 5

### Ranking Rationale
1. **google-workspace** - Highest business value (covers email, calendar, docs, sheets, drive in one skill), official Hermes skill with excellent documentation, strong community signal
2. **asana** - High business value for project management, clean security model, well-documented CLI with PAT auth
3. **todoist-task-manager** - Strong business value for daily task management, mature CLI tool, good filter/label support
4. **microsoft-workspace-skill** - High value for M365-based businesses (email, calendar, contacts, Teams), well-documented with security-conscious design
5. **teams-meeting-pipeline** - Unique meeting notes extraction capability with high business value, official Hermes skill

### Why others were not selected
- **better-notion (openclaw)**: Health score D (69/100) and overlaps with Hermes notion skill; lower community signal
- **notion (hermes)**: Good but overlaps with google-workspace for document management; less differentiated
- **linear (hermes)**: More developer-oriented than business-owner facing; Asana better serves non-technical PM needs

## Final Output

- **[Google Workspace](https://github.com/NousResearch/hermes-agent/blob/main/skills/productivity/google-workspace/SKILL.md)** - Unified access to Gmail, Google Calendar, Drive, Docs, and Sheets through OAuth2, letting a business owner manage email, schedule meetings, organize files, and update spreadsheets all from one agent skill. `hermes`
- **[Asana](https://github.com/k0nkupa/openclaw-asana-skill)** - Connects your agent to Asana for listing workspaces, creating and completing tasks, searching projects, and posting comments, giving business owners hands-free project management. `openclaw`
- **[Todoist Task Manager](https://github.com/openclaw/skills/blob/main/skills/2mawi2/todoist-task-manager/SKILL.md)** - Manages Todoist tasks through natural language, supporting filters, priorities, labels, and projects so a business owner can add, complete, and organize daily to-dos without leaving their chat. `openclaw`
- **[Microsoft Workspace](https://github.com/Andrew-Girgis/microsoft-workspace-skill)** - Integrates Microsoft 365 via Graph API for managing Outlook email, calendar events with Teams video links, free/busy scheduling, and contacts, ideal for businesses running on the Microsoft stack. `hermes`
- **[Teams Meeting Pipeline](https://github.com/NousResearch/hermes-agent/blob/main/skills/productivity/teams-meeting-pipeline/SKILL.md)** - Automatically summarizes Microsoft Teams meetings, extracts action items, and manages the meeting-notes pipeline so business owners never lose track of decisions and follow-ups. `hermes`
