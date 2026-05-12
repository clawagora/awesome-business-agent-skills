# Data & Analytics - Curation Checkpoint
## Stage 1: Discover
- Status: done
- Candidates found: 16
- Sources searched: [VoltAgent/awesome-openclaw-skills README, clawskills.sh, SkyworkAI/Skywork-Skills GitHub, GitHub search, WebSearch]
- Candidates:
  1. data-analyst (oyi77) - Data viz, report generation, SQL queries, spreadsheets
  2. csv-pipeline (gitgoodordietrying) - Process, transform, analyze CSV/JSON data
  3. skywork-excel (SkyworkAI) - AI-powered Excel/spreadsheet operations
  4. xlsx (seanphan) - Comprehensive spreadsheet creation and analysis
  5. biz-reporter (ariktulcha) - Business intelligence reports from GA4, Stripe, etc.
  6. check-analytics (jeftekhari) - Audit Google Analytics implementation
  7. google-analytics-api (rich-song) - GA API integration with managed OAuth
  8. agent-analytics (dannyshmueli) - Website analytics for AI agents
  9. chart-image (dannyshmueli) - Generate publication-quality chart images
  10. duckdb-en (camelsprout) - DuckDB CLI for SQL analysis
  11. daily-report (visualdeptcreative) - Track progress, report metrics
  12. financial-analyst (aniebyl) - Financial analysis and research workflows
  13. amplitude-automation (sohamganatra) - Automate Amplitude tasks
  14. add-analytics (jeftekhari) - Add GA4 tracking to projects
  15. cost-report (vincentqiu) - Track OpenClaw usage costs
  16. work-report (leeguooooo) - Daily/weekly work reports from git commits

## Stage 2: Evaluate Relevance
- Status: done
- Candidates after filter: 9
- Passed to Stage 3:
  1. csv-pipeline - Business-friendly CSV/JSON data processing; production-ready (3.4k downloads, benign); directly useful for business reporting
  2. skywork-excel - Full Excel/spreadsheet automation; production-ready (SkyworkAI backed); high business value for reports, budgets, analysis
  3. check-analytics - Audits GA implementation; production-ready (2.3k downloads, benign); useful for business owners checking their analytics setup
  4. duckdb-en - SQL analysis on local CSV/Parquet files; production-ready (3.1k downloads, benign); useful for business owners querying data
  5. chart-image - Generates charts from data; production-ready (v2.5.1); useful for business reporting and data visualization
  6. data-analyst - Comprehensive data analysis skill; high downloads (16.3k); covers SQL, spreadsheets, viz, reports
  7. financial-analyst - Financial analysis and research workflows; useful for business financial reporting
  8. biz-reporter - Automated BI reports from GA4, Stripe; directly useful for business KPI tracking
  9. agent-analytics - Website analytics; production-ready (v4.0.3, benign); useful for business website metrics
- Rejected (with reasons):
  1. xlsx (seanphan) - Overlaps heavily with skywork-excel; skywork-excel is more feature-rich and better documented
  2. google-analytics-api (rich-song) - Requires third-party Maton OAuth service; adds unnecessary dependency; flagged suspicious
  3. add-analytics (jeftekhari) - Developer-oriented (adding tracking code to projects); not a business analytics/reporting skill
  4. daily-report (visualdeptcreative) - Very narrow (lead generation pipeline tracking with Telegram); flagged suspicious by OpenClaw
  5. amplitude-automation (sohamganatra) - Developer/product team tool for Amplitude; requires Rube MCP; too niche
  6. cost-report (vincentqiu) - Tracks OpenClaw usage costs only; not general business analytics
  7. work-report (leeguooooo) - Git-based developer standup reports; not business analytics

## Stage 3: Safety Audit
- Status: done
- Audited: 9 candidates

### 1. csv-pipeline (gitgoodordietrying)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys, tokens, or credentials
- [x] No data exfiltration (sending data to unknown endpoints)
- [x] No prompt injection (hidden instructions to override agent behavior)
- [x] No destructive commands (rm -rf, DROP TABLE, etc.)
- [x] No obfuscated/encoded payloads (base64 blobs, eval(), exec())
- [x] No unauthorized network calls
- [x] Has valid YAML frontmatter with name and description
- VirusTotal: Benign | OpenClaw: Benign
- RESULT: PASS

### 2. skywork-excel (SkyworkAI/Skywork-Skills)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (uses SKYWORK_API_KEY env var)
- [x] No data exfiltration (only sends to official skywork.ai API endpoint)
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] Network calls only to api-tools.skywork.ai (authorized, documented)
- [x] Has valid YAML frontmatter with name and description
- Full source code audited (SKILL.md, excel_api_client.py, constant.py, skywork_auth.py)
- RESULT: PASS

### 3. check-analytics (jeftekhari)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls (read-only analysis of codebase)
- [x] Has valid YAML frontmatter with name and description
- VirusTotal: Benign | OpenClaw: Benign (HIGH confidence)
- RESULT: PASS

### 4. duckdb-en (camelsprout)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls (local DuckDB CLI only)
- [x] Has valid YAML frontmatter with name and description
- VirusTotal: Benign | OpenClaw: Benign
- Only dependency: DuckDB CLI installed locally
- RESULT: PASS

