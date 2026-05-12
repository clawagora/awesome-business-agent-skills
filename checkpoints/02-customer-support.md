# Customer Support - Curation Checkpoint
## Stage 1: Discover
- Status: done
- Candidates found: 20
- Sources searched: [clawskills.sh, clawhub.ai, VoltAgent/awesome-openclaw-skills, hermes-agent.nousresearch.com, 0xNyk/awesome-hermes-agent, shopclawmart.com, userorbit.com, composio.dev, LeoYeAI/openclaw-master-skills, WebSearch]

### Candidates:
1. customer-onboarding-2 (jk-0001) [openclaw]
2. emotionwise (timexicali) [openclaw]
3. agentmail (adboio) [openclaw]
4. activecampaign (kesslerio) [openclaw]
5. Customer Reply Tone Fixer (Skippythemagnificent) [openclaw, Claw Mart]
6. Support Builder (Skippythemagnificent) [openclaw, Claw Mart]
7. Customer Support Playbook (Melisia Archimedes) [openclaw, Claw Mart]
8. Haven - AI Customer Support Rep (Nexus Vael) [openclaw, Claw Mart]
9. Customer Support Automation Plugin (Bravo1058AI) [openclaw, Claw Mart]
10. Support Knowledge Base Plugin (Bravo1058AI) [openclaw, Claw Mart]
11. Customer Feedback Analyzer (Bravo1058AI) [openclaw, Claw Mart]
12. Customer Feedback System (Kinetic Goods) [openclaw, Claw Mart]
13. Customer Success Playbook (Kinetic Goods) [openclaw, Claw Mart]
14. WhatsApp Business FAQ Generator (Adam Labs) [openclaw, Claw Mart]
15. Bug Report Rewriter (Rubixhacker) [openclaw, Claw Mart]
16. synapse-msp-it-operations-starter (Jonathan Colwell) [openclaw, Claw Mart]
17. userorbit (userorbit) [hermes]
18. Client Onboarding Emails (Kinetic Goods) [openclaw, Claw Mart]
19. customer-success-manager (alirezarezvani) [openclaw, curated]
20. onboarding-cro (jchopard69) [openclaw, curated]

## Stage 2: Evaluate Relevance
- Status: done
- Candidates after filter: 5
- Rejected (with reasons):
  - #3 agentmail: General email tool, not customer-support-specific; flagged Suspicious by OpenClaw security
  - #4 activecampaign: CRM/sales tool, not primarily customer support
  - #5 Customer Reply Tone Fixer: Source not auditable (paid Claw Mart, no public SKILL.md)
  - #6 Support Builder: Source not auditable (paid Claw Mart)
  - #7 Customer Support Playbook: Source not auditable (paid Claw Mart)
  - #8 Haven: Source not auditable (paid Claw Mart)
  - #9 Customer Support Automation Plugin: Source not auditable (paid Claw Mart)
  - #10 Support Knowledge Base Plugin: Source not auditable (paid Claw Mart)
  - #11 Customer Feedback Analyzer: Source not auditable (paid Claw Mart)
  - #12 Customer Feedback System: Too generic/thin, source not auditable
  - #13 Customer Success Playbook (Kinetic Goods): Too generic, source not auditable
  - #14 WhatsApp Business FAQ Generator: Source not auditable (paid Claw Mart)
  - #15 Bug Report Rewriter: Developer-facing, not business-owner facing
  - #16 synapse-msp-it-operations-starter: IT ops focused, not general customer support
  - #18 Client Onboarding Emails: Too narrow, source not auditable

### Remaining candidates (5 with auditable source):
1. **customer-onboarding-2** (jk-0001) - Full SKILL.md verified from clawhub.ai
2. **emotionwise** (timexicali) - Full SKILL.md verified from clawhub.ai
3. **userorbit** (userorbit) - Full SKILL.md + api-helper.sh verified from GitHub (userorbit/skill)
4. **customer-success-manager** (alirezarezvani) - Full SKILL.md + 3 Python scripts from GitHub (LeoYeAI/openclaw-master-skills)
5. **onboarding-cro** (jchopard69) - Full SKILL.md verified from GitHub (LeoYeAI/openclaw-master-skills)

## Stage 3: Safety Audit
- Status: done
- Passed: 5
- Failed (with reasons): []

### Audit Results:

#### 1. customer-onboarding-2 (jk-0001)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys, tokens, or credentials
- [x] No data exfiltration (sending data to unknown endpoints)
- [x] No prompt injection (hidden instructions to override agent behavior)
- [x] No destructive commands (rm -rf, DROP TABLE, etc.)
- [x] No obfuscated/encoded payloads (base64 blobs, eval(), exec())
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- Notes: Pure markdown playbook. No scripts, no API calls. Contains only instructional content for building onboarding flows. VirusTotal: Benign. OpenClaw: Benign.
- Verdict: PASS

