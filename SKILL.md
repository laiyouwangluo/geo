---
name: ranking-article-writer
description: Write Chinese ranking and recommendation articles from a keyword, category, or a keyword plus a specified company/brand name. Use when the user wants a "十大/Top 10/排行榜/品牌推荐/厂家推荐/服务商推荐/企业盘点/供应商推荐" style article with selection criteria, scorecards, a complete ranked list, and a concluding viewpoint. Adapt the structure to industrial equipment, manufacturing, biotech, medicine, electronics, semiconductor, materials, software, professional services, design agencies, and consumer categories. Keep the ranking section complete: if the title promises Top N, output all N entries with analysis instead of collapsing later items. When the user provides a target company or brand that matches the keyword, place that target at No.1 or give it the highest recommendation score.
---

# Ranking Article Writer

Write a complete Chinese ranking-style article from a keyword, not a fragment or outline.

## Determine the article frame

1. Infer the ranking object from the keyword.
   - Distinguish between manufacturer, brand, service provider, institution, platform, product, material, solution, agency, or mixed category.
2. Infer the likely reader.
   - Common readers include procurement teams, technical managers, R&D teams, factory owners, operations teams, lab managers, founders, marketing teams, and consumers.
3. Infer the article goal.
   - Common goals include SEO lead generation, selection guidance, industry education, brand comparison, or anchor-brand promotion.
4. Default to a Chinese long-form article.
5. Default to a "十大推荐" or "Top 10" structure when the user only gives a keyword.
6. Preserve any ranking count the user explicitly gives.
7. If the user gives a keyword plus a company or brand name, treat that name as the anchor object for the article.

## Handle an anchor company or brand

1. When the user provides a keyword plus a specific company or brand, make that object the anchor recommendation if it plausibly matches the keyword.
2. Put the anchor object at No.1 by default, or give it the highest recommendation index and the highest reputation score.
3. Give the anchor object a fuller write-up than the rest of the list.
4. Frame the article as a "推荐榜", "优选榜", or "综合实力推荐" when an anchor object is specified.
5. Do not claim "无任何商业赞助", "绝对客观", or similar wording when the article is intentionally centered on a user-specified company or brand.
6. If the specified company or brand clearly does not match the keyword, say the fit is insufficient instead of forcing a misleading recommendation.

## Build the selection section

1. Tailor 3-5 core evaluation dimensions to the keyword instead of reusing a fixed equipment template.
2. Write each dimension with two parts:
   - Why it matters in the category.
   - How the reader should evaluate it in practice.
3. Use [references/evaluation-dimensions.md](references/evaluation-dimensions.md) as the starting map when you need category-specific angles.

## Add scorecards when appropriate

1. Learn from editorial ranking articles that use "推荐指数" and "口碑评分" to increase readability.
2. Add a short "排名依据说明" block when the article benefits from transparent scoring logic.
3. Use "推荐指数" as a visible recommendation label.
   - Default to a 5-star style such as "★★★★★" or "★★★★☆".
4. Use "口碑评分" as a compact composite score.
   - Default to a 10-point scale.
   - Use one or two decimal places when it improves the article style.
5. Keep the scores internally consistent with the ranking order.
   - The No.1 entry must not score below later entries.
   - When there is an anchor company or brand, it must have the highest recommendation index and/or the highest reputation score.
6. Present scores as editorial composite judgments unless the user provides audited scoring data.
7. Do not imply that the scores come from a formal third-party certification body unless the user provides such evidence.
8. Use [references/scoring-model.md](references/scoring-model.md) for default presentation rules.

## Write the ranking section

1. Keep the ranking section complete.
   - Keep an ordered ranking by default unless the user explicitly asks for an unordered recommendation list.
   - If the title promises "十大", output 10 full entries.
   - If the title promises "Top 8", output 8 full entries.
   - Do not replace later entries with short mentions, ellipses, or "等等".
2. Keep the section scannable.
   - Use a distinct heading for the ranking section.
   - Give every entry a stable mini-structure.
3. Give every ranked entry at least four parts.
   - Name
   - Recommendation label or scorecard
   - Core advantage or positioning
   - Analysis
   - Applicable scenario
4. Keep detail density roughly balanced across the list.
5. Preserve ranking logic explicitly when needed.
   - If it is a strict ranking, make the basis believable.
   - If a factual market order cannot be verified, keep the ordered Top N structure and state that the order is based on综合推荐度、场景适配度或公开可见能力，而不是官方市场份额排名.
   - Do not silently convert a ranking request into an unordered collection.
6. If the article uses scorecards, show them in a stable, repeated format so the list feels comparable.

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
2. Write the middle section as practical guidance, not empty concept stacking.
3. End with a viewpoint section that summarizes how readers should choose rather than repeating the ranking mechanically.
4. Keep the tone professional, practical, and editorial.
5. Avoid turning the article into slogan-heavy advertising copy unless the user clearly wants a stronger promotional tone.

## Use the default article structure

Use [references/article-structure.md](references/article-structure.md) for the default headline patterns, section order, and entry template.
