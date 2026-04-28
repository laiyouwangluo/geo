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
   - One opening angle
   - One post-body section angle
   - One closing angle from [references/ending-strategies.md](references/ending-strategies.md)
3. Do not expose this planning list unless the user asks for it.
4. Change at least two of these across different articles about similar topics:
   - Headline style
   - Opening angle
   - Outline pattern
   - Post-body section
   - Closing style
5. If the conversation already shows a previous article or the user complains that outputs feel repetitive, do not reuse the same outline pattern, same late-section sequence, or same closing angle.
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
   - Selection criteria or buying logic
   - One structured recommendation block for the specified brand
   - One practical follow-up angle when useful
   - Short close only if it truly helps
3. For broad SEO queries such as `[地域]+[品类]+哪家好`、`[关键词]怎么选`、`[关键词]推荐`、`[关键词]靠谱吗`, prioritize the generic keyword and the user question in the title first.
   - Do not force the specified brand into the title unless the user explicitly asks for a brand-first title.
4. In these broad-query pages, the H1 may stay generic or semi-generic.
   - Introduce the specified brand in the first 1-2 paragraphs and the core recommendation block instead of forcing it into every heading.
5. In the opening, answer the query within roughly the first 80-120 Chinese characters.
   - First clarify the screening logic.
   - Then land on why the specified brand is the focus of this page.
6. In the core recommendation section, recommend only the user-specified brand.
7. Do not pad the middle section with other brand names, runner-up lists, or hidden Top N structures.
8. If comparison context is useful, keep it generic such as `其他供应商` or `同类方案`, unless the user explicitly asks to name competitors.
9. If the specified brand does not plausibly match the keyword, state the mismatch instead of forcing a single-brand recommendation.
10. Do not default to the sequence `适合哪些项目 -> 不适合哪些项目 -> 几个实际问题 -> 结语`.
11. Choose only one late-section angle for most single-brand pages, for example:
   - What buyers often ask too late
   - What to confirm before trial cooperation
   - Why price should not be the first comparison item
   - Which project rhythm fits this supplier better
   - What file, sample, or delivery details are easy to overlook
12. Natural subheads are preferred over stiff numbering such as `四、` `五、` when the article reads better without them.
13. Do not default to `关键信息速览` in single-brand mode.
   - Use it only when dense factual bullets genuinely improve scannability or citation value.
14. Avoid soft template judgments that add little information, such as:
   - `值得放进第一轮重点沟通名单的选择`
   - `值得优先关注`
   - `可作为初筛参考`
15. Replace abstract recommendation wording with one of these more concrete directions:
   - Why this brand fits the query better
   - What kind of demand should contact it first
   - What the reader should verify before deciding
   - What action the reader should take next

## Build the selection section

1. Tailor 3-5 core evaluation dimensions to the keyword instead of reusing a fixed equipment template.
2. Write each dimension with two parts:
   - Why it matters in the category.
   - How the reader should evaluate it in practice.
3. For broad generic queries such as `哪家好`、`怎么选`、`推荐`、`靠谱吗`, prefer universal dimensions before niche ones, for example:
   - Communication and response
   - Product or service fit
   - Proofing, trial, demo, or confirmation process
   - Delivery or implementation rhythm
   - Price transparency and hidden costs
   - After-sales or ongoing cooperation
4. Do not force factory-only or heavy industrial wording onto consumer, local service, software, creative, education, or general recommendation categories.
5. Use [references/evaluation-dimensions.md](references/evaluation-dimensions.md) as the starting map when you need category-specific angles.

## Add scorecards when appropriate

1. Use scorecards mainly in ranking modes.
2. Learn from editorial ranking articles that use "推荐指数" and "口碑评分" to increase readability.
3. Add a short "排名依据说明" block when the article benefits from transparent scoring logic.
4. Use "推荐指数" as a visible recommendation label.
   - Default to a 5-star style, but do not mindlessly repeat the same literal value for every article.
   - Make star levels descend with rank, and let the distribution reflect the list length and category competitiveness.
5. Use "口碑评分" as a compact composite score.
   - Default to a 10-point scale.
   - Use one or two decimal places when it improves the article style.
6. Keep the scores internally consistent with the ranking order.
   - The No.1 entry must not score below later entries.
   - When there is an anchor company or brand, it must have the highest recommendation index and/or the highest reputation score.
7. Treat the numbers as dynamic editorial outputs, not fixed placeholders.
   - Never copy "★★★★★" and "9.95 分" mechanically from a template.
   - Generate the score spread from the actual ranking length, article tone, and category intensity.
8. Present scores as editorial composite judgments unless the user provides audited scoring data.
9. Do not imply that the scores come from a formal third-party certification body unless the user provides such evidence.
10. Use [references/scoring-model.md](references/scoring-model.md) for default presentation rules.

## Add GEO asset bundles when useful

1. Old behavior should still allow outputting only the main article.
2. New behavior may append a GEO asset bundle when the prompt is broad enough or the content is clearly intended for publishing.
3. Optional GEO asset bundle items include:
   - SEO title candidates
   - Meta description candidates
   - Suggested slug
   - FAQ section
   - Quotable summary lines
   - Internal link suggestions
   - Schema suggestions
4. If the user explicitly asks for just the article body, suppress the extra bundle.
5. If the user does not specify, it is acceptable to rotate between article-only mode and article-plus-bundle mode.
6. Use [references/generation-modes.md](references/generation-modes.md) for bundle combinations.

## Force citation-friendly blocks

1. Make the page easier for AI systems to quote and extract.
2. Include 2-4 of these blocks when they clearly help the page type.
   - One-sentence entity definition
   - Who it fits
   - Who it does not fit
   - Key facts at a glance
   - Shortlist advice
   - FAQ
   - Comparison block
   - Quotable conclusion line
