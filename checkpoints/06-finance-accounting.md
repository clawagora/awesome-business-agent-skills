# Finance & Accounting - Curation Checkpoint
## Stage 1: Discover
- Status: done
- Candidates found: 20+
- Sources searched:
  - VoltAgent/awesome-openclaw-skills README.md
  - hermes-agent.nousresearch.com/docs/skills/
  - openclawai.io/skills/finance (105 finance tools)
  - GitHub search: "openclaw skill invoice accounting finance"
  - GitHub search: "hermes skill expense bookkeeping tax"
  - playbooks.com/skills/openclaw/skills/ (accounting, expense-report, financial-overview, etc.)
  - clawskills.sh skill pages
  - agentskills.io ecosystem search

### Candidates Identified:
1. Bookkeeper (h4gen) - Meta-skill orchestrating gmail, OCR, stripe, xero
2. AccountsOS (paulgosnell) - AI-native accounting for UK micro-businesses
3. EzBookkeeping (mayswind) - Self-hosted personal finance app integration
4. Expense Report (openclaw/skills) - Business expense organizer for reimbursement/tax
5. Financial Overview (openclaw/skills) - Consolidated financial dashboard
6. Expense Tracker Pro (jhillin8) - Natural language expense tracking
7. Smart Expense Tracker (openclaw/skills) - Local-first AI expense tracker
8. Intelligent Budget Tracker (openclaw/skills) - TypeScript library for AI agents
9. Accounting (openclaw/skills) - Bookkeeping to professional practice reference
10. ERPClaw (openclaw/skills) - Full ERP system with accounting, invoicing, payroll
11. Invoice Chaser (audsmith28) - Automated invoice follow-up sequences
12. Invoice Engine (afrexai) - Invoice generation with recurring billing
13. AI CFO (aiwithabidi) - P&L, revenue tracking, cash flow forecasting
14. Wave (aiwithabidi) - Small business accounting CLI
15. Payment (openclaw/skills) - Payment processing and invoice management
16. Accounting Assistant (akkualle) - German accounting with DATEV export
17. Personal Finance (openclaw/skills) - SQLite-backed personal finance tracker
18. Bexio (rdewolff) - Swiss business software API integration
19. Xero (mrgoodb) - Xero accounting integration
20. Actual Budget (thisisjeron) - Personal finance via Actual Budget app

## Stage 2: Evaluate Relevance
- Status: done
- Candidates after filter: 10
- Rejected (with reasons):
  - Invoice Engine (afrexai): 0 installs, 1.1/5 quality rating, not production-ready
  - AI CFO (aiwithabidi): 0 installs, 2/5 quality, no verifiable source code
  - Wave (aiwithabidi): 0 installs, 1/5 quality rating, not production-ready
  - Invoice Chaser (audsmith28): Flagged SUSPICIOUS by both VirusTotal and OpenClaw
  - Accounting Assistant (akkualle): 0 installs, 2.1/5, pricing contradiction, German-only
  - Bexio (rdewolff): Very niche (Swiss-only), limited documentation
  - Xero (mrgoodb): Could not verify source code, limited details
  - Personal Finance (openclaw/skills): SQLite personal tracker, less business-oriented
  - Intelligent Budget Tracker: TypeScript library, more developer-oriented than business owner
  - Payment (openclaw/skills): More developer-oriented (gateway integration), could not verify full source

### Remaining 10 candidates for safety audit:
1. Expense Report (openclaw/skills)
2. Financial Overview (openclaw/skills)
3. Expense Tracker Pro (jhillin8)
4. Smart Expense Tracker (openclaw/skills)
5. Accounting (openclaw/skills)
6. ERPClaw (openclaw/skills)
7. AccountsOS (paulgosnell)
8. Bookkeeper (h4gen)
9. EzBookkeeping (mayswind)
10. Actual Budget (thisisjeron)

## Stage 3: Safety Audit
- Status: done
- Passed: 7
- Failed (with reasons):
  - Bookkeeper (h4gen): Flagged SUSPICIOUS by both VirusTotal and OpenClaw; requires MATON_API_KEY gateway; 0 current installs
  - EzBookkeeping (mayswind): Flagged SUSPICIOUS by VirusTotal; bundles scripts requiring non-standard deployment; mixed safety signals
  - Actual Budget (thisisjeron): Flagged SUSPICIOUS by OpenClaw; prior version (1.0.1) flagged by VirusTotal; history of insecure TLS handling (NODE_TLS_REJECT_UNAUTHORIZED=0)

### Safety Audit Details for Passed Skills:

#### 1. Expense Report
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys, tokens, or credentials
- [x] No data exfiltration (sending data to unknown endpoints)
- [x] No prompt injection (hidden instructions to override agent behavior)
- [x] No destructive commands (rm -rf, DROP TABLE, etc.)
- [x] No obfuscated/encoded payloads (base64 blobs, eval(), exec())
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- Notes: Pure documentation/template skill. No executable components. Explicit disclaimer about limitations.

#### 2. Financial Overview
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys, tokens, or credentials
- [x] No data exfiltration (sending data to unknown endpoints)
- [x] No prompt injection (hidden instructions to override agent behavior)
- [x] No destructive commands (rm -rf, DROP TABLE, etc.)
- [x] No obfuscated/encoded payloads (base64 blobs, eval(), exec())
- [x] No unauthorized network calls (uses declared MCP dependency: norman-finance)
- [x] Has valid YAML frontmatter with name and description
- Notes: Read-only financial dashboard. All API calls via declared MCP connector.

