---
name: product-dossier
description: |
  PRIMARY entry point for all product research. Use this when user wants to: 收集产品资料, 收集XX的产品资料, 做产品资料收集, 建产品资料库, 产品调研, 做产品调研, research a product, collect product info, build product dossier, product deep-dive for video script. Internally calls market-research-analysis for industry context, then applies Raymond's 10-dimension framework with layered injection. Output is 10 chapter files + 1 combined master per product. IMPORTANT: when user asks about a specific product (not a market/industry category), use this skill — not market-research-analysis alone.
---

# Product Dossier Builder

Two-phase product research system for video script production. Phase 1 gathers industry/market context via market-research-analysis skill. Phase 2 applies Raymond's 11-dimension product framework, with market findings injected at defined points.

---

## When to Use

Trigger when the user:
- Asks to "collect product info" or "build product dossier" for a new product
- Mentions a product they want to make a video about
- Says "research X product" in the context of their JJXS Studio workflow
- Asks to apply "my product research system" to a new item

## When NOT to Use

- Pure market/industry reports without a specific product → use market-research-analysis directly
- Simple spec lookups or one-off questions
- Non-physical products (software, services) — the framework can adapt but needs user confirmation first

---

## Phase 0: Setup

Before any research begins:

1. **Confirm the product** with user — exact model, configuration, and any known context (e.g., "I have the device" vs "no device yet")
2. **Confirm the output directory** — default is `~/Documents/JJXS_Studio/02-产品资料/[产品名]/`
3. **Check if there's an existing topic** in `~/Documents/JJXS_Studio/01-选题/`
4. **Create the directory** and begin

---

## Phase 1: Market Context (market-research-analysis)

**Run this FIRST**, before any product-specific research. Invoke the market-research-analysis skill with a prompt focused on the product's category:

```
Analyze the [PRODUCT CATEGORY] market. Focus on:
1. Industry trends and growth direction
2. Competitive landscape (top 5 players, their positioning, market share)
3. Consumer behavior insights (purchase drivers, price sensitivity bands, replacement cycles)
4. Technology trends affecting this category

Keep it concise — this feeds into a product-level dossier, not a standalone report.
```

**Extract these specific outputs for injection:**

| Output | Format | Inject Into |
|--------|--------|-------------|
| Category trend direction | 1-2 sentences: growing/shrinking/transforming, key driver | 05-核心卖点与短板 (context for value judgment) |
| Top 5 competitors with positioning | Brief table: player, positioning, price band, key differentiator | 07-使用场景深度分析 (enriches competitor comparison) |
| Consumer purchase drivers | Top 3-5 factors ranked by importance | 06-消费者核心问题 (validates user persona and buying barriers) |
| Price sensitivity band | The range most buyers consider acceptable | 01-产品基本盘 (context for price trend judgment) |
| Replacement/upgrade cycle | Typical ownership period | 04-关键变化 (context for "vs previous gen" upgrade advice) |

**Critical rule:** Market-research provides *context*, not *conclusions*. The final judgment on "is this product worth buying" always comes from the product-level analysis in Phase 2.

---

## Phase 2: Product Deep Dive (Self-Built Framework)

Build all 11 dimensions. Run independent research tasks in parallel where possible (web search + web fetch for specs, reviews, community feedback, competitor comparisons).

### The 11 Dimensions