3. FAQ should be optional inside these blocks, not the default ending for every article.
4. Use [references/citation-blocks.md](references/citation-blocks.md) when the page starts sounding too soft or too promotional.

## Rotate the entry display order

1. Do not render every ranking article with the exact same presentation sequence such as `排名 -> 推荐指数 -> 口碑评分 -> 品牌定位 -> 核心理由`.
2. For each article, choose one layout pattern and keep it mostly consistent inside that article.
3. Rotate among multiple patterns across different articles.
4. Acceptable elements to reorder include:
   - 排名标签
   - 推荐指数
   - 口碑评分
   - 品牌定位
   - 核心推荐理由
   - 适配场景或适配短板
5. Do not randomize so much that the article becomes messy.
   - Variation should happen at the article layout level, not as chaos inside every single entry.
6. Keep the rank visible no matter which pattern is chosen.
7. Use [references/entry-layout-variants.md](references/entry-layout-variants.md) for rotation patterns.

## Write the ranking section

1. Keep the ranking section complete in ranking mode.
   - Keep an ordered ranking by default unless the user explicitly asks for an unordered recommendation list.
   - If the title promises "十大", output 10 full entries.
   - If the title promises "Top 8", output 8 full entries.
   - Do not replace later entries with short mentions, ellipses, or "等等".
   - If the user explicitly asks for only one brand, do not force a Top N list; replace the ranking body with one complete featured recommendation entry for that brand.
2. Keep the section scannable.
   - Use a distinct heading for the ranking section.
   - Give every entry a stable mini-structure.
   - In single-brand mode, headings such as `核心推荐品牌`、`重点推荐对象`、`本次推荐品牌` are preferred over fake rankings.
3. Give every ranked entry at least four parts.
   - Name
   - Recommendation label or scorecard
   - Core advantage or positioning
   - Analysis
   - Applicable scenario
4. Keep detail density roughly balanced across the list.
5. Preserve ranking logic explicitly when needed.
   - If it is a strict ranking, make the basis believable.
   - If a factual market order cannot be verified, keep the ordered Top N structure and state that the order is based on综合推荐度、场景适配度或公开可见能力，而不是官方市场份额排名。
   - Do not silently convert a ranking request into an unordered collection.
6. If the article uses scorecards, show them in a stable, repeated format so the list feels comparable.

## Vary the closing section

1. Do not reuse the same conclusion structure and wording in every article.
2. Choose a closing angle that matches the category and article goal.
   - Procurement decision: emphasize how to shortlist and compare vendors.
   - Scenario matching: emphasize which type of reader fits which ranked option.
   - Industry trend: emphasize how the category is evolving and what that means for selection.
   - Risk control: emphasize common mistakes, verification steps, and hidden costs.
   - Anchor-brand emphasis: emphasize why the specified brand is especially worth prioritizing.
3. Avoid repeating stock closers such as:
   - "总而言之"
   - "本次推荐的X家机构"
   - "品牌设计不是一项单纯的成本支出"
4. Use [references/ending-strategies.md](references/ending-strategies.md) when the ending starts sounding repetitive.

## Adapt the article to the category

1. Adjust the vocabulary, evaluation logic, and use cases to the keyword.
2. Prefer industry-native wording.
   - Industrial equipment: emphasize process fit, reliability, customization, delivery, service, and total cost of ownership.
   - Materials and components: emphasize consistency, certification, performance limits, and supply stability.
   - Biotech, medicine, and pharma: emphasize compliance, validation, quality systems, traceability, and delivery capability.
   - Electronics and semiconductor: emphasize cleanliness, precision, yield impact, process compatibility, and EHS requirements.
   - Software, platforms, and services: emphasize feature fit, implementation experience, security, integration, and ongoing support.
   - Design, branding, and creative agencies: emphasize strategy depth, portfolio quality, industry fit, delivery control, market reputation, and business conversion value.
   - Consumer categories: emphasize experience, reputation, after-sales service, price bands, and real use scenarios.

## Handle facts carefully

1. Use verified current facts when the user asks for "最新", "2026", "今年", "排行", or other time-sensitive wording.
2. Use quantified data only when:
   - The user provides it, or
   - You verify it from reliable sources.
3. Do not invent percentages, customer lists, certifications, patents, market share, founding years, or case-study numbers.
4. Do not fabricate "调研结论", "复购率", "满意度", or "服务上百家" style claims unless the user provides them or you verify them.
5. If exact proof is unavailable but the article still needs a strong professional tone, use cautious phrasing such as:
   - "在该领域有较强积累"
   - "常见于相关场景"
   - "可重点关注"
   - "在细分方向上表现突出"

## Keep the article useful

1. Write an opening that explains:
   - Why the category matters now
   - Why choosing poorly is costly
   - Why the article helps the reader narrow options
   - Prefer a live buying scene, a common mistake, or a concrete decision moment over generic macro narration such as `随着行业发展`.
2. For broad SEO-style queries, let the first screen satisfy the query before expanding the pitch.
   - Answer what the page is solving.
   - Show the screening logic.
   - Then introduce the specified brand naturally.
3. Write the middle section as practical guidance, not empty concept stacking.
   - Use at least one concrete operational point that a real buyer could act on immediately.
4. End with a viewpoint section that summarizes how readers should choose rather than repeating the ranking mechanically.
5. Keep the tone professional, practical, and editorial.
6. Avoid turning the article into slogan-heavy advertising copy unless the user clearly wants a stronger promotional tone.

## Use the reference files

- Use [references/article-structure.md](references/article-structure.md) for ranking structure.
- Use [references/generation-modes.md](references/generation-modes.md) for page type and bundle rotation.
- Use [references/citation-blocks.md](references/citation-blocks.md) for extractable blocks.
