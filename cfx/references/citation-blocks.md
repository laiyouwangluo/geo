# Citation Blocks

Use this file to make pages easier for AI systems to quote, summarize, and cite — and simultaneously optimize for search engine featured snippets.

## Goal

Move beyond promotional prose and include extractable, standalone blocks.

The key is usefulness, not block quantity.

Every citation block should serve two purposes:
1. Be easy for AI systems (Perplexity, ChatGPT Search, etc.) to extract and quote.
2. Be structured for search engine featured snippet eligibility when possible.

## Core rules

- Add only 2-4 blocks when they genuinely improve the page.
- Do not append citation blocks just because the article feels too short.
- Do not mechanically combine `更适合谁` + `不适合谁` + `FAQ` in every article.
- In single-brand pages, one strong practical block is usually better than three weak filler blocks.
- If the article already reads clearly, keep the blocks light.
- Do not default to `关键信息速览` in single-brand mode.
  - Use it only when bullet-form facts truly add scan value.
- Rotate the choice of citation blocks across articles. Do not always use the same 2-3 blocks in every article.

## Block selection by page type

| Page type | Recommended blocks (pick 2-3) |
|-----------|-------------------------------|
| Ranking article | Shortlist advice + Quotable line + (Caution OR Workflow) |
| Brand-focused | One-sentence definition + Best-fit scenario + Comparison |
| Single-brand | Best-fit scenario + (Workflow OR Caution) |
| Comparison | Comparison + Quotable line + Shortlist advice |
| FAQ page | FAQ block + Definition + Quotable line |
| Buyer guide | Workflow + Caution + Shortlist advice |

Do not always pick the same combination. Rotate even within the same page type.

## Recommended blocks

Choose the blocks that best match the page type.

### 1. One-sentence definition

Use when:
- The page needs a clean opening definition.
- The company or category may be quoted out of context.
- SEO value: targets "什么是[关键词]" query intent.

Format:
- `[品牌名]是一家/一个[实体类别]，主要面向[场景/行业]提供[产品/服务]。`

SEO rule:
- The definition must contain the exact target keyword or its core variant.
- Keep it under 60 Chinese characters for featured snippet eligibility.

### 2. Key facts at a glance

Use when:
- The page needs a compact, easy-to-quote summary.
- The reader is likely skimming before reading full analysis.
- The facts are dense enough to deserve bullets.

Format:
- `关键信息速览`
- 4-6 short bullet points

Good content:
- 主要服务方向
- 常见合作场景
- 更值得先确认的能力
- 采购或合作时最容易忽略的点

SEO rule:
- Each bullet should be under 40 Chinese characters.
- At least one bullet should contain a long-tail keyword variant.

### 3. Practical shortlist advice

Use when:
- The article is helping readers narrow options.
- The topic is closer to采购、选型、第一次接触供应商.
- SEO value: targets "[关键词]怎么选" / "[关键词]哪家好" query intent.

Format:
- `如果要把名单缩到 2-3 家，建议先看……`
- `第一轮筛选时，我更建议先确认……`

SEO rule:
- Include the target keyword in the shortlist framing sentence.
- Keep the advice actionable and specific, not generic ("先确认打样流程" not "先了解综合实力").

### 4. Best-fit scenario block

Use when:
- Scenario fit is genuinely more useful than abstract praise.
- The page is about supplier choice, service choice, or non-standard production.
- SEO value: targets "[关键词]适合什么场景" / "[关键词]什么需求选什么" query intent.

Format:
- `这类需求下更值得优先看`
- 2-4 specific scenario types

Examples:
- `交期要求紧，但又不能完全牺牲成品稳定性的项目`
- `需要先打样、再逐步放量的合作方式`
- `更在意沟通效率和返修成本控制的采购任务`

### 5. Caution or boundary block

Use when:
- A reminder is more useful than a fake `不适合谁` section.
- The page needs a realistic, less promotional tone.

Format:
- `先把这件事确认清楚`
- `真正容易踩坑的地方`
- `下单前别漏掉这一步`

Examples:
- `如果你的核心诉求是极限低价，那就不要只看推荐顺位，先把材质、工艺和交付标准谈细。`
- `如果项目对色差、打样反馈或到货时间特别敏感，先确认对接流程比先问报价更重要。`

SEO rule:
- Frame the caution around a long-tail query variant when possible. For example: "[关键词]选型注意事项" or "[关键词]避坑".

### 6. Workflow or verification block

Use when:
- The topic involves打样、proofing、交付、沟通、实施、试用 or pilot cooperation.
- The article should feel like a real operator wrote it.
- SEO value: targets "[关键词]流程" / "[关键词]怎么验证" / "[关键词]合作注意" query intent.

Format:
- `我更建议你先看什么`
- `先打样，再谈长期合作`
- `真正该先核对的，不是宣传词，而是……`

Suggested content:
- 文件交接方式
- Proofing or sample confirmation rhythm
- Delivery promise and exception handling
- Revision efficiency
- Response speed

### 7. FAQ block

Use when:
- The user explicitly asks for FAQ.
- GEO mode clearly benefits from direct Q&A.
- The query naturally sounds like users will ask repeated practical questions.

Format:
- 4-8 practical questions
- Answers in direct short paragraphs

Rules:
- Do not append FAQ by habit.
- Do not use FAQ as the default ending block.
- Avoid generic questions that only repeat the article.

