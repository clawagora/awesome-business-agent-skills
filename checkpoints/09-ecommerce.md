# E-Commerce - Curation Checkpoint
## Stage 1: Discover
- Status: done
- Candidates found: 16
- Sources searched: [VoltAgent/awesome-openclaw-skills README, shopping-and-e-commerce.md category, hermes-agent.nousresearch.com/docs/skills/, 0xNyk/awesome-hermes-agent, GitHub search for openclaw/hermes ecommerce/shopify/stripe/payment skills, clawskills.sh, clawhub.ai, playbooks.com]

### Candidates:
1. **shopify** (openclaw, mrgoodb) - Manage Shopify stores via Admin REST API
2. **clawpify** (openclaw, alhwyn) - Query and manage Shopify stores via GraphQL Admin API
3. **shopify** (hermes, NousResearch) - Shopify Admin & Storefront GraphQL APIs via curl
4. **stripe-integration-expert** (openclaw, alirezarezvani) - Stripe payment integration patterns
5. **payment** (openclaw, openclaw/skills) - Multi-gateway payment processing and invoice management
6. **ecommerce** (openclaw, openclaw/skills) - E-commerce store architecture and operations guide
7. **whop-cli** (openclaw, g9pedro) - Manage Whop digital products store
8. **atoship** (openclaw, atoship-dev) - Ship packages, compare rates, buy labels across carriers
9. **clawver-digital-products** (openclaw, nwang783) - Create and sell digital products on Clawver
10. **eachlabs-product-visuals** (openclaw, eftalyurtseven) - Generate e-commerce product photography
11. **hermes-payguard** (hermes, nativ3ai) - Safe USDC and x402 payments with spending limits
12. **dropshipping** (openclaw, ivangdavila) - Shopify dropshipping guidance and risk management
13. **buy-anything** (openclaw, tsyvic) - Purchase products from Amazon conversationally
14. **amazon-product-api-skill** (openclaw, phheng) - Extract product listings from Amazon
15. **ad-ready** (openclaw, pauldelavallaz) - Generate advertising images from product URLs
16. **closing-deals** (openclaw, jk-0001) - Close sales deals as a solopreneur

## Stage 2: Evaluate Relevance
- Status: done
- Candidates after filter: 9
- Rejected (with reasons):
  - stripe-integration-expert: Developer guidance skill, provides code patterns not direct payment management; not useful to non-technical business owners
  - ecommerce: Knowledge-base skill providing guidance and code patterns, does not connect to live APIs or execute actions
  - hermes-payguard: Crypto-focused (USDC/x402), not mainstream e-commerce payments; too niche for general business owners
  - dropshipping: Guidance/knowledge document, not a direct integration or operational tool
  - buy-anything: Consumer purchasing tool, not a business operations tool
  - ad-ready: Marketing/advertising image generation, tangential to core e-commerce operations
  - closing-deals: Sales technique skill, not e-commerce operations

### Remaining candidates (9):
1. **shopify** (openclaw, mrgoodb) - Manage Shopify stores via Admin REST API
2. **clawpify** (openclaw, alhwyn) - Query and manage Shopify stores via GraphQL Admin API
3. **shopify** (hermes, NousResearch) - Shopify Admin & Storefront GraphQL APIs via curl
4. **payment** (openclaw) - Multi-gateway payment processing and invoice management
5. **whop-cli** (openclaw, g9pedro) - Manage Whop digital products store
6. **atoship** (openclaw, atoship-dev) - Ship packages, compare rates, buy labels
7. **clawver-digital-products** (openclaw, nwang783) - Create and sell digital products
8. **eachlabs-product-visuals** (openclaw, eftalyurtseven) - Generate product photography
9. **amazon-product-api-skill** (openclaw, phheng) - Extract product data from Amazon

## Stage 3: Safety Audit
- Status: done
- Passed: 8
- Failed (with reasons):
  - amazon-product-api-skill: FAILED - Flagged as Suspicious by BOTH VirusTotal AND OpenClaw moderation systems; routes data through third-party BrowserAct service (api.browseract.com), raising data exfiltration concerns

### Audit details for passed candidates:

1. **shopify (openclaw, mrgoodb)** - PASS
   - [x] No curl|bash or remote code execution
   - [x] No hardcoded API keys (uses SHOPIFY_STORE, SHOPIFY_ACCESS_TOKEN env vars)
   - [x] No data exfiltration (communicates only with Shopify Admin API)
   - [x] No prompt injection
   - [x] No destructive commands
   - [x] No obfuscated/encoded payloads
   - [x] No unauthorized network calls
   - [x] Valid YAML frontmatter with name and description

2. **clawpify (openclaw, alhwyn)** - PASS
   - [x] No curl|bash (uses shopify_graphql tool)
   - [x] No hardcoded API keys (uses Shopify access token from env)
   - [x] No data exfiltration (Shopify GraphQL API only)
   - [x] No prompt injection
   - [x] No destructive commands (requires explicit user permission for destructive ops)
   - [x] No obfuscated/encoded payloads
   - [x] No unauthorized network calls
   - [x] Valid YAML frontmatter
   - Note: OpenClaw "Suspicious" flag due to broad API authority, but operational risk not malicious