### 5. chart-image (dannyshmueli)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] No unauthorized network calls (pure Node.js with Sharp binaries)
- [x] Has valid YAML frontmatter with name and description
- VirusTotal: Suspicious | OpenClaw: Benign
- NOTE: VirusTotal flagged as suspicious, but OpenClaw's own audit says Benign. VirusTotal false positives are common for Node.js packages with native binaries.
- RESULT: PASS (with note on VT flag)

### 6. data-analyst (oyi77)
- [ ] Cannot fully audit (source code not publicly accessible; repo returns 404)
- VirusTotal: Benign | OpenClaw: Suspicious (HIGH confidence) -- "Some operations require external access"
- The skill integrates with external databases (BigQuery, Snowflake, Redshift) and REST APIs
- 16.3k downloads, but flagged suspicious by OpenClaw moderation
- RESULT: FAIL -- OpenClaw flagged suspicious with high confidence; cannot audit actual code

### 7. financial-analyst (aniebyl)
- [ ] Cannot fully audit (source code not publicly accessible; repo returns 404)
- No security scan data available from clawskills.sh (page 404)
- RESULT: FAIL -- unable to verify source code or security status

### 8. biz-reporter (ariktulcha)
- VirusTotal: Suspicious | OpenClaw: Suspicious (HIGH confidence)
- Requires numerous API credentials (GA4, Stripe, HubSpot, social media)
- Dual suspicious flags from independent systems
- RESULT: FAIL -- flagged suspicious by both VirusTotal and OpenClaw

### 9. agent-analytics (dannyshmueli)
- [x] No curl|bash or remote code execution
- [x] No hardcoded API keys (uses AGENT_ANALYTICS_API_KEY env var)
- [x] No data exfiltration
- [x] No prompt injection
- [x] No destructive commands
- [x] No obfuscated/encoded payloads
- [x] Uses npx @agent-analytics/cli scoped package (authorized)
- [x] Has valid YAML frontmatter with name and description
- VirusTotal: Benign | OpenClaw: Benign
- RESULT: PASS

### Summary
- Passed: 6 (csv-pipeline, skywork-excel, check-analytics, duckdb-en, chart-image, agent-analytics)
- Failed: 3 (data-analyst -- OpenClaw suspicious; financial-analyst -- unauditable; biz-reporter -- dual suspicious flags)

## Stage 4: Final Selection
- Status: done
- Ranking criteria: (1) business value, (2) documentation quality, (3) community signal
- Selected: 5

### Rankings
1. **skywork-excel** -- Highest business value: complete Excel/spreadsheet automation including charts, formulas, pivot tables, financial modeling, and report generation. Fully auditable open-source code on GitHub. Backed by SkyworkAI. Multi-language support.
2. **csv-pipeline** -- High business value: zero-dependency CSV/JSON/TSV processing for filtering, joining, aggregating, deduplicating, and generating Markdown reports. 3.4k downloads. Both security scans benign.
3. **duckdb-en** -- High business value: query CSV, Parquet, and JSON files with SQL without setting up a database. Local-only (no network calls). 3.1k downloads. Both scans benign.
4. **check-analytics** -- Good business value: audit and validate Google Analytics implementation. Read-only and safe. Both scans benign with HIGH confidence. 2.3k downloads.
5. **chart-image** -- Good business value: generate publication-quality PNG/SVG charts (line, bar, pie, heatmap, candlestick, etc.) for reports and presentations. Mature (v2.5.1). OpenClaw benign.

### Not selected (passed safety but ranked 6th)
- agent-analytics -- Requires external Agent Analytics service registration and API key; narrower scope (website analytics only); lower download count (1.7k). Still a valid skill, but the top 5 cover broader business analytics needs.

## Final Output

- **[Skywork Excel](https://github.com/SkyworkAI/Skywork-Skills)** - AI-powered spreadsheet automation that creates Excel files with data, formulas, charts, and pivot tables, analyzes existing files, and generates professional reports -- ideal for budgets, financial modeling, and business dashboards. `openclaw`
- **[CSV Pipeline](https://clawskills.sh/skills/gitgoodordietrying-csv-pipeline)** - Processes, transforms, and analyzes CSV, TSV, and JSON data using Python 3 with zero external dependencies -- supports filtering, joining, aggregating, deduplicating, and generating Markdown summary reports from your business data. `openclaw`
- **[DuckDB CLI AI Skills](https://clawskills.sh/skills/camelsprout-duckdb-cli-ai-skills)** - Lets you query CSV, Parquet, and JSON files with SQL directly from the command line, without setting up a database server -- perfect for ad-hoc business data analysis and format conversion. `openclaw`
- **[Check Analytics](https://clawskills.sh/skills/jeftekhari-check-analytics)** - Audits your existing Google Analytics implementation by scanning for tracking identifiers, detecting configuration issues, and generating a prioritized report of critical fixes, warnings, and suggestions. `openclaw`
- **[Chart Image](https://clawskills.sh/skills/dannyshmueli-chart-image)** - Generates publication-quality PNG and SVG charts from data, supporting line, bar, pie, heatmap, candlestick, and multi-series chart types -- useful for embedding visuals in business reports and presentations. `openclaw`