#### 2. emotionwise (timexicali)
- [x] No curl|bash or remote code execution - uses documented API endpoint (api.emotionwise.ai) via standard HTTP POST
- [x] No hardcoded API keys - reads from EMOTIONWISE_API_KEY env var
- [x] No data exfiltration - sends only user-provided text to the declared API
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] Network calls are authorized - single documented API endpoint for emotion analysis
- [x] Has valid YAML frontmatter with name and description
- Notes: Simple API wrapper skill. Sends text to emotionwise.ai and returns emotion labels + sarcasm scores. Requires user-provisioned API key. VirusTotal: Benign. OpenClaw: Benign.
- Verdict: PASS

#### 3. userorbit (userorbit)
- [x] No curl|bash or remote code execution - curl calls are to documented Userorbit API only
- [x] No hardcoded API keys - reads from USERORBIT_API_KEY and USERORBIT_TEAM_ID env vars
- [x] No data exfiltration - all calls go to api.userorbit.com (the product's own API)
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] Network calls are authorized - single base URL https://api.userorbit.com/api/v1
- [x] Has valid YAML frontmatter with name and description
- Notes: api-helper.sh is a simple 6-line curl wrapper. SKILL.md is a comprehensive API reference covering feedback, boards, announcements, articles, roadmaps, tags, and subscribers. All endpoints are POST to the documented Userorbit REST API. Source verified at github.com/userorbit/skill.
- Verdict: PASS

#### 4. customer-success-manager (alirezarezvani)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys, tokens, or credentials
- [x] No data exfiltration - Python scripts are local-only (file input -> stdout output)
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads - all 3 Python scripts use standard library only (json, argparse, sys, datetime)
- [x] No unauthorized network calls - zero network imports (no requests, urllib, http, socket)
- [x] Has valid YAML frontmatter with name, description, version, author, license (MIT)
- Notes: Three local CLI tools (health_score_calculator.py, churn_risk_analyzer.py, expansion_opportunity_scorer.py). Read JSON, compute weighted scores, output text/JSON. No external dependencies. 1,053 downloads. VirusTotal: Benign. Source verified at github.com/LeoYeAI/openclaw-master-skills.
- Verdict: PASS

#### 5. onboarding-cro (jchopard69)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys, tokens, or credentials
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- Notes: Pure markdown playbook (220 lines). Advisory content only -- guides agent to assess and optimize post-signup onboarding flows using the "aha moment" framework. No scripts or API calls. Part of the marketing-skills bundle (16,205 downloads). Source verified at github.com/LeoYeAI/openclaw-master-skills.
- Verdict: PASS

## Stage 4: Final Selection
- Status: done
- Selected: 5

### Ranking:
1. **customer-success-manager** - Highest business value (3 production-grade Python tools for health scoring, churn prediction, expansion identification). Best documentation quality. MIT license. Version 2.1.1 on ClawHub. 1,053 downloads.
2. **userorbit** - High business value (full customer feedback platform integration with help center, roadmap, announcements). Production Hermes skill with open GitHub source. Comprehensive API coverage.
3. **customer-onboarding-2** - High business value (complete onboarding system with activation metrics, email sequences, friction reduction, retention measurement). Well-documented playbook on ClawHub.
4. **emotionwise** - Unique capability (28-label emotion taxonomy + sarcasm detection). Practical for analyzing support ticket tone and customer feedback sentiment. 230 downloads on ClawHub.
5. **onboarding-cro** - Solid practical framework for optimizing post-signup activation with "aha moment" identification and drop-off analysis. Part of popular marketing-skills bundle (16k+ downloads).

## Final Output

- **[Customer Success Manager](https://clawskills.sh/skills/alirezarezvani-customer-success-manager)** - Monitors customer health, predicts churn risk, and identifies expansion opportunities using three local Python CLI tools with weighted scoring models -- no external API needed. `openclaw`
- **[Userorbit](https://github.com/userorbit/skill)** - Connects your agent to the Userorbit platform to automatically triage customer feedback, update product roadmaps, manage help center articles, and send announcements. `hermes`
- **[Customer Onboarding](https://clawskills.sh/skills/jk-0001-customer-onboarding-2)** - A comprehensive playbook that guides your agent to design and execute customer onboarding flows with activation metrics, email sequences, friction reduction, and retention measurement. `openclaw`
- **[EmotionWise](https://clawskills.sh/skills/timexicali-emotionwise)** - Analyzes customer messages for 28 distinct emotions and detects sarcasm, helping support teams understand the true tone of tickets, reviews, and feedback. `openclaw`
- **[Onboarding CRO](https://clawhub.ai/jchopard69/marketing-skills)** - Helps optimize post-signup onboarding by identifying your product's "aha moment," mapping user drop-off points, and producing a concrete activation improvement plan. `openclaw`