| # | File | Core Question | Key Tables |
|---|------|--------------|------------|
| 00 | `00-概要与收集状态.md` | Where are we in the research process? | Collection status dashboard |
| 01 | `01-产品基本盘.md` | What is this product? | Spec table (dimension/param/one-line interpretation/source), Price matrix (channel/config/price/note/source), Timeline |
| 02 | `02-技术剖析.md` | Where does the key tech come from, and how was it engineered? | Tech deep-dive (tech/origin & evolution/problem it solves/implementation approach/measured result/source) |
| 03 | `03-核心技术解析.md` | What's the tech behind the marketing? | Tech breakdown (tech/marketing claim/actual principle/real user value/source), Limitations list |
| 04 | `04-关键变化.md` | What changed vs last gen / within product line? | Gen-over-gen comparison (dimension/current/last gen/delta/feelable difference/source), Product line positioning, Performance data |
| 05 | `05-核心卖点与短板.md` | What matters and what doesn't? | TOP 3 selling points (what/why/unique), TOP 3 weaknesses (scenario/severity/condition), Perception vs reality value matrix |
| 06 | `06-消费者核心问题.md` | Who buys this and why do they hesitate? | User personas (type/share/scenario/triggers/barriers), Top 3 purchase barriers (pro/con/Raymond's take), Real user feedback (positive/negative/surprises/audience questions) |
| 07 | `07-使用场景深度分析.md` | How does it perform in real use? | Scene analysis (scene/requirements/expected/bottleneck/to-test), Limit scenarios, Competitor comparison |
| 08 | `08-争议与品控.md` | What's wrong with it? | Controversy table (issue/viewpoints/source/own judgment/impact on purchase), QC issues, To-test checklist |
| 09 | `09-数据来源索引.md` | Where did the info come from? | Source table (source/content/credibility) |
| 10 | `10-脚本关键结论.md` | What goes into the video? | One-line verdict, 3 must-say points, 3 must-be-honest points, Purchase boundary conditions, Differentiation angle, Visual shot list, Voiceover drafts |

### Injection Points (Market → Product)

When writing each chapter, pull in Phase 1 findings at these specific locations:

**05-核心卖点与短板, after TOP 3 weaknesses:**
Add a brief "行业背景" callout:
```
> 行业背景：[Category trend direction from Phase 1]. 
> 这意味着[product]的[strength/weakness]是在[顺/逆]行业趋势。
```

**06-消费者核心问题, within 6.1 Target User Personas:**
Validate or adjust persona share estimates against Phase 1 consumer behavior data. Add a note if market data contradicts assumptions.

**07-使用场景深度分析, within 7.3 Competitor Comparison:**
Add a "格局说明" row or callout summarizing the competitive landscape from Phase 1, so the feature-by-feature comparison is grounded in market reality.

### Writing Standards

Every table follows the pattern: **fact column + interpretation column + source column**. Never give a parameter without a value judgment. Never give a judgment without a source.

Source credibility markers:
- 🔒 = Official / confirmed
- ✅ = Multi-source verified
- ⚠️ = Single source / subjective / rumor
- 🔲 = Not yet collected

**If user HAS the device:** Add a "⏳ 待实测" column to scene analysis tables. Mark all to-test items in 08 accordingly.
**If user does NOT have the device:** All "待实测" items stay 🔲. Flag this in 00 overview.

---

## Phase 3: Assembly

After all chapters are written:

1. **Write individual files** — one per chapter, with frontmatter (`title` + `chapter: N`)
2. **Concatenate the master file** — `产品资料-[产品名].md` combining all 11 chapters
3. **Verify** — run `ls -la` and `wc -l` on the output directory
4. **Report** — tell user the directory path, file count, total line count, and highlight any information gaps

### Directory Structure

```
02-产品资料/[产品名]/
├── 产品资料-[产品名].md          ← Combined master
├── 00-概要与收集状态.md
├── 01-产品基本盘.md
├── 02-技术剖析.md
├── 03-核心技术解析.md
├── 04-关键变化.md
├── 05-核心卖点与短板.md
├── 06-消费者核心问题.md
├── 07-使用场景深度分析.md
├── 08-争议与品控.md
├── 09-数据来源索引.md
└── 10-脚本关键结论.md
```

---

## Quality Checklist

Before reporting completion:

- [ ] All 11 dimensions covered with real data (no placeholder "TBD" sections)
- [ ] At least 3 independent sources per factual claim
- [ ] Phase 1 market context injected at 05, 06, 07
- [ ] Every table has source markers
- [ ] Controversies and QC issues are not suppressed — 08 should have real negative content
- [ ] 10 script conclusions are specific and opinionated, not generic
- [ ] "No device" status clearly marked if applicable
- [ ] Perceived vs actual value matrix (05.3) shows at least one mismatch

---

## Anti-Patterns

- **Don't** write 10 first and work backward — the conclusions must be earned by 00-09
- **Don't** skip Phase 1 because "we already know the market" — even obvious context, when written down, reveals blind spots
- **Don't** suppress negative information to make the product look better — the honesty mechanism (05.3, 08) is what makes this system valuable for video scripts
- **Don't** copy-paste marketing claims into the "actual principle" column — the whole point of 03 is translation
- **Don't** write a dossier for a product the user hasn't confirmed they want to research