3. **shopify (hermes, NousResearch)** - PASS
   - [x] No curl|bash piped execution (curl for GraphQL API calls only)
   - [x] No hardcoded API keys (uses SHOPIFY_ACCESS_TOKEN, SHOPIFY_STORE_DOMAIN env vars)
   - [x] No data exfiltration (Shopify domains only)
   - [x] No prompt injection
   - [x] No destructive commands (warns about mutations, advises confirmation)
   - [x] No obfuscated/encoded payloads
   - [x] No unauthorized network calls
   - [x] Valid YAML frontmatter (name, description, version, author, license, platforms, prerequisites)

4. **payment (openclaw)** - PASS
   - [x] No curl|bash
   - [x] No hardcoded keys (explicitly warns against storing raw credentials)
   - [x] No data exfiltration
   - [x] No prompt injection
   - [x] No destructive commands
   - [x] No obfuscated/encoded payloads
   - [x] No unauthorized network calls
   - [x] Valid YAML frontmatter

5. **whop-cli (openclaw, g9pedro)** - PASS
   - [x] No curl|bash (uses npm SDK)
   - [x] No hardcoded keys (uses WHOP_API_KEY, WHOP_COMPANY_ID env vars)
   - [x] No data exfiltration (Whop API only)
   - [x] No prompt injection
   - [x] No destructive commands
   - [x] No obfuscated/encoded payloads
   - [x] No unauthorized network calls
   - [x] Valid YAML frontmatter

6. **atoship (openclaw, atoship-dev)** - PASS
   - [x] No curl|bash
   - [x] No hardcoded keys (uses ATOSHIP_API_KEY env var)
   - [x] No data exfiltration (communicates exclusively with atoship.com)
   - [x] No prompt injection
   - [x] No destructive commands
   - [x] No obfuscated/encoded payloads
   - [x] No unauthorized network calls
   - [x] Valid YAML frontmatter
   - Explicit user confirmation required before wallet-affecting actions

7. **clawver-digital-products (openclaw, nwang783)** - PASS
   - [x] No curl|bash
   - [x] No hardcoded keys (uses CLAW_API_KEY env var)
   - [x] No data exfiltration (api.clawver.store only)
   - [x] No prompt injection
   - [x] No destructive commands
   - [x] No obfuscated/encoded payloads
   - [x] No unauthorized network calls
   - [x] Valid YAML frontmatter
   - VirusTotal and OpenClaw: both Benign

8. **eachlabs-product-visuals (openclaw, eftalyurtseven)** - PASS
   - [x] No curl|bash
   - [x] No hardcoded keys (uses EACHLABS_API_KEY env var)
   - [x] No data exfiltration (eachlabs.ai only)
   - [x] No prompt injection
   - [x] No destructive commands
   - [x] No obfuscated/encoded payloads
   - [x] No unauthorized network calls
   - [x] Valid YAML frontmatter
   - VirusTotal: Benign; OpenClaw: Suspicious (expected for image generation external access)

## Stage 4: Final Selection
- Status: done
- Selected: 5

### Ranking criteria: (1) business value, (2) documentation quality, (3) community signal

| Rank | Skill | Business Value | Doc Quality | Community Signal | Score |
|------|-------|---------------|-------------|-----------------|-------|
| 1 | shopify (hermes) | 10/10 | 10/10 | 10/10 | 30 |
| 2 | clawpify (openclaw) | 9/10 | 9/10 | 8/10 | 26 |
| 3 | atoship (openclaw) | 9/10 | 9/10 | 7/10 | 25 |
| 4 | payment (openclaw) | 9/10 | 8/10 | 7/10 | 24 |
| 5 | whop-cli (openclaw) | 8/10 | 8/10 | 6/10 | 22 |

### Not selected (passed safety but lower ranked):
- shopify (openclaw, mrgoodb): Uses legacy REST API (deprecated since 2024-04), overlaps with clawpify and hermes shopify which use the recommended GraphQL API
- clawver-digital-products: Platform-specific (Clawver only), narrower applicability
- eachlabs-product-visuals: Useful but supplementary to core e-commerce operations

## Final Output

- **[Shopify](https://github.com/NousResearch/hermes-agent/blob/main/optional-skills/productivity/shopify/SKILL.md)** - Official Shopify-built skill that lets your agent manage products, orders, inventory, customers, and fulfillments across your Shopify store using the modern GraphQL Admin API. Built by the Shopify team with comprehensive documentation covering every core store operation. `hermes`

- **[Clawpify](https://clawskills.sh/skills/alhwyn-clawpify)** - Query and manage your Shopify store via the GraphQL Admin API, covering products, orders, customers, inventory levels, discount codes, and bulk exports. Requires explicit user confirmation before any destructive action like refunds or cancellations. `openclaw`

- **[Atoship](https://clawskills.sh/skills/atoship-dev-atoship)** - Compare live shipping rates across USPS, FedEx, and UPS, purchase discounted labels, track packages, and generate return labels -- all without visiting individual carrier websites. Requires explicit confirmation before any purchase. `openclaw`

- **[Payment](https://playbooks.com/skills/openclaw/skills/payment)** - Streamlines payment processing and invoice management across multiple gateways including Stripe, PayPal, Square, and crypto providers, with transaction reconciliation, refund handling, and audit logging built in. `openclaw`

- **[Whop CLI](https://clawskills.sh/skills/g9pedro-whop-cli)** - Manage your Whop digital products store end-to-end: create products and pricing plans, generate checkout links, track payments, handle memberships, and set up promo codes. `openclaw`