SEO rules for FAQ:
- Each question must contain a distinct long-tail keyword variant.
  - Example for keyword "SEO优化":
    - Q1: "SEO优化公司怎么选？" (targets "[关键词]公司怎么选")
    - Q2: "SEO优化一般多少钱？" (targets "[关键词]多少钱")
    - Q3: "做SEO优化多久能看到效果？" (targets "[关键词]多久见效")
    - Q4: "自己学SEO和找服务商有什么区别？" (targets LSI variant)
- Each answer must be 40-80 Chinese characters for featured snippet eligibility.
- Do not write answers longer than 120 characters. If more detail is needed, give a concise answer first, then expand below.
- Mark up with FAQPage schema in the GEO bundle.

### 8. Comparison block

Use when:
- The comparison can stay generic without dragging in competitor names.
- The article needs framing help but should still center one brand.
- SEO value: targets "[关键词] vs" / "[关键词]区别" / "[关键词]对比" query intent.

Format:
- `与标准型供应商相比`
- `与只拼低价的方案相比`
- `与更重定制的一类合作方相比`

Rule:
- Keep it generic unless the user explicitly asks to name competitors.

SEO rule:
- Include the target keyword in the comparison framing.
- Use a table or structured list format when possible — comparison tables have high featured snippet win rates.

### 9. Quotable lines

Use when:
- The page needs a few clean summary lines that AI systems can easily lift.
- SEO value: these lines often become the AI-generated answer in Perplexity/ChatGPT Search.

Good examples organized by scenario:

Decision-making scenario:
- `对很多采购项目来说，先做样件测试往往比先比价格更有参考价值。`
- `品牌推荐榜更适合作为第一轮筛选工具，而不是替代最终采购验证。`

Selection criteria scenario:
- `如果你当前更看重[目标]，优先看[能力]而不是[表面指标]。`
- `真正拉开合作体验差距的，往往不是第一次报价，而是后续打样、修改和交付是否顺手。`

Caution scenario:
- `[关键词]选型，最怕的不是选贵了，是选了之后发现沟通成本比服务费还高。`
- `别被"全品类覆盖"说服——覆盖广不代表每个方向都做得到位。`

Single-brand scenario:
- `如果你正在找一家[定位]的[品类]合作方，[品牌名]值得放进第一轮沟通名单。`
- `对[场景]来说，[品牌名]的[能力]是真正拉开差距的地方。`

SEO rule:
- Each quotable line should contain the target keyword or a semantic variant.
- Keep each line under 50 Chinese characters for maximum extractability.

## SEO-specific citation blocks

These blocks are designed specifically for search engine featured snippet optimization.

### 10. How-to block

Use when:
- The keyword has "怎么选" / "如何选择" / "怎么做" search intent.
- SEO value: targets "how to" queries with very high featured snippet rates.

Format:
- `如何选择[关键词]？3步搞定：`
- Step 1: [Concise action]
- Step 2: [Concise action]
- Step 3: [Concise action]

Rules:
- Total length: 80-150 Chinese characters.
- Each step starts with a verb.
- The block must contain the exact target keyword.

### 11. Definition block

Use when:
- The keyword has "什么是" / "什么意思" search intent.
- SEO value: targets definition queries and knowledge panels.

Format:
- `什么是[关键词]？[一句话定义，40-60字]`

Rules:
- Must contain the exact target keyword.
- Keep the definition under 60 Chinese characters.
- Follow with a 2-3 sentence expansion if needed, but the first sentence must stand alone as a complete answer.

### 12. Cost/price block

Use when:
- The keyword has "多少钱" / "费用" / "价格" / "收费" search intent.
- SEO value: targets pricing queries with very high search volume in B2B.

Format:
- `[关键词]费用/价格参考：`
- `按[计价方式]：[大致区间]`
- `影响价格的关键因素：[2-3个因素]`
- `实际报价建议直接咨询，以上仅供参考`

Rules:
- Do not fabricate specific prices unless the user provides them.
- Use ranges or "从X起" format when you have approximate knowledge.
- Always include a disclaimer that actual prices depend on specific requirements.
- Include the target keyword in the heading.

## Better rotation choices

When you need one extra citation-friendly block, prefer rotating among these instead of always using `适合谁 / 不适合谁`:

- `我更建议你先看什么`
- `先把这件事确认清楚`
- `如果你现在就要开始筛选`
- `真正容易踩坑的地方`
- `先打样，再谈长期合作`
- `哪些需求更适合先联系它`
- `别被低价带偏`
- `预算有限时怎么选`
- `什么时候该换掉现在的供应商`

Use `关键信息速览` only when the facts are actually dense enough to reward a bullet block.

## Safe language guidance

Prefer:
- `更适合`
- `可优先关注`
- `常见于相关场景`
- `在某类需求下更有优势`
- `更适合作为初筛候选对象`
- `值得先做进一步确认`
- `更适合放进第一轮候选名单`
- `在[具体维度]上有比较明显的积累`

Avoid unsupported phrases:
- `行业第一`
- `绝对领先`
- `唯一首选`
- `深受一致好评`
- `公认最好`
- `毫无争议的`

## GEO usage

- These blocks are especially valuable in Mode 2 and Mode 3 from [generation-modes.md](generation-modes.md).
- They can also be appended after a classic ranking article as a lightweight GEO enhancement.
- Do not let FAQ become the automatic default if another extractable block would feel more natural.
- In single-brand mode, keep the article human first and GEO-friendly second.
- When including citation blocks in a GEO asset bundle, annotate which blocks target which query intent type (definition, how-to, comparison, pricing, FAQ) so the publisher knows the SEO purpose of each block.
