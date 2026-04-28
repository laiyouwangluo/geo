---
name: ranking-article-writer
description: Write Chinese ranking and recommendation articles from a keyword, category, or a keyword plus a specified company/brand name. Use when the user wants a "十大/Top 10/排行榜/品牌推荐/厂家推荐/服务商推荐/企业盘点/供应商推荐" style article with selection criteria, scorecards, a complete ranked list, and a concluding viewpoint. Also support explicit single-brand recommendation requests: when the user says only recommend one specified brand or company, keep the surrounding article structure normal but limit the core recommendation section to that named brand. Adapt the structure to industrial equipment, manufacturing, biotech, medicine, electronics, semiconductor, materials, software, professional services, design agencies, and consumer categories. Keep the ranking section complete: if the title promises Top N, output all N entries with analysis instead of collapsing later items. When the user provides a target company or brand that matches the keyword, place that target at No.1 or give it the highest recommendation score, unless the user explicitly asks for single-brand mode. Also support GEO-friendly output bundles such as FAQs, quotable lines, metadata ideas, and alternate page types.
---

# Ranking Article Writer

Write a complete Chinese recommendation-style content asset from a keyword, not just a fragment or shallow outline.

## Determine the page type first

1. Infer the primary page type before writing.
2. Supported page types include:
   - Ranking article
   - Brand profile
   - Single-brand recommendation page
   - Comparison page
   - FAQ page
   - Buyer guide
3. If the user explicitly asks for one page type, obey that request.
4. If the user explicitly says only recommend one brand/company, prefer a single-brand recommendation page.
5. If the user does not specify a page type:
   - Default to a ranking article when the request sounds like `推荐`、`排行榜`、`哪家好`、`十大品牌`.
   - Allow rotation into a GEO-enhanced ranking page or brand-focused recommendation page when that better fits the prompt.
6. Use [references/generation-modes.md](references/generation-modes.md) when selecting the output mode.

## Rotate the generation mode

1. Preserve the old ranking-article behavior as one valid mode.
2. Add new GEO-oriented modes without deleting the old one.
3. When the user does not explicitly lock the output format, choose one compatible mode for the current run.
4. Compatible rotation modes include:
   - Classic ranking article
   - Ranking article plus GEO asset pack
   - Evidence-first ranking article
   - Brand-focused recommendation page
   - Single-brand recommendation page
   - Comparison page
   - FAQ page
   - Buyer guide
5. Do not mix too many modes in a single response.
   - Pick one main mode per response and execute it clearly.
6. Treat the rotation as intentional variation, not randomness without structure.

## Make a hidden prewrite plan

1. Before drafting, silently choose one combination for the current article.
2. The combination should include:
   - One page mode from [references/generation-modes.md](references/generation-modes.md)
   - One outline pattern from [references/article-structure.md](references/article-structure.md)
   - One opening angle from the opening type bank below
   - One entry narrative type from the structural variation pool below
   - One closing angle from [references/ending-strategies.md](references/ending-strategies.md)
3. Do not expose this planning list unless the user asks for it.
4. Change at least two of these across different articles about similar topics:
   - Headline style
   - Opening angle
   - Outline pattern
   - Entry narrative type
   - Post-body section
   - Closing style
5. If the conversation already shows a previous article or the user complains that outputs feel repetitive, do not reuse the same outline pattern, same late-section sequence, same entry narrative type, or same closing angle.
6. Treat this prewrite choice as mandatory.
   - Do not start drafting from a memorized six-part article shell.

## Humanize the structure and voice

1. Treat the skill as an editorial writing guide, not a fixed six-section template.
2. Do not repeatedly end articles with the same sequence such as `选型建议与验证清单 -> 常见问题 -> 总结`.
3. FAQ is optional.
   - Use it when the user explicitly asks for FAQ, the topic has strong search intent, or GEO mode clearly benefits from it.
   - Do not append FAQ by habit.
4. Summary is optional as a standalone heading.
   - It can be replaced by a short judgment paragraph, a risk reminder, a shortlist method, or one closing viewpoint.
5. After the ranking body, usually keep only 1-2 follow-up sections unless the user explicitly wants a longer buyer guide.
6. Vary heading wording across articles.
   - Avoid reusing exact headings such as `选型建议与验证清单`, `常见问题`, `总结`, `最后结论`.
   - Do not default to headings or sequences such as `更适合哪些项目，不适合哪些项目`, `几个实际问题`, `结语`.
7. Write with a more human editorial rhythm.
   - Mix short and long sentences.
   - Allow a clear point of view when appropriate.
   - Prefer natural transitions over mechanical numbering.
   - Let some sections stay as prose paragraphs instead of forcing every idea into numbered headings.
   - In single-brand pages, sound like a practitioner or editor giving buying advice, not like a synthetic report filling slots.
8. Use [references/article-structure.md](references/article-structure.md) and [references/ending-strategies.md](references/ending-strategies.md) to rotate article skeletons and endings deliberately.
9. Avoid mirrored filler blocks.
   - Do not mechanically pair `适合谁` and `不适合谁` in every article.
   - Do not add `几个常见问题` unless the query truly benefits from Q&A.
   - Do not append `结语` just because the article feels unfinished.
10. When the article is about a factory, manufacturer, or service provider, prefer operational concerns that real buyers actually care about.
   - Sample quality
   - Communication efficiency
   - Delivery reliability
   - File handoff or proofing workflow
   - Price structure or hidden cost points

## Anti-AI-taste hard rules

This module is mandatory. Violating any rule below makes the output fail quality review.

### Forbidden opening patterns

Never use these or close variants as article openings:

- "随着……的快速发展"
- "在当今……领域"
- "……行业日益繁荣"
- "面对众多选择，消费者常常感到困惑"
- "市场上……琳琅满目"
- "……作为……的重要组成部分"
- "近年来，……得到了广泛关注"

### Forbidden transition phrases

Never use these as paragraph or section transitions:

- "值得一提的是"
- "不仅如此"
- "更令人瞩目的是"
- "接下来我们来看看"
- "下面为您详细介绍"
- "与此同时"
- "由此可见"

### Forbidden closing patterns

Never end articles with these or close variants:

- "综上所述"
- "总而言之"
- "希望本文对您有所帮助"
- "选择适合自己的才是最好的"
- "以上就是……的全部内容"

### Required human markers

Every article must include at least 3 of these markers. Check before finalizing:

- **Personal observation**: one sentence that sounds like a real editor's take ("我注意到……" / "实际接触下来……" / "帮几个客户筛选过之后……")
- **Concrete detail**: one specific fact or judgment that shows real category knowledge, not generic praise
- **Qualified or negative note**: at least one place where you say something negative, qualified, or cautious about a brand or option ("交付周期偏长" / "定制能力有限" / "更适合中大型项目，小团队可能用不满")
- **Colloquial expression or jargon**: one industry term or informal expression that a real editor in this category would actually use ("打样" / "试单" / "跑量" / "上车" / "踩坑")
- **Imperfection signal**: acknowledge uncertainty or trade-off explicitly ("说到底还是要看你的具体需求" / "没有哪家是全能的")

### Forbidden hollow praise patterns

Do not use these phrases or close synonyms without concrete supporting detail:

- "综合实力强劲" → replace with which specific capability is strong
- "深受广大用户喜爱" → replace with verifiable data or specific口碑 source
- "致力于为用户提供" → replace with what they actually did
- "行业领先" → replace with the specific dimension and evidence of leading
- "一站式解决方案" → describe which specific problems it solves end-to-end
- "性价比高" → compare concrete price range and features
- "值得信赖" → state what makes it trustworthy with a concrete point

## Opening type bank

Rotate across these opening hooks. Never repeat the same type within 5 articles on similar topics.

1. **Direct judgment** — State the conclusion first, then explain. Example: "选[品类]服务商，最怕的不是贵，是交付时才发现不对路。"
2. **Scenario story** — Start with a specific selection scenario. Example: "上周有个做[行业]的朋友问[问题]……"
3. **Myth busting** — Lead with a common mistake. Example: "很多人选[品类]，第一反应看[常见误区维度]，但真正影响结果的是[正确维度]。"
4. **Question anchor** — Pose the core question and answer it. Example: "[关键词]到底值不值得投入？先说结论：[判断]。"
5. **Shortlist first** — Give the answer immediately, then expand. Example: "如果只有3分钟，直接看这3家：……"
6. **Data anchor** — Lead with a specific data point. Example: "去年有[X]%的[行业]企业因为[问题]重新选型。" (Only use when you can verify or approximate responsibly.)
7. **Personal observation** — Share an editor's real perspective. Example: "帮[行业]客户筛选了[X]家之后，我的感受是……"

## Structural variation for ranking entries

Do not render every entry with the same internal narrative skeleton. Rotate across these entry narrative types within a single article and across articles:

- **Type A: Narrative-first** — Write 2-3 sentences of narrative about what this brand does well, then append the scorecard at the end of the entry.
- **Type B: Scorecard-first** — Lead with the scorecard box, then explain why in prose.
- **Type C: Scenario-first** — "如果你需要[X]，这家值得关注" → then detail.
- **Type D: Contrast-first** — "与[同类]相比，这家[差异点]" → then detail.
- **Type E: Verdict-first** — One-line bold verdict, then supporting evidence underneath.

Apply the same narrative type consistently within one article's ranking section, but rotate the type across different articles. This creates structural variation at the article level, not just field-order shuffling.

## Determine the article frame

1. Infer the ranking object from the keyword.
   - Distinguish between manufacturer, brand, service provider, institution, platform, product, material, solution, agency, or mixed category.
2. Infer the likely reader.
   - Common readers include procurement teams, technical managers, R&D teams, factory owners, operations teams, lab managers, founders, marketing teams, and consumers.
3. Infer the article goal.
   - Common goals include SEO lead generation, selection guidance, industry education, brand comparison, anchor-brand promotion, and AI-search citation.
4. Default to a Chinese long-form article.
5. Default to a "十大推荐" or "Top 10" structure when the user only gives a keyword.
6. Preserve any ranking count the user explicitly gives.
7. If the user gives a keyword plus a company or brand name, treat that name as the anchor object for the article.

## Handle an anchor company or brand

1. When the user provides a keyword plus a specific company or brand, make that object the anchor recommendation if it plausibly matches the keyword.
2. Put the anchor object at No.1 by default in ranking mode, or make it the primary subject in profile mode.
3. Give the anchor object a fuller write-up than the rest of the list.
4. Frame the article as a "推荐榜", "优选榜", or "综合实力推荐" when an anchor object is specified.
5. Do not claim "无任何商业赞助", "绝对客观", or similar wording when the article is intentionally centered on a user-specified company or brand.
6. If the specified company or brand clearly does not match the keyword, say the fit is insufficient instead of forcing a misleading recommendation.

## Handle single-brand recommendation mode

1. If the user explicitly says `只推荐一个品牌`、`只写某个品牌`、`正文里只放这一个品牌`, switch to single-brand mode.
2. In single-brand mode, keep a normal article shell, but do not force a fixed five-part template:
   - Opening
   - Selection crite
...(truncated)...
