# Claude Code Skills — SEO & Content

Custom skills for [Claude Code](https://claude.ai/code) covering technical SEO audits, semantic SEO optimization, and content creation. Built on Koray Tugberk Gubur's Topical Authority framework.

## Skills

### Audits

| Skill | Path | Description |
|-------|------|-------------|
| **Full-Site Audit** | `audits/full-site-audit/` | Deterministic, evidence-backed SEO audits for websites, blog posts, and GitHub repos. 16 sub-skills, 10 specialist agents, 33 Python scripts, 11 report templates. Produces `FULL-AUDIT-REPORT.md` and `ACTION-PLAN.md`. |
| **Content Audit** | `audits/content-audit/` | Audits existing content for semantic gaps, topical coverage, frame semantics completeness, and AI citation readiness. Evaluates intent distribution (TOFU/MOFU/BOFU) and identifies cannibalization. |

### Semantic SEO

| Skill | Path | Description |
|-------|------|-------------|
| **Agentic SEO** | `semantic-seo/agentic-seo/` | Standalone, installable version of the full-site audit skill with cross-IDE support (Claude Code, Codex, Antigravity). Includes install scripts, CI workflow, and documentation. |
| **Internal Linking** | `semantic-seo/internal-linking/` | Plans and optimizes internal links using contextual bridges, anchor text strategy, and hub-and-spoke architecture. Classifies links as S-nodes (structural), C-nodes (content block), and I-nodes (contextual). |
| **Entity Optimizer** | `semantic-seo/entity-optimizer/` | Maps Entity-Attribute-Value relationships, builds lexical coverage across 17 relationship types, and optimizes for Knowledge Panels and AI citations. |
| **Topical Map** | `semantic-seo/topical-map/` | Builds semantic topical maps with query networks, frame semantics coverage, and pillar-cluster architecture. Identifies the "Compounding Threshold" (60% coverage = topical authority). |

### Content

| Skill | Path | Description |
|-------|------|-------------|
| **Content Brief** | `content/content-brief/` | Generates 10-component semantic briefs: heading vectors, extractive answers, EAV triplets, 6-source questions, internal link plans, schema specs, and competitor analysis. |
| **Semantic Writer** | `content/semantic-writer/` | Writes or rewrites content following 41 authorship rules for semantic SEO. Covers sentence structure, entity coverage, answer formatting, lexical depth, and featured snippet optimization. |

## Workflow

The skills form an integrated pipeline:

```
Topical Map → Content Brief → Semantic Writer
     ↓              ↓              ↓
Entity Optimizer   Internal Linking
     ↓              ↓
Content Audit ← Full-Site Audit
```

1. **Topical Map** — plan the content architecture
2. **Content Brief** — spec out individual articles
3. **Semantic Writer** — write the articles
4. **Entity Optimizer** — ensure complete entity coverage
5. **Internal Linking** — connect the articles
6. **Content Audit** — evaluate gaps in existing content
7. **Full-Site Audit** — comprehensive technical + content SEO analysis

## Full-Site Audit Resources

The full-site audit includes an extensive resource library:

**10 Specialist Agents** — Technical, Content, Performance, Schema, Sitemap, Visual, Verifier, GitHub Data, GitHub Analyst, GitHub Benchmark

**33 Python Scripts** — Automated evidence collection for robots, PageSpeed, security headers, broken links, redirects, schema validation, readability, internal links, hreflang, entity checking, duplicate content, social meta, GSC, IndexNow, llms.txt, GitHub SEO, and more

**16 Sub-Skills** — Page audit, technical audit, content analysis, schema validation, sitemap check, hreflang, images, links, article SEO, AEO, GEO, programmatic SEO, competitor pages, GitHub SEO, SEO planning, full audit orchestration

**11 Report Templates** — Generic, SaaS, eCommerce, agency, local service, blog post, news article, technical article, publisher, GitHub SEO report, GitHub weekly scorecard

**10 Reference Guides** — Google SEO reference, E-E-A-T framework, Core Web Vitals thresholds, quality gates, schema types, link building, LLM audit rubric, README audit rubric, GitHub ranking factors, GitHub API operations

## Installation

Copy the skill folders into your Claude Code skills directory:

```bash
# Clone the repo
git clone https://github.com/bartmagera/claude-skills.git

# Copy all skills
cp -R claude-skills/* ~/.claude/skills/

# Or copy individual skills
cp -R claude-skills/audits/full-site-audit ~/.claude/skills/audits/
cp -R claude-skills/content/semantic-writer ~/.claude/skills/content/
```

## Requirements

- [Claude Code](https://claude.ai/code)
- Python 3.8+ (for audit scripts)
- `pip install requests beautifulsoup4` (minimum dependencies)
- Optional: Playwright (`pip install playwright && playwright install`) for visual analysis
- Optional: GitHub CLI (`gh`) for GitHub SEO features

## License

See individual skill directories for licensing. The Agentic SEO skill includes its own [LICENSE](semantic-seo/agentic-seo/LICENSE).
