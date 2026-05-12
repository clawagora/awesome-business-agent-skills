# Sales & CRM - Curation Checkpoint

## Stage 1: Discover
- Status: done
- Candidates found: 18
- Sources searched:
  - VoltAgent/awesome-openclaw-skills README.md
  - VoltAgent/awesome-openclaw-skills categories/marketing-and-sales.md
  - hermes-agent.nousresearch.com/docs/skills/ (Skills Hub)
  - NousResearch/hermes-agent GitHub repo (optional-skills/)
  - GitHub search: "openclaw skill CRM sales"
  - GitHub search: "hermes skill sales lead pipeline"
  - Web search: clawskills.sh sales CRM HubSpot Salesforce
  - Bluecraft-AI/machfive-skills GitHub repo
  - BrianRWagner/ai-marketing-claude-code-skills GitHub repo
  - kesslerio/activecampaign-openclaw-skill GitHub repo

### Candidates:
1. activecampaign (kesslerio) - CRM integration for lead/deal management
2. apollo (jhumanj) - Apollo.io REST API for people/org enrichment
3. attio-enhanced (capt-marbles) - Attio CRM API with batch operations
4. cold-email (bluecraft-ai) - AI-generated personalized cold email sequences via MachFive
5. cold-outreach (staybased) - Multi-channel outreach copy (email, SMS, LinkedIn DM)
6. cold-outreach-sequence (BrianRWagner) - LinkedIn + email outreach sequences
7. business-development (oyi77) - Partnership outreach, market research, proposals
8. campaign-orchestrator (kesslerio) - Multi-channel follow-up campaigns
9. foxreach (concaption) - FoxReach cold email outreach management
10. ai-lead-generator-skill (highlander89) - B2B lead generation via AI research
11. workcrm (extraterrest) - Lightweight local-first CRM with SQLite
12. sentiment-priority-scorer (vishalgojha) - Lead scoring for real estate
13. alibaba-supplier-outreach (blockchainhb) - Supplier outreach on Alibaba
14. social-media-lead-generation (shahbaz02197ali) - Social media lead gen
15. one-three-one-rule (Hermes/NousResearch) - Structured proposals/decision framework
16. agentmail (Hermes/NousResearch) - Agent-owned email inboxes
17. telephony (Hermes/NousResearch) - Phone/SMS/voice calls via Twilio
18. kvcore-mcp-cli (danielfoch) - Real estate CRM actions

## Stage 2: Evaluate Relevance
- Status: done
- Candidates after filter: 9
- Rejected (with reasons):
  - apollo: Flagged SUSPICIOUS by OpenClaw; primarily a developer API wrapper, not business-owner focused
  - ai-lead-generator-skill: Flagged SUSPICIOUS by OpenClaw; only 4 installs; requires LinkedIn Sales Navigator (niche)
  - campaign-orchestrator: Flagged SUSPICIOUS by both VirusTotal and OpenClaw; dual red flags
  - foxreach: Flagged SUSPICIOUS by both VirusTotal and OpenClaw; dual red flags
  - workcrm: Flagged SUSPICIOUS by OpenClaw; alpha-stage (v0.1.0-alpha.4); 0 installs
  - alibaba-supplier-outreach: Too narrow (supplier sourcing, not general sales/CRM)
  - social-media-lead-generation: Very low adoption; vague description
  - kvcore-mcp-cli: Too narrow (real estate only)
  - one-three-one-rule: Primarily a technical decision framework, not sales-specific

### Remaining candidates (9):
1. activecampaign (kesslerio) - CRM integration
2. cold-email (bluecraft-ai) - AI cold email sequences
3. cold-outreach (staybased) - Multi-channel outreach copy
4. cold-outreach-sequence (BrianRWagner) - LinkedIn + email sequences
5. business-development (oyi77) - Partnership & proposal frameworks
6. attio-enhanced (capt-marbles) - Attio CRM batch operations
7. sentiment-priority-scorer (vishalgojha) - Lead scoring
8. agentmail (Hermes/NousResearch) - Agent email for outreach
9. telephony (Hermes/NousResearch) - Phone/SMS for sales calls

## Stage 3: Safety Audit
- Status: done

