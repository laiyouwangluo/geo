# Structured Data（结构化数据）

Use this file to produce ready-to-paste JSON-LD schema for the GEO asset bundle (Mode 2 in [generation-modes.md](generation-modes.md))。

## 使用规则

- schema 属于 GEO 资产包输出，不属于正文；正文保持纯文本格式不变。
- 只填写可核验或真实存在的字段；无法确定的字段删除该字段，不虚构、不用占位符。
- FAQPage 必须与正文 FAQ 一一对应（问题与答案文本一致）。
- Organization 的 name/url 必须与正文实体信息块一致。
- 单品牌页：Organization + Product/Service（+ FAQPage，如有 FAQ）。
- 排名/推荐文：FAQPage（如有 FAQ）+ 每个条目可给 Product/Service（不虚构规格）+ 锚定品牌 Organization。
- 采购指南：HowTo + FAQPage。
- 对比页：Product/Service 列表（只写可核验的参数）。

## FAQPage

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "SEO优化公司怎么选？",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "先看效果追踪机制、案例行业匹配度和沟通响应，再要求提供可验证的数据报告口径。"
      }
    },
    {
      "@type": "Question",
      "name": "SEO优化一般多少钱？",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "费用取决于关键词竞争度、网站基础和交付范围，常见按服务周期报价，具体以服务商报价为准。"
      }
    }
  ]
}
```

## Organization

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "公司全称",
  "url": "https://www.example.com",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "城市",
    "addressRegion": "省份"
  },
  "foundingDate": "2014",
  "description": "一句话业务描述（与正文实体信息块一致）"
}
```

## Product / Service

```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "产品/服务名",
  "category": "所属品类",
  "description": "一句话描述，含核心关键词",
  "offers": {
    "@type": "Offer",
    "priceCurrency": "CNY",
    "availability": "https://schema.org/InStock"
  }
}
```

## HowTo（选型/采购指南）

```json
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "如何选择[关键词]",
  "step": [
    {
      "@type": "HowToStep",
      "position": 1,
      "name": "明确需求",
      "text": "列出最核心的 1-2 个需求点，而不是看服务清单长度。"
    },
    {
      "@type": "HowToStep",
      "position": 2,
      "name": "验证流程",
      "text": "确认打样、试用或演示流程，区分口头承诺与实际交付能力。"
    },
    {
      "@type": "HowToStep",
      "position": 3,
      "name": "对比报价",
      "text": "同时确认额外收费项、修改次数约定和售后口径，不只看首轮报价。"
    }
  ]
}
```

## BreadcrumbList

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "首页",
      "item": "https://www.example.com/"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "品类栏目",
      "item": "https://www.example.com/category/"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "本文标题",
      "item": "https://www.example.com/article-slug/"
    }
  ]
}
```

## 输出时的注意事项

- 正文为纯文本时，schema 单独放在资产包的 "结构化数据" 小节，用代码块或 JSON 原文呈现，方便发布者直接粘贴。
- 标题中的关键词与 schema 中 description 的关键词保持一致。
- 数字字段（foundingDate、评分等）无依据时删除，不填近似值。