#### 3. Expense Tracker Pro
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys, tokens, or credentials
- [x] No data exfiltration -- "All data stays local on your machine"
- [x] No prompt injection (hidden instructions to override agent behavior)
- [x] No destructive commands (rm -rf, DROP TABLE, etc.)
- [x] No obfuscated/encoded payloads (base64 blobs, eval(), exec())
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- Notes: Local-only data storage. Platform security review marked safe.

#### 4. Smart Expense Tracker
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys, tokens, or credentials
- [x] No data exfiltration -- "makes no external network calls"
- [x] No prompt injection (hidden instructions to override agent behavior)
- [x] No destructive commands (rm -rf, DROP TABLE, etc.)
- [x] No obfuscated/encoded payloads (base64 blobs, eval(), exec())
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- Notes: Strict local-only operation at ~/.openclaw/expense-tracker/. Backup rotation keeps 4 weekly snapshots.

#### 5. Accounting
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys, tokens, or credentials
- [x] No data exfiltration (sending data to unknown endpoints)
- [x] No prompt injection (hidden instructions to override agent behavior)
- [x] No destructive commands (rm -rf, DROP TABLE, etc.)
- [x] No obfuscated/encoded payloads (base64 blobs, eval(), exec())
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- Notes: Educational/reference skill. Adapts to user role. Appropriately flags when professional consultation needed.

#### 6. ERPClaw
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys, tokens, or credentials
- [x] No data exfiltration -- local-first architecture, core functions work offline
- [x] No prompt injection (hidden instructions to override agent behavior)
- [x] No destructive commands -- immutable GL entries, cancellations create reversals not deletions
- [x] No obfuscated/encoded payloads -- explicitly prohibits raw SQL
- [x] No unauthorized network calls -- only fetch-exchange-rates (public API) and GitHub module ops
- [x] Has valid YAML frontmatter with name and description
- Notes: Local SQLite DB. RBAC with PBKDF2-HMAC-SHA256. Parameterized queries. Confirmation required before destructive actions. v3.1.2.

#### 7. AccountsOS
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys -- uses ACCOUNTSOS_API_KEY env var
- [x] No data exfiltration -- all operations within AccountsOS system
- [x] No prompt injection (hidden instructions to override agent behavior)
- [x] No destructive commands (rm -rf, DROP TABLE, etc.)
- [x] No obfuscated/encoded payloads -- base64 for document upload is standard/documented
- [x] No unauthorized network calls -- all calls to declared AccountsOS API
- [x] Has valid YAML frontmatter with name and description
- Notes: Benign status from both VirusTotal and OpenClaw. 942 downloads. Three permission scopes (read/write/admin). UK micro-business focused.

## Stage 4: Final Selection
- Status: done
- Selected: 5

### Ranking criteria:
1. Business value: How useful is this to a non-technical business owner?
2. Documentation quality: How well-documented and easy to understand?
3. Community signal: Downloads, installs, quality ratings, security status

### Rankings:
1. **ERPClaw** - Highest business value (full ERP with 365+ actions across 14 domains), excellent documentation, v3.1.2 maturity, strong safety design
2. **AccountsOS** - Strong business value for UK businesses (VAT, deadlines, invoices), 942 downloads (highest), benign security status, well-documented API
3. **Expense Report** - High practical value (IRS-aligned templates, tax-ready reports), clean safe skill, MIT license, clear limitations stated
4. **Financial Overview** - Direct business value (financial dashboard with actionable recommendations), clean MCP integration, read-only safety
5. **Accounting** - Broad utility (adapts from small business to professional), excellent documentation quality, comprehensive coverage of QuickBooks/Xero workflows

### Runners-up:
6. Smart Expense Tracker - Excellent privacy/safety but more personal than business-oriented
7. Expense Tracker Pro - Solid but overlaps with Smart Expense Tracker; less documented

## Final Output

- **[ERPClaw](https://playbooks.com/skills/openclaw/skills/erpclaw)** - AI-native ERP system offering full double-entry accounting, invoicing, inventory, purchasing, tax compliance, HR, and payroll in a single local-first install with 365+ actions and an immutable audit trail. `openclaw`
- **[AccountsOS](https://playbooks.com/skills/openclaw/skills/accountsos)** - AI-native accounting for UK micro-businesses, handling transaction tracking, VAT management, filing deadline alerts, invoice management, and document storage with automated categorization. `openclaw`
- **[Expense Report](https://playbooks.com/skills/openclaw/skills/expense-report)** - Organizes and categorizes business expenses into clear, IRS-aligned reimbursement and tax-ready reports with categorized summaries, line items, and missing-documentation checklists. `openclaw`
- **[Financial Overview](https://playbooks.com/skills/openclaw/skills/financial-overview)** - Provides a consolidated financial dashboard combining current balance, recent cash flow, outstanding invoices, and upcoming tax obligations with actionable recommendations. `openclaw`
- **[Accounting](https://playbooks.com/skills/openclaw/skills/accounting)** - Comprehensive accounting reference that adapts from basic bookkeeping to professional practice, covering journal entries, bank reconciliation, QuickBooks/Xero workflows, and revenue recognition standards. `openclaw`
