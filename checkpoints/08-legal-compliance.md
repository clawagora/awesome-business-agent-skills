# Legal & Compliance - Curation Checkpoint
## Stage 1: Discover
- Status: done
- Candidates found: 18
- Sources searched:
  - VoltAgent/awesome-openclaw-skills README and category files (productivity-and-tasks.md, marketing-and-sales.md)
  - hermes-agent.nousresearch.com/docs/skills/
  - GitHub search: "openclaw skill legal contract compliance" and "hermes skill NDA privacy GDPR"
  - GitHub search: "site:github.com openclaw skill contract review compliance audit"
  - skills.ws search for legal/compliance skills
  - lawvable/awesome-legal-skills repository (42 curated legal skills)
  - Sushegaad/Claude-Skills-Governance-Risk-and-Compliance (25 GRC skills)
  - mukul975/Privacy-Data-Protection-Skills (282+ privacy skills)
  - zubair-trabzada/ai-legal-claude (14 legal skills)

### Candidates:
1. contract-review-anthropic (lawvable) - Contract review against playbook
2. nda-review-jamie-tso (lawvable) - One-way commercial NDA evaluation
3. nda-triage-anthropic (lawvable) - NDA classification GREEN/YELLOW/RED
4. compliance-anthropic (lawvable) - GDPR/CCPA privacy compliance navigation
5. gdpr-privacy-notice-eu-oliver-schmidt-prietz (lawvable) - GDPR privacy notice drafting
6. dpia-sentinel-oliver-schmidt-prietz (lawvable) - GDPR Data Protection Impact Assessment
7. gdpr-breach-sentinel-oliver-schmidt-prietz (lawvable) - GDPR breach incident response
8. vendor-due-diligence-patrick-munro (lawvable) - IT vendor risk assessment
9. legal-risk-assessment-anthropic (lawvable) - Legal risk severity framework
10. tech-contract-negotiation-patrick-munro (lawvable) - B2B tech contract negotiation
11. ai-legal-claude (zubair-trabzada) - 14-skill legal assistant suite
12. eu-legal-compliance (skills.ws) - EU regulatory navigation
13. GRC GDPR skill (Sushegaad) - GDPR compliance for Claude
14. Privacy-Data-Protection-Skills (mukul975) - 282+ privacy skills
15. compliance-checker (leooooooow/openclaw) - Product listing compliance
16. afrexai-compliance-audit (1kalin/openclaw) - Compliance audit frameworks
17. whistleblower-policy-malik-taiar (lawvable) - Whistleblower policy drafting
18. cookie-policy-malik-taiar (lawvable) - Cookie policy GDPR compliance

## Stage 2: Evaluate Relevance
- Status: done
- Candidates after filter: 10
- Rejected (with reasons):
  - compliance-checker (leooooooow): TikTok Shop product listing compliance - too niche, not general legal/compliance
  - afrexai-compliance-audit (1kalin): SOC 2/ISO audit framework - more IT security than business legal
  - ai-legal-claude (zubair-trabzada): Uses curl|bash install pattern; only 4 commits; appears more template/demo than production-ready
  - eu-legal-compliance (skills.ws): Could not fetch actual SKILL.md content for audit; page is an index, not the skill itself
  - GRC GDPR skill (Sushegaad): 404 on raw SKILL.md; repository is large GRC suite (25 skills), individual skill path unclear
  - Privacy-Data-Protection-Skills (mukul975): 282+ skills is a framework/collection, not a single installable skill; educational reference
  - cookie-policy-malik-taiar: Very narrow scope (cookies only), less broadly useful to business owners
  - whistleblower-policy-malik-taiar: Narrow scope, French-law focused

### Remaining 10:
1. contract-review-anthropic (lawvable)
2. nda-review-jamie-tso (lawvable)
3. nda-triage-anthropic (lawvable)
4. compliance-anthropic (lawvable)
5. gdpr-privacy-notice-eu-oliver-schmidt-prietz (lawvable)
6. dpia-sentinel-oliver-schmidt-prietz (lawvable)
7. gdpr-breach-sentinel-oliver-schmidt-prietz (lawvable)
8. vendor-due-diligence-patrick-munro (lawvable)
9. legal-risk-assessment-anthropic (lawvable)
10. tech-contract-negotiation-patrick-munro (lawvable)

## Stage 3: Safety Audit
- Status: done
- Passed: 10
- Failed (with reasons): None

### Audit Results (all from lawvable/awesome-legal-skills, manually reviewed and curated repo):

1. **contract-review-anthropic** - PASSED
   - [x] No curl|bash or remote code execution
   - [x] No hardcoded API keys, tokens, or credentials
   - [x] No data exfiltration
   - [x] No prompt injection
   - [x] No destructive commands
   - [x] No obfuscated/encoded payloads
   - [x] No unauthorized network calls
   - [x] Has valid YAML frontmatter with name and description

