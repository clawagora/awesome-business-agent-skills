# HR & Recruiting - Curation Checkpoint

## Stage 1: Discover
- Status: done
- Candidates found: 16
- Sources searched:
  - VoltAgent/awesome-openclaw-skills README.md
  - hermes-agent.nousresearch.com/docs/skills/
  - hermes-agent.nousresearch.com/docs/reference/skills-catalog
  - GitHub search: "openclaw skill HR recruiting resume hiring"
  - GitHub search: "hermes skill hiring interview onboarding agent"
  - GitHub search: "SKILL.md HR recruiting onboarding interview job description"
  - GitHub search: "openclaw skills recruiter-assistant recruitment-automation"
  - GitHub search: "SKILL.md employee handbook payroll HR compliance"
  - tuanductran/hr-skills repository (15 HR skills)
  - OpenJobsAI/openjobs-openclaw-skills repository (4 recruiting skills)
  - 0xNyk/awesome-hermes-agent list
  - LeoYeAI/openclaw-master-skills
  - LobeHub Skills Marketplace
  - Termo.ai skills

### Candidates:
1. tuanductran/hr-skills: hr-recruiting - End-to-end recruiting and talent acquisition
2. tuanductran/hr-skills: hr-onboarding - Employee onboarding and offboarding
3. tuanductran/hr-skills: hr-compliance - Workplace compliance and employee handbook
4. tuanductran/hr-skills: hr-performance-management - Reviews, PIPs, goal setting
5. tuanductran/hr-skills: hr-employee-engagement - Engagement surveys, recognition
6. tuanductran/hr-skills: hr-compensation-benefits - Compensation strategy, benefits
7. tuanductran/hr-skills: hr-training-development - Learning programs
8. tuanductran/hr-skills: hr-analytics - HR data analytics
9. OpenJobsAI/openjobs-people-search - Candidate profile search for recruiting
10. OpenJobsAI/openjobs-people-match - Candidate-job fit evaluation
11. noamseg/interview-coach-skill - Interview coaching for job seekers
12. poferraz/career-ops - All-in-one career operations (resume, interview prep, etc.)
13. gakkiismywife/recruiter-assistant - Automated resume screening (Shenzhen market)
14. afrexai/employee-onboarding - 90-day onboarding program generator
15. Christabel337/job-scout-agent - Autonomous job hunting agent (Hermes)
16. lngdao/agenthire - Agent-to-Agent marketplace (blockchain)

## Stage 2: Evaluate Relevance
- Status: done
- Candidates after filter: 10
- Rejected (with reasons):
  - hr-training-development: More L&D focused, less core HR/recruiting for a business owner
  - hr-analytics: Developer/analyst tool, not directly useful to non-technical business owner
  - lngdao/agenthire: Not HR-related, it's an agent-to-agent blockchain marketplace; flagged Suspicious by VirusTotal
  - Christabel337/job-scout-agent: Job seeker tool (candidate-side), not employer/business owner tool; also uses curl|bash install
  - hr-employee-engagement: Overlaps heavily with hr-performance-management; less core to recruiting/hiring
  - hr-compensation-benefits: Useful but less directly actionable for a small business owner than the other HR skills

### Remaining 10 candidates:
1. tuanductran/hr-skills: hr-recruiting
2. tuanductran/hr-skills: hr-onboarding
3. tuanductran/hr-skills: hr-compliance
4. tuanductran/hr-skills: hr-performance-management
5. OpenJobsAI/openjobs-people-search
6. OpenJobsAI/openjobs-people-match
7. noamseg/interview-coach-skill
8. poferraz/career-ops
9. gakkiismywife/recruiter-assistant
10. afrexai/employee-onboarding

## Stage 3: Safety Audit
- Status: done
- Passed: 8
- Failed (with reasons):
  - gakkiismywife/recruiter-assistant: FAILED - Flagged SUSPICIOUS by both VirusTotal and OpenClaw security scans. Could not retrieve SKILL.md to verify content (404). Untrusted.
  - afrexai/employee-onboarding: FAILED - Could not retrieve SKILL.md (404 on multiple paths). Hosting platform (Termo.ai) showed hardcoded Supabase credentials in client-side JS. Cannot verify skill content for safety. Only 1 install on LobeHub.

### Passed skills audit details:

1. **hr-recruiting** (tuanductran/hr-skills)
   - [x] No curl|bash or remote code execution
   - [x] No hardcoded API keys, tokens, or credentials
   - [x] No data exfiltration
   - [x] No prompt injection
   - [x] No destructive commands
   - [x] No obfuscated/encoded payloads
   - [x] No unauthorized network calls
   - [x] Has valid YAML frontmatter with name and description

2. **hr-onboarding** (tuanductran/hr-skills)
   - [x] All safety checks passed
   - [x] Has valid YAML frontmatter with name and description

