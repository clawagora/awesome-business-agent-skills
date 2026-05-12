# Awesome Business Agent Skills [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of AI agent skills, templates, and resources to help business owners automate operations, customer support, marketing, and more.

AI agents are transforming how businesses operate. But finding the right skills — the modular capabilities that make agents actually useful — is hard. Skill registries contain thousands of entries, many untested, some unsafe. This list cuts through the noise and highlights **50 production-ready, security-audited skills** organized by business function.

Whether you run an e-commerce store, a consulting firm, or a SaaS company, these skills can help you automate the repetitive work and focus on what matters.

## How We Curate

Every skill on this list went through a 4-stage pipeline before being included. We don't list skills based on popularity alone — we verify them.

### Stage 1: Discover

We search across multiple skill registries and repositories:

- [OpenClaw ClawHub](https://github.com/openclaw/skills) — 13,700+ community-built skills
- [Hermes Agent Skills Hub](https://hermes-agent.nousresearch.com/docs/skills/) — 672 skills across 4 registries
- GitHub repositories from independent authors and organizations
- Community indexes like [clawskills.sh](https://clawskills.sh), [clawhub.ai](https://clawhub.ai), and [playbooks.com](https://playbooks.com)

For the initial curation, we ran 10 parallel agents (one per category), each independently searching these sources. They collectively reviewed **~184 candidates**.

### Stage 2: Evaluate Relevance

Each candidate is evaluated against three questions:

1. **Is this useful to a non-technical business owner?** Developer tools, coding utilities, and infrastructure skills are filtered out.
2. **Is this production-ready?** Proof-of-concepts, abandoned repos, and skills with zero community adoption are excluded.
3. **Does it fit the category?** Skills are placed where a business owner would look for them.

This stage reduced candidates from ~184 to ~89.

### Stage 3: Security Audit

Every remaining skill's source code (SKILL.md, scripts, API calls) is fetched and reviewed against an 8-point safety checklist:

- [ ] No `curl | bash` or remote code execution patterns
- [ ] No hardcoded API keys, tokens, or credentials
- [ ] No data exfiltration (sending data to unknown endpoints)
- [ ] No prompt injection (hidden instructions to override agent behavior)
- [ ] No destructive filesystem commands (`rm -rf`, `DROP TABLE`, etc.)
- [ ] No obfuscated or encoded payloads (`base64` blobs, `eval()`, `exec()`)
- [ ] No unauthorized network calls to unknown domains
- [ ] Valid YAML frontmatter with `name` and `description`

We cross-reference with VirusTotal and OpenClaw's moderation system. Skills flagged as **Suspicious** by either system are rejected. Skills whose source code cannot be fetched (404) are also rejected — if we can't read it, we don't list it.

**11 skills were rejected** in this stage, including candidates flagged for dangerous exec patterns, data exfiltration through third-party proxies, TLS bypass, and leaked credentials on hosting platforms.

### Stage 4: Final Selection

Remaining candidates are ranked by:

1. **Business value** — Does this solve a real problem a business owner would pay to fix?
2. **Documentation quality** — Can someone understand what it does in 10 seconds?
3. **Community signal** — Downloads, installs, version maturity, author reputation

We select the top 5 per category. The full audit trail for every skill — including rejected candidates and reasons — is published in the [`checkpoints/`](checkpoints/) directory.

---

## Contents

- [Platforms](#platforms)
- [Email & Communication](#email--communication)
- [Customer Support](#customer-support)
- [Sales & CRM](#sales--crm)
- [Content & Marketing](#content--marketing)
- [Operations & Admin](#operations--admin)
- [Finance & Accounting](#finance--accounting)
- [HR & Recruiting](#hr--recruiting)
- [Legal & Compliance](#legal--compliance)
- [E-Commerce](#e-commerce)
- [Data & Analytics](#data--analytics)
- [Integrations](#integrations)
- [Learning Resources](#learning-resources)
- [Community](#community)
- [Contributing](#contributing)

## Platforms

Where to deploy and run your agent skills.

- [OpenClaw](https://github.com/openclaw/openclaw) - Open-source personal AI assistant and gateway. Connects 20+ messaging channels (Slack, Telegram, WhatsApp, Discord, etc.) to AI agents. Self-hosted or managed. ([Docs](https://docs.openclaw.ai/))
- [Hermes Agent](https://github.com/NousResearch/hermes-agent) - Self-improving AI agent by Nous Research with a built-in learning loop. Creates skills from experience, remembers across sessions, runs on 20+ platforms. ([Docs](https://hermes-agent.nousresearch.com/docs/))
- [ClawAgora](https://www.clawagora.com) - Managed hosting platform and workspace template marketplace for OpenClaw agents. One-click deployment, no coding or self-hosting required. ([Pricing](https://www.clawagora.com/en/pricing))

## Email & Communication

Skills for managing inboxes, drafting responses, and keeping communication flowing.

- **[Google Workspace](https://github.com/NousResearch/hermes-agent/blob/main/skills/productivity/google-workspace/SKILL.md)** - Manage Gmail, Google Calendar, Drive, Docs, and Sheets through a single OAuth-authenticated skill. Lets your agent read and draft emails, schedule meetings, and organize documents with built-in safety rules that require your approval before sending anything. `hermes`
- **[Slack](https://github.com/openclaw/openclaw/blob/main/skills/slack/SKILL.md)** - Send, read, edit, and pin messages in Slack channels and DMs, add emoji reactions, and look up team member profiles. A built-in skill that turns your agent into a full Slack participant for team communication. `openclaw`
- **[Microsoft Workspace](https://github.com/Andrew-Girgis/microsoft-workspace-skill)** - Access Outlook email, calendar, and contacts via Microsoft Graph API for Hotmail, Outlook.com, and Microsoft 365 accounts. Supports reading, sending, and searching email plus scheduling meetings with Teams links. `hermes`
- **[Coordinate Meeting](https://clawskills.sh/skills/mkelk-coordinate-meeting)** - Automate group scheduling by creating availability polls, collecting votes from both humans and AI agents, and identifying the best meeting time. Works like a smart Doodle alternative powered by your agent. `openclaw`
- **[Rocket.Chat](https://clawskills.sh/skills/zenjabba-rocketchat)** - Integrate with your self-hosted Rocket.Chat server to manage channels, send and read messages, look up users, and configure integrations via REST API. Ideal for businesses that run their own team messaging platform. `openclaw`

## Customer Support

Skills for handling tickets, answering FAQs, and keeping customers happy.

- **[Customer Success Manager](https://clawskills.sh/skills/alirezarezvani-customer-success-manager)** - Monitors customer health, predicts churn risk, and identifies expansion opportunities using three local Python CLI tools with weighted scoring models -- no external API needed. `openclaw`
- **[Userorbit](https://github.com/userorbit/skill)** - Connects your agent to the Userorbit platform to automatically triage customer feedback, update product roadmaps, manage help center articles, and send announcements. `hermes`
- **[Customer Onboarding](https://clawskills.sh/skills/jk-0001-customer-onboarding-2)** - A comprehensive playbook that guides your agent to design and execute customer onboarding flows with activation metrics, email sequences, friction reduction, and retention measurement. `openclaw`
- **[EmotionWise](https://clawskills.sh/skills/timexicali-emotionwise)** - Analyzes customer messages for 28 distinct emotions and detects sarcasm, helping support teams understand the true tone of tickets, reviews, and feedback. `openclaw`
- **[Onboarding CRO](https://clawhub.ai/jchopard69/marketing-skills)** - Helps optimize post-signup onboarding by identifying your product's "aha moment," mapping user drop-off points, and producing a concrete activation improvement plan. `openclaw`

## Sales & CRM

Skills for prospecting, qualifying leads, and managing your pipeline.

- **[ActiveCampaign](https://clawskills.sh/skills/kesslerio-activecampaign)** - Connects your AI agent to ActiveCampaign CRM for managing contacts, deals, tags, and email automations -- sync demo leads, track your sales pipeline stages, and trigger follow-up sequences automatically. `openclaw`
- **[Cold Email](https://clawskills.sh/skills/bluecraft-ai-cold-email)** - Generates hyper-personalized cold email sequences using AI-powered prospect research via MachFive, turning lead lists into high-converting outreach campaigns instead of generic templates. `openclaw`
- **[Business Development](https://clawskills.sh/skills/oyi77-business-development)** - Provides frameworks and templates for the entire business development lifecycle including partner qualification scoring, outreach sequencing, competitor analysis, and proposal generation. `openclaw`
- **[Cold Outreach Sequence](https://github.com/BrianRWagner/ai-marketing-claude-code-skills/tree/main/cold-outreach-sequence)** - Builds personalized multi-touch outreach sequences for LinkedIn and email with tiered personalization based on prospect research, covering connection requests through break-up messages with pipeline tracking. `openclaw`
- **[Cold Outreach](https://clawskills.sh/skills/staybased-cold-outreach)** - Generates high-converting cold outreach copy for email, SMS, and LinkedIn DM using proven sales frameworks from Hormozi's methodology and analysis of over 100,000 campaigns. `openclaw`

## Content & Marketing

Skills for creating, scheduling, and analyzing content.

- **[Content Recycler](https://clawskills.sh/skills/michael-laffin-content-recycler)** - Transforms a single blog post or article into platform-optimized content for Twitter/X, LinkedIn, Instagram, TikTok, Facebook, and email, saving hours of manual repurposing work. `openclaw`
- **[Reef Copywriting](https://clawskills.sh/skills/staybased-reef-copywriting)** - Generates landing pages, product descriptions, ads, and sales copy using six proven direct-response frameworks (PAS, AIDA, FAB, BAB, 4Ps, Star-Story-Solution) with no external dependencies. `openclaw`
- **[BlogBurst](https://clawskills.sh/skills/shensi8312-blogburst)** - Turns any article into 10+ ready-to-publish social media posts across X, Bluesky, Telegram, and Discord in seconds, managing the full content-to-social pipeline. `openclaw`
- **[Meta Tags Optimizer](https://clawskills.sh/skills/aaron-he-zhu-meta-tags-optimizer)** - Generates optimized title tags, meta descriptions, Open Graph tags, and Twitter cards with CTR-focused A/B test variations to improve search visibility and social sharing. `openclaw`
- **[AEO Content Free](https://clawskills.sh/skills/psyduckler-aeo-content-free)** - Creates content optimized to get cited by AI assistants like ChatGPT, Gemini, and Perplexity, researching competitors and coverage gaps to boost your brand's AI search visibility. `openclaw`

## Operations & Admin

Skills for keeping the business running smoothly day-to-day.

- **[Google Workspace](https://github.com/NousResearch/hermes-agent/blob/main/skills/productivity/google-workspace/SKILL.md)** - Unified access to Gmail, Google Calendar, Drive, Docs, and Sheets through OAuth2, letting a business owner manage email, schedule meetings, organize files, and update spreadsheets all from one agent skill. `hermes`
- **[Asana](https://github.com/k0nkupa/openclaw-asana-skill)** - Connects your agent to Asana for listing workspaces, creating and completing tasks, searching projects, and posting comments, giving business owners hands-free project management. `openclaw`
- **[Todoist Task Manager](https://github.com/openclaw/skills/blob/main/skills/2mawi2/todoist-task-manager/SKILL.md)** - Manages Todoist tasks through natural language, supporting filters, priorities, labels, and projects so a business owner can add, complete, and organize daily to-dos without leaving their chat. `openclaw`
- **[Microsoft Workspace](https://github.com/Andrew-Girgis/microsoft-workspace-skill)** - Integrates Microsoft 365 via Graph API for managing Outlook email, calendar events with Teams video links, free/busy scheduling, and contacts, ideal for businesses running on the Microsoft stack. `hermes`
- **[Teams Meeting Pipeline](https://github.com/NousResearch/hermes-agent/blob/main/skills/productivity/teams-meeting-pipeline/SKILL.md)** - Automatically summarizes Microsoft Teams meetings, extracts action items, and manages the meeting-notes pipeline so business owners never lose track of decisions and follow-ups. `hermes`

## Finance & Accounting

Skills for managing money, invoices, and financial reporting.

- **[ERPClaw](https://playbooks.com/skills/openclaw/skills/erpclaw)** - AI-native ERP system offering full double-entry accounting, invoicing, inventory, purchasing, tax compliance, HR, and payroll in a single local-first install with 365+ actions and an immutable audit trail. `openclaw`
- **[AccountsOS](https://playbooks.com/skills/openclaw/skills/accountsos)** - AI-native accounting for UK micro-businesses, handling transaction tracking, VAT management, filing deadline alerts, invoice management, and document storage with automated categorization. `openclaw`
- **[Expense Report](https://playbooks.com/skills/openclaw/skills/expense-report)** - Organizes and categorizes business expenses into clear, IRS-aligned reimbursement and tax-ready reports with categorized summaries, line items, and missing-documentation checklists. `openclaw`
- **[Financial Overview](https://playbooks.com/skills/openclaw/skills/financial-overview)** - Provides a consolidated financial dashboard combining current balance, recent cash flow, outstanding invoices, and upcoming tax obligations with actionable recommendations. `openclaw`
- **[Accounting](https://playbooks.com/skills/openclaw/skills/accounting)** - Comprehensive accounting reference that adapts from basic bookkeeping to professional practice, covering journal entries, bank reconciliation, QuickBooks/Xero workflows, and revenue recognition standards. `openclaw`

## HR & Recruiting

Skills for hiring, onboarding, and managing your team.

- **[HR Recruiting & Talent Acquisition](https://github.com/tuanductran/hr-skills)** - End-to-end recruiting support that helps business owners write job descriptions, create interview questions, screen resumes, draft offer letters, and build employer branding -- covering the full hiring lifecycle from sourcing to close. `openclaw`
- **[OpenJobs People Search](https://github.com/OpenJobsAI/openjobs-openclaw-skills)** - Searches and retrieves professional candidate profiles for recruiting and talent sourcing, with structured filtering by skills, experience, and location, plus side-by-side candidate comparison and talent pool analytics. `openclaw`
- **[Interview Coach](https://github.com/noamseg/interview-coach-skill)** - A high-rigor interview coaching system with 23 commands covering structured prep, transcript analysis, practice drills, storybank management, and performance tracking across PM, Engineering, Design, and other roles. `openclaw`
- **[HR Onboarding & Offboarding](https://github.com/tuanductran/hr-skills)** - Designs complete employee onboarding programs with pre-boarding checklists, orientation schedules, buddy systems, 30/60/90-day milestone plans, and exit interview processes to reduce early turnover and accelerate new hire productivity. `openclaw`
- **[HR Compliance & Workplace Policies](https://github.com/tuanductran/hr-skills)** - Guides business owners through employment law compliance (EEO, OSHA, FMLA, ADA), employee handbook creation, harassment prevention policies, workplace investigations, and HR audit preparation to reduce legal risk. `openclaw`

## Legal & Compliance

Skills for reducing legal overhead and staying compliant.

- **[Contract Review](https://github.com/lawvable/awesome-legal-skills/tree/main/skills/contract-review-anthropic)** - Reviews commercial contracts against your organization's negotiation playbook, flagging risky clauses by severity (green/yellow/red) and generating redline suggestions for negotiation. `openclaw`
- **[Privacy Compliance](https://github.com/lawvable/awesome-legal-skills/tree/main/skills/compliance-anthropic)** - Navigates privacy regulations including GDPR, CCPA, and LGPD, helping you review data processing agreements, handle data subject requests, and assess cross-border data transfer requirements. `openclaw`
- **[NDA Review](https://github.com/lawvable/awesome-legal-skills/tree/main/skills/nda-review-jamie-tso)** - Evaluates one-way commercial NDAs with clause-by-clause analysis, identifying unfavorable terms and providing a structured negotiation framework from either the disclosing or receiving party's perspective. `openclaw`
- **[GDPR Privacy Notice Generator](https://github.com/lawvable/awesome-legal-skills/tree/main/skills/gdpr-privacy-notice-eu-oliver-schmidt-prietz)** - Drafts GDPR-compliant privacy notices as .docx documents for any EU/EEA jurisdiction, with built-in compliance checklists for country-specific requirements across Germany, France, Austria, Italy, Spain, and more. `openclaw`
- **[Vendor Due Diligence](https://github.com/lawvable/awesome-legal-skills/tree/main/skills/vendor-due-diligence-patrick-munro)** - Assesses IT vendors and service providers across financial, operational, compliance, and security risk dimensions, with regulatory compliance checklists covering GDPR, DORA, NIS2, and SOC 2. `openclaw`

## E-Commerce

Skills for online stores and product businesses.

- **[Shopify](https://github.com/NousResearch/hermes-agent/blob/main/optional-skills/productivity/shopify/SKILL.md)** - Official Shopify-built skill that lets your agent manage products, orders, inventory, customers, and fulfillments across your Shopify store using the modern GraphQL Admin API. Built by the Shopify team with comprehensive documentation covering every core store operation. `hermes`
- **[Clawpify](https://clawskills.sh/skills/alhwyn-clawpify)** - Query and manage your Shopify store via the GraphQL Admin API, covering products, orders, customers, inventory levels, discount codes, and bulk exports. Requires explicit user confirmation before any destructive action like refunds or cancellations. `openclaw`
- **[Atoship](https://clawskills.sh/skills/atoship-dev-atoship)** - Compare live shipping rates across USPS, FedEx, and UPS, purchase discounted labels, track packages, and generate return labels -- all without visiting individual carrier websites. Requires explicit confirmation before any purchase. `openclaw`
- **[Payment](https://playbooks.com/skills/openclaw/skills/payment)** - Streamlines payment processing and invoice management across multiple gateways including Stripe, PayPal, Square, and crypto providers, with transaction reconciliation, refund handling, and audit logging built in. `openclaw`
- **[Whop CLI](https://clawskills.sh/skills/g9pedro-whop-cli)** - Manage your Whop digital products store end-to-end: create products and pricing plans, generate checkout links, track payments, handle memberships, and set up promo codes. `openclaw`

## Data & Analytics

Skills for making sense of your business data.

- **[Skywork Excel](https://github.com/SkyworkAI/Skywork-Skills)** - AI-powered spreadsheet automation that creates Excel files with data, formulas, charts, and pivot tables, analyzes existing files, and generates professional reports -- ideal for budgets, financial modeling, and business dashboards. `openclaw`
- **[CSV Pipeline](https://clawskills.sh/skills/gitgoodordietrying-csv-pipeline)** - Processes, transforms, and analyzes CSV, TSV, and JSON data using Python 3 with zero external dependencies -- supports filtering, joining, aggregating, deduplicating, and generating Markdown summary reports from your business data. `openclaw`
- **[DuckDB CLI AI Skills](https://clawskills.sh/skills/camelsprout-duckdb-cli-ai-skills)** - Lets you query CSV, Parquet, and JSON files with SQL directly from the command line, without setting up a database server -- perfect for ad-hoc business data analysis and format conversion. `openclaw`
- **[Check Analytics](https://clawskills.sh/skills/jeftekhari-check-analytics)** - Audits your existing Google Analytics implementation by scanning for tracking identifiers, detecting configuration issues, and generating a prioritized report of critical fixes, warnings, and suggestions. `openclaw`
- **[Chart Image](https://clawskills.sh/skills/dannyshmueli-chart-image)** - Generates publication-quality PNG and SVG charts from data, supporting line, bar, pie, heatmap, candlestick, and multi-series chart types -- useful for embedding visuals in business reports and presentations. `openclaw`

## Integrations

Common platforms these skills connect to.

| Category | Platforms |
|----------|-----------|
| Email | Gmail, Outlook, Yahoo Mail |
| Calendar | Google Calendar, Outlook Calendar, Calendly |
| Messaging | Slack, Telegram, WhatsApp, Discord, Rocket.Chat |
| Documents | Google Docs, Notion, Dropbox, OneDrive |
| CRM | ActiveCampaign, HubSpot, Salesforce, Pipedrive |
| Project Management | Asana, Todoist, Trello, Linear |
| Accounting | QuickBooks, Xero, FreshBooks |
| E-Commerce | Shopify, Whop, Stripe, PayPal |
| Social Media | LinkedIn, Twitter/X, Instagram, Bluesky |
| Analytics | Google Analytics, DuckDB, Excel |

OpenClaw supports 3000+ app integrations. See the [ClawAgora Features page](https://www.clawagora.com/en/features) for a full list, or the [OpenClaw documentation](https://docs.openclaw.ai/) for self-hosted setup.

## Learning Resources

- [OpenClaw Getting Started Guide](https://documentation.openclaw.ai/start/getting-started) - Install OpenClaw and chat with your AI assistant in under 5 minutes.
- [OpenClaw Agent Workspace](https://documentation.openclaw.ai/concepts/agent-workspace) - Understanding how workspaces, skills, and configurations fit together.
- [Hermes Agent Quickstart](https://hermes-agent.nousresearch.com/docs/getting-started/quickstart) - Get Hermes Agent running with the one-line installer.
- [Hermes Skills Hub](https://hermes-agent.nousresearch.com/docs/skills/) - Browse and install community-contributed skills for Hermes.
- [How to Run OpenClaw Without Self-Hosting](https://www.clawagora.com/en/blog/how-to-run-openclaw-without-self-hosting) - Every managed hosting option compared, including ClawAgora.
- [5 Workspace Patterns for Power Users](https://www.clawagora.com/en/blog/5-workspace-patterns-power-users) - Advanced patterns that separate beginners from power users.

## Community

- [OpenClaw GitHub](https://github.com/openclaw/openclaw) - Source code, issues, and community discussions for OpenClaw.
- [Hermes Agent GitHub](https://github.com/NousResearch/hermes-agent) - Source code and releases for Hermes Agent.
- [ClawAgora Marketplace](https://www.clawagora.com/en/marketplace) - Browse and download community-built agent workspace templates.
- [ClawAgora Blog](https://www.clawagora.com/en/blog) - Tutorials, comparisons, and workspace tips.
- [GitHub Discussions](https://github.com/clawagora/awesome-business-agent-skills/discussions) - Ask questions, request skills, and share your setups.

## Contributing

Contributions are welcome! Please read the [contribution guidelines](CONTRIBUTING.md) before submitting a pull request.

If you find a skill that's helped your business, [open a PR](https://github.com/clawagora/awesome-business-agent-skills/pulls) to share it with the community.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

This list is released under [CC0](LICENSE). You can copy, modify, and distribute it, even for commercial purposes, without asking permission.
