# Skill Curation Swarm Report

**Date:** 2026-05-11
**Agents:** 10 (one per category)
**Pipeline:** Discover > Evaluate Relevance > Safety Audit > Final Selection

## Aggregate Statistics

| Metric | Count |
|--------|-------|
| Total candidates discovered | ~184 |
| After relevance filter | ~89 |
| Passed safety audit | ~78 |
| Failed safety audit | 11 |
| **Final selected** | **50** |

## Per-Category Results

| # | Category | Discovered | Filtered | Safety Pass | Safety Fail | Selected | Runtimes |
|---|----------|-----------|----------|-------------|-------------|----------|----------|
| 1 | Email & Communication | 20 | 9 | 7 | 2 | 5 | 2 hermes, 3 openclaw |
| 2 | Customer Support | 20 | 5 | 5 | 0 | 5 | 1 hermes, 4 openclaw |
| 3 | Sales & CRM | 18 | 9 | 9 | 0 | 5 | 5 openclaw |
| 4 | Content & Marketing | 20 | 10 | 10 | 0 | 5 | 5 openclaw |
| 5 | Operations & Admin | 20 | 8 | 8 | 0 | 5 | 3 hermes, 2 openclaw |
| 6 | Finance & Accounting | 20+ | 10 | 7 | 3 | 5 | 5 openclaw |
| 7 | HR & Recruiting | 16 | 10 | 8 | 2 | 5 | 5 openclaw |
| 8 | Legal & Compliance | 18 | 10 | 10 | 0 | 5 | 5 openclaw |
| 9 | E-Commerce | 16 | 9 | 8 | 1 | 5 | 1 hermes, 4 openclaw |
| 10 | Data & Analytics | 16 | 9 | 6 | 3 | 5 | 5 openclaw |

## Safety Audit Failures (11 total)

| Skill | Category | Failure Reason |
|-------|----------|----------------|
| gmail-secretary | Email | OpenClaw: dangerous_exec flag (HIGH), persistent across 22+ versions |
| microsoft365 (openclaw) | Email | VirusTotal: Suspicious flag, limited adoption (622 downloads) |
| Bookkeeper | Finance | Suspicious by BOTH VirusTotal and OpenClaw; requires MATON_API_KEY gateway |
| EzBookkeeping | Finance | VirusTotal: Suspicious; non-standard deployment scripts |
| Actual Budget | Finance | OpenClaw: Suspicious; history of NODE_TLS_REJECT_UNAUTHORIZED=0 |
| recruiter-assistant | HR | Suspicious by BOTH VirusTotal and OpenClaw; SKILL.md 404 |
| employee-onboarding (afrexai) | HR | SKILL.md 404; hosting platform leaked Supabase credentials |
| amazon-product-api | E-Commerce | Suspicious by BOTH; routes data through BrowserAct (exfiltration risk) |
| data-analyst | Data | OpenClaw: Suspicious (HIGH); source code 404/unauditable |
| financial-analyst | Data | Source code 404; no security scan data available |
| biz-reporter | Data | Suspicious by BOTH VirusTotal and OpenClaw |

## Runtime Distribution

| Runtime | Skills Selected |
|---------|----------------|
| OpenClaw only | 39 |
| Hermes only | 8 |
| Both | 3 |

## Sources Used Across All Agents

- VoltAgent/awesome-openclaw-skills (5,211 categorized skills)
- Hermes Agent Skills Hub (672 skills across 4 registries)
- clawskills.sh (OpenClaw skill pages)
- clawhub.ai (OpenClaw community hub)
- playbooks.com (skill marketplace)
- GitHub repos: NousResearch/hermes-agent, lawvable/awesome-legal-skills, tuanductran/hr-skills, OpenJobsAI, SkyworkAI, BrianRWagner, kesslerio, Bluecraft-AI, and others
- Security: VirusTotal + OpenClaw moderation system

## Key Observations

1. **Legal category strongest**: All 10 candidates passed safety (lawvable/awesome-legal-skills is well-curated). Anthropic-authored skills scored highest trust.
2. **Finance/Data highest rejection rate**: 3 failures each -- financial skills attract more suspicious actors or have complex dependencies that trigger security flags.
3. **Hermes skills underrepresented**: Most business-focused skills are OpenClaw-native. Hermes excels in productivity/operations (Google Workspace, Microsoft, Shopify, Teams) but fewer niche business skills.
4. **Paid marketplace skills (Claw Mart) excluded**: ~15 candidates from shopclawmart.com were rejected because source code was not publicly auditable.
5. **Quality signal matters**: Skills with 0 downloads/installs were consistently dropped in Stage 4 regardless of safety status.