3. **hr-compliance** (tuanductran/hr-skills)
   - [x] All safety checks passed
   - [x] Has valid YAML frontmatter with name and description

4. **hr-performance-management** (tuanductran/hr-skills)
   - [x] All safety checks passed
   - [x] Has valid YAML frontmatter with name and description

5. **openjobs-people-search** (OpenJobsAI)
   - [x] No curl|bash or remote code execution
   - [x] No hardcoded API keys (uses MIRA_KEY env var)
   - [x] No data exfiltration (all data from OpenJobs AI database only)
   - [x] No prompt injection
   - [x] No destructive commands
   - [x] No obfuscated/encoded payloads
   - [x] Authorized network calls only (OpenJobs AI API)
   - [x] Has valid YAML frontmatter with name and description

6. **openjobs-people-match** (OpenJobsAI)
   - [x] All safety checks passed (same patterns as people-search)
   - [x] Uses MIRA_KEY env var, HTTPS-only endpoints
   - [x] Has valid YAML frontmatter with name and description

7. **interview-coach** (noamseg)
   - [x] No curl|bash or remote code execution
   - [x] No hardcoded API keys
   - [x] No data exfiltration
   - [x] No prompt injection (structured command routing)
   - [x] No destructive commands
   - [x] No obfuscated/encoded payloads
   - [x] No unauthorized network calls
   - [x] Has valid YAML frontmatter with name and description

8. **career-ops** (poferraz)
   - [x] No curl|bash or remote code execution
   - [x] No hardcoded API keys
   - [x] No data exfiltration
   - [x] No prompt injection
   - [x] No destructive commands
   - [x] No obfuscated/encoded payloads
   - [x] No unauthorized network calls
   - [x] Has valid YAML frontmatter with name and description (missing author/version but name+description present)

## Stage 4: Final Selection
- Status: done
- Selected: 5

### Ranking criteria applied:
1. Business value - How useful is this for a non-technical business owner doing HR/recruiting?
2. Documentation quality - How well-documented is the skill?
3. Community signal - Stars, downloads, forks, maintenance activity

### Rankings:
1. **hr-recruiting** (tuanductran) - Highest business value: covers the full recruiting lifecycle from JD writing to offer letters. Well documented with 6 prompt categories. Part of a maintained 15-skill HR suite. MIT licensed.
2. **openjobs-people-search** (OpenJobsAI) - Direct business value for sourcing candidates. Production-grade API with proper auth, rate limiting, error handling. Part of a 4-skill recruiting suite.
3. **interview-coach** (noamseg) - 1.2k stars, 234 forks, MIT license. Comprehensive 23-command coaching system. High documentation quality with structured scoring rubrics. Useful for hiring managers preparing interview processes.
4. **hr-onboarding** (tuanductran) - Critical business function: structured onboarding reduces turnover by 82%. Well-documented with pre-boarding through 90-day coverage. Part of maintained HR suite.
5. **hr-compliance** (tuanductran) - Essential for any business owner: employee handbooks, EEO/OSHA/FMLA compliance, harassment prevention policies. Reduces legal risk. Well-documented.

### Runners-up (not selected):
- career-ops (poferraz): Only 6 stars, 0 forks. Candidate-side focus (resume writing, job search) rather than employer-side HR. Lower community signal.
- openjobs-people-match: Strong but overlaps with people-search; selecting one OpenJobs skill is sufficient.
- hr-performance-management: Valuable but slightly less critical than recruiting, onboarding, and compliance for a business owner getting started with HR.

## Final Output

- **[HR Recruiting & Talent Acquisition](https://github.com/tuanductran/hr-skills)** - End-to-end recruiting support that helps business owners write job descriptions, create interview questions, screen resumes, draft offer letters, and build employer branding -- covering the full hiring lifecycle from sourcing to close. `openclaw`
- **[OpenJobs People Search](https://github.com/OpenJobsAI/openjobs-openclaw-skills)** - Searches and retrieves professional candidate profiles for recruiting and talent sourcing, with structured filtering by skills, experience, and location, plus side-by-side candidate comparison and talent pool analytics. `openclaw`
- **[Interview Coach](https://github.com/noamseg/interview-coach-skill)** - A high-rigor interview coaching system with 23 commands covering structured prep, transcript analysis, practice drills, storybank management, and performance tracking across PM, Engineering, Design, and other roles. `openclaw`
- **[HR Onboarding & Offboarding](https://github.com/tuanductran/hr-skills)** - Designs complete employee onboarding programs with pre-boarding checklists, orientation schedules, buddy systems, 30/60/90-day milestone plans, and exit interview processes to reduce early turnover and accelerate new hire productivity. `openclaw`
- **[HR Compliance & Workplace Policies](https://github.com/tuanductran/hr-skills)** - Guides business owners through employment law compliance (EEO, OSHA, FMLA, ADA), employee handbook creation, harassment prevention policies, workplace investigations, and HR audit preparation to reduce legal risk. `openclaw`
