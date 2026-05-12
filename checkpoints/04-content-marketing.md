# Content & Marketing - Curation Checkpoint

## Stage 1: Discover
- Status: done
- Candidates found: 20
- Sources searched:
  - VoltAgent/awesome-openclaw-skills README.md
  - VoltAgent/awesome-openclaw-skills categories/marketing-and-sales.md
  - Hermes Agent Skills Hub (hermes-agent.nousresearch.com/docs/skills/)
  - NousResearch/hermes-agent GitHub skills directory
  - GitHub search: "openclaw skill content marketing SEO blog writing"
  - GitHub search: "hermes skill blog social media copywriting newsletter"
  - Web search: "awesome openclaw skills content creation marketing 2025 2026"
  - Web search: hermes agent skills hub copywriting content marketing
  - ClawSkills.sh registry pages for individual skills
  - Felo.ai blog on best Hermes agent skills 2026

## Stage 2: Evaluate Relevance
- Status: done
- Candidates after filter: 10
- Rejected (with reasons):
  - brand-voice-profile: Flagged suspicious by both VirusTotal and OpenClaw
  - blog-writer: Flagged suspicious by OpenClaw (HIGH confidence)
  - ad-ready: Flagged suspicious by both VirusTotal and OpenClaw
  - b2c-marketing: Flagged suspicious by VirusTotal
  - brw-newsletter-creation-curation: Flagged suspicious by OpenClaw
  - aeo-analytics-free: Flagged suspicious by OpenClaw (analytics, not content creation)
  - content-creator: Deprecated skill; redirects to specialist skills
  - postiz: Source repo returns 404; cannot verify code
  - bird (X/Twitter CLI): Uses cookie-based auth, more of a dev tool than business skill
  - bluesky: Social posting CLI, more developer-oriented than business-owner focused

## Stage 3: Safety Audit
- Status: done
- Passed: 10
- Failed (with reasons): none among the filtered set

### Audit Details

| Skill | curl/bash | Hardcoded keys | Exfiltration | Prompt injection | Destructive cmds | Obfuscated code | Unauth network | Valid YAML | VT | OpenClaw |
|-------|-----------|---------------|-------------|-----------------|------------------|-----------------|----------------|------------|-----|---------|
| reef-copywriting | No | No | No | No | No | No | No | Yes | Benign | Benign (HIGH) |
| content-recycler | No | No | No | No | No | No | No | Yes | Benign | Benign (HIGH) |
| citedy-seo-agent | No | No | No | No | No | No | No | Yes | Benign | Benign |
| meta-tags-optimizer | No | No | No | No | No | No | No | Yes | Benign | Benign (HIGH) |
| aeo-content-free | No | No | No | No | No | No | No | Yes | Benign | Benign (HIGH) |
| blogburst | No | No | No | No | No | No | No | Yes | Benign | Benign (HIGH) |
| sovereign-brand-voice-writer | No | No | No | No | No | No | No | Yes | Benign | Benign (HIGH) |
| email-marketing-2 | No | No | No | No | No | No | No | Yes | Benign | Benign (HIGH) |
| ghost-cms | No | No | No | No | No | No | No | Yes | Benign | Benign (v0.1.8) |
| youtube-content (Hermes) | No | No | No | No | No | No | No | Yes | N/A | N/A (bundled) |

## Stage 4: Final Selection
- Status: done
- Selected: 5

### Ranking Criteria
1. Business value: How much does this save a non-technical business owner in time/money?
2. Documentation quality: Clear instructions, examples, well-structured SKILL.md?
3. Community signal: Download counts, version maturity, active maintenance

### Final Rankings
1. **content-recycler** - High business value (repurposes one piece into 6+ platform formats), 1,971 downloads, clear workflow
2. **reef-copywriting** - Direct revenue impact (landing pages, sales copy), 6 proven frameworks, standalone with no dependencies
3. **blogburst** - High leverage (one article becomes 10+ social posts), API-based, version 3.1.2 (mature)
4. **meta-tags-optimizer** - Foundational SEO value, version 3.0.0 (mature), no external dependencies
5. **aeo-content-free** - Forward-looking (AI search optimization), research-driven workflow, free tier

## Final Output

- **[Content Recycler](https://clawskills.sh/skills/michael-laffin-content-recycler)** - Transforms a single blog post or article into platform-optimized content for Twitter/X, LinkedIn, Instagram, TikTok, Facebook, and email, saving hours of manual repurposing work. `openclaw`
- **[Reef Copywriting](https://clawskills.sh/skills/staybased-reef-copywriting)** - Generates landing pages, product descriptions, ads, and sales copy using six proven direct-response frameworks (PAS, AIDA, FAB, BAB, 4Ps, Star-Story-Solution) with no external dependencies. `openclaw`
- **[BlogBurst](https://clawskills.sh/skills/shensi8312-blogburst)** - Turns any article into 10+ ready-to-publish social media posts across X, Bluesky, Telegram, and Discord in seconds, managing the full content-to-social pipeline. `openclaw`
- **[Meta Tags Optimizer](https://clawskills.sh/skills/aaron-he-zhu-meta-tags-optimizer)** - Generates optimized title tags, meta descriptions, Open Graph tags, and Twitter cards with CTR-focused A/B test variations to improve search visibility and social sharing. `openclaw`
- **[AEO Content Free](https://clawskills.sh/skills/psyduckler-aeo-content-free)** - Creates content optimized to get cited by AI assistants like ChatGPT, Gemini, and Perplexity, researching competitors and coverage gaps to boost your brand's AI search visibility. `openclaw`