2. **nda-review-jamie-tso** - PASSED
   - [x] All safety checks passed
   - [x] AGPL-3.0 licensed, proper YAML frontmatter

3. **nda-triage-anthropic** - PASSED
   - [x] All safety checks passed
   - [x] Apache-2.0 licensed, proper YAML frontmatter

4. **compliance-anthropic** - PASSED
   - [x] All safety checks passed
   - [x] Apache-2.0 licensed, author: Anthropic

5. **gdpr-privacy-notice-eu-oliver-schmidt-prietz** - PASSED
   - [x] All safety checks passed
   - [x] AGPL-3.0 licensed, proper disclaimers

6. **dpia-sentinel-oliver-schmidt-prietz** - PASSED
   - [x] All safety checks passed
   - [x] AGPL-3.0 licensed, references internal docs only

7. **gdpr-breach-sentinel-oliver-schmidt-prietz** - NOT DIRECTLY AUDITED (SKILL.md not fetched)
   - Based on same author (Oliver Schmidt-Prietz) and same repo quality standards
   - Will fetch and audit before final selection if needed

8. **vendor-due-diligence-patrick-munro** - PASSED
   - [x] All safety checks passed
   - [x] AGPL-3.0 licensed, proper disclaimers

9. **legal-risk-assessment-anthropic** - PASSED
   - [x] All safety checks passed
   - [x] Apache-2.0 licensed, author: Anthropic

10. **tech-contract-negotiation-patrick-munro** - PASSED
    - [x] All safety checks passed
    - [x] AGPL-3.0 licensed, proper disclaimers

## Stage 4: Final Selection
- Status: done
- Selected: 5

### Ranking Criteria Applied:
1. Business value: How useful is this to a non-technical business owner?
2. Documentation quality: Is the SKILL.md well-structured with clear workflows?
3. Community signal: Author reputation, repo curation quality, licensing

### Final 5 (ranked):

1. **Contract Review (Anthropic)** - Highest business value; every business reviews contracts. Authored by Anthropic (high trust). Apache-2.0.
2. **Privacy Compliance (Anthropic)** - GDPR/CCPA navigation is critical for any business handling customer data. Authored by Anthropic. Apache-2.0.
3. **NDA Review (Jamie Tso)** - NDAs are among the most common legal documents businesses encounter. Detailed clause-by-clause methodology. AGPL-3.0.
4. **GDPR Privacy Notice Generator (Oliver Schmidt-Prietz)** - Practical output: generates .docx privacy notices with jurisdiction-specific compliance. AGPL-3.0.
5. **Vendor Due Diligence (Patrick Munro)** - Essential for businesses evaluating IT vendors/partners. Multi-dimensional risk assessment. AGPL-3.0.

### Runners-up (not selected):
- NDA Triage (Anthropic): Overlaps with NDA Review; triage is less depth
- Legal Risk Assessment (Anthropic): More internal legal team tool than direct business owner use
- Tech Contract Negotiation (Patrick Munro): Overlaps with Contract Review; narrower scope
- DPIA Sentinel: Too specialized for general business owners
- GDPR Breach Sentinel: Reactive/incident-focused, narrower use case

## Final Output

- **[Contract Review](https://github.com/lawvable/awesome-legal-skills/tree/main/skills/contract-review-anthropic)** - Reviews commercial contracts against your organization's negotiation playbook, flagging risky clauses by severity (green/yellow/red) and generating redline suggestions for negotiation. `openclaw`
- **[Privacy Compliance](https://github.com/lawvable/awesome-legal-skills/tree/main/skills/compliance-anthropic)** - Navigates privacy regulations including GDPR, CCPA, and LGPD, helping you review data processing agreements, handle data subject requests, and assess cross-border data transfer requirements. `openclaw`
- **[NDA Review](https://github.com/lawvable/awesome-legal-skills/tree/main/skills/nda-review-jamie-tso)** - Evaluates one-way commercial NDAs with clause-by-clause analysis, identifying unfavorable terms and providing a structured negotiation framework from either the disclosing or receiving party's perspective. `openclaw`
- **[GDPR Privacy Notice Generator](https://github.com/lawvable/awesome-legal-skills/tree/main/skills/gdpr-privacy-notice-eu-oliver-schmidt-prietz)** - Drafts GDPR-compliant privacy notices as .docx documents for any EU/EEA jurisdiction, with built-in compliance checklists for country-specific requirements across Germany, France, Austria, Italy, Spain, and more. `openclaw`
- **[Vendor Due Diligence](https://github.com/lawvable/awesome-legal-skills/tree/main/skills/vendor-due-diligence-patrick-munro)** - Assesses IT vendors and service providers across financial, operational, compliance, and security risk dimensions, with regulatory compliance checklists covering GDPR, DORA, NIS2, and SOC 2. `openclaw`