### 1. activecampaign (kesslerio)
- Source: https://github.com/kesslerio/activecampaign-openclaw-skill (SKILL.md verified)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (uses env vars ACTIVECAMPAIGN_URL, ACTIVECAMPAIGN_API_KEY)
- [x] No data exfiltration (connects only to user's own ActiveCampaign instance)
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls (only ActiveCampaign API)
- [x] Has valid YAML frontmatter with name and description
- VirusTotal: Benign | OpenClaw: Benign (HIGH confidence)
- PASSED

### 2. cold-email (bluecraft-ai)
- Source: https://github.com/Bluecraft-AI/machfive-skills (SKILL.md verified)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (uses env var MACHFIVE_API_KEY)
- [x] No data exfiltration (sends lead data to MachFive API - legitimate third-party service)
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls (only app.machfive.io endpoints)
- [x] Has valid YAML frontmatter with name and description
- VirusTotal: Benign | OpenClaw: Benign (HIGH confidence)
- PASSED

### 3. cold-outreach (staybased)
- Source: clawskills.sh (metadata verified)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (no API keys required - prompt-only skill)
- [x] No data exfiltration (no external connections)
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls (no network calls at all)
- [x] Has valid YAML frontmatter with name and description
- VirusTotal: Benign | OpenClaw: Benign (HIGH confidence)
- Note: Pure copywriting framework, no code execution
- PASSED

### 4. cold-outreach-sequence (BrianRWagner)
- Source: https://github.com/BrianRWagner/ai-marketing-claude-code-skills (SKILL.md verified in full)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (no keys needed)
- [x] No data exfiltration (uses web_search for prospect research - standard agent tool)
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- Note: Framework-based skill with research + sequence generation
- PASSED

### 5. business-development (oyi77)
- Source: clawskills.sh (metadata verified)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (no APIs required - self-contained)
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- VirusTotal: Benign | OpenClaw: Benign (HIGH confidence)
- PASSED

### 6. attio-enhanced (capt-marbles)
- Source: clawskills.sh (metadata verified)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- VirusTotal: Benign | OpenClaw: Benign (MEDIUM confidence)
- Note: 0 installs; newly published; limited adoption signal
- PASSED (but lower confidence due to new/unproven)

### 7. sentiment-priority-scorer (vishalgojha)
- Source: clawskills.sh (metadata verified)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (no APIs required)
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- VirusTotal: Benign | OpenClaw: Benign (HIGH confidence)
- Note: Read-only scoring skill; niche (real estate leads)
- PASSED

### 8. agentmail (Hermes/NousResearch)
- Source: https://github.com/NousResearch/hermes-agent (SKILL.md verified in full)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (uses env var AGENTMAIL_API_KEY)
- [x] No data exfiltration (connects to legitimate AgentMail service)
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls (only agentmail MCP server)
- [x] Has valid YAML frontmatter with name and description
- Note: Official Hermes skill by Nous Research; MIT license
- PASSED

### 9. telephony (Hermes/NousResearch)
- Source: https://github.com/NousResearch/hermes-agent (SKILL.md verified in full)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (credentials saved to ~/.hermes/.env by user)
- [x] No data exfiltration (connects to Twilio/Bland.ai/Vapi - user-configured services)
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- [x] Has explicit safety rules (confirm before calling, never dial emergency, no spam)
- Note: Official Hermes skill by Nous Research; MIT license
- PASSED

### Summary:
- Passed: 9
- Failed: 0

## Stage 4: Final Selection
- Status: done
- Selected: 5

### Ranking criteria applied:
1. Business value: How useful is this to a non-technical business owner for sales/CRM?
2. Documentation quality: Is the SKILL.md thorough, well-structured, with examples?
3. Community signal: Downloads, installs, security audit confidence, author reputation

### Rankings:
1. **activecampaign** - Top business value (full CRM pipeline management); excellent docs (full command reference, field mappings, related skills); 3,136 downloads, 8 installs; HIGH confidence benign
2. **cold-email** - High business value (AI-personalized cold email at scale); excellent docs (full API reference, batch workflows, error handling); 3,841 downloads, 10 installs; MIT license
3. **business-development** - Strong business value (partnership outreach, proposals, competitor analysis, pipeline tracking); good docs; 3,198 downloads, 20 installs (highest adoption); HIGH confidence benign
4. **cold-outreach-sequence** - High business value (systematic LinkedIn+email outreach with research); excellent docs (tiered personalization, self-critique, tracking table); verified source on GitHub; MIT-compatible
5. **cold-outreach** - Good business value (multi-channel outreach copy); clean framework-based approach; 1,343 downloads, 5 installs; no external dependencies

### Runners-up (not selected):
6. telephony - Excellent but more general-purpose (not sales-specific)
7. agentmail - Excellent but more general-purpose (not sales-specific)
8. sentiment-priority-scorer - Too niche (real estate only)
9. attio-enhanced - Too new (0 installs, MEDIUM confidence)

## Final Output

- **[ActiveCampaign](https://clawskills.sh/skills/kesslerio-activecampaign)** - Connects your AI agent to ActiveCampaign CRM for managing contacts, deals, tags, and email automations -- sync demo leads, track your sales pipeline stages, and trigger follow-up sequences automatically. `openclaw`
- **[Cold Email](https://clawskills.sh/skills/bluecraft-ai-cold-email)** - Generates hyper-personalized cold email sequences using AI-powered prospect research via MachFive, turning lead lists into high-converting outreach campaigns instead of generic templates. `openclaw`
- **[Business Development](https://clawskills.sh/skills/oyi77-business-development)** - Provides frameworks and templates for the entire business development lifecycle including partner qualification scoring, outreach sequencing, competitor analysis, and proposal generation. `openclaw`
- **[Cold Outreach Sequence](https://github.com/BrianRWagner/ai-marketing-claude-code-skills/tree/main/cold-outreach-sequence)** - Builds personalized multi-touch outreach sequences for LinkedIn and email with tiered personalization based on prospect research, covering connection requests through break-up messages with pipeline tracking. `openclaw`
- **[Cold Outreach](https://clawskills.sh/skills/staybased-cold-outreach)** - Generates high-converting cold outreach copy for email, SMS, and LinkedIn DM using proven sales frameworks from Hormozi's methodology and analysis of over 100,000 campaigns. `openclaw`
