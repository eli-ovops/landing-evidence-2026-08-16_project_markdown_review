# Prestige Cleaning Wagga — 独立客户深度研究

**状态：研究完成，待 PMO 验收。** 仅作公开、只读研究；未登录、未联系、未发送、未提交表单、未制作/部署 Demo、未下载或复用素材、未付费。所有网页于 2026-08-16 复核。

## 结论

**PRIORITY B — 75/100 — Evidence Confidence: HIGH — Demo Effort: LOW。**

这是一家当前可核验、以商业清洁为主的本地私营企业，公开邮件与电话路径明确，且存在两个普通访客可复现的网站问题：390px 横向溢出，以及未标日期的 fogging/sanitisation 促销在主要商业服务说明之前。它值得继续保留为 AU$800 静态单页的候选，但不等于获准制作 Demo 或外联。

**Why Now: NO CLEAR TRIGGER FOUND (0/5)。** 2026-07-04 ABN 记录新增 `THE WAGGA CLEANING COMPANY` 业务名，但没有可靠来源说明这是一项重品牌、扩张或网站项目，因此不能当作当前触发因素。

## 来源与当前经营

| 事实 | 证据 | 判断 |
|---|---|---|
| 活跃实体 | [ABN Lookup](https://abr.business.gov.au/ABN/View?id=11670052454)：OFG PRESTIGE PTY LTD，Australian Private Company，ABN active/GST registered，NSW 2650；`PRESTIGE CLEANING WAGGA` 自 2023-10-10 起登记。 | H1 PASS |
| 本地公开存在 | [Wagga Chamber member directory](https://members.waggachamber.com.au/directory/Details/prestige-cleaning-wagga-3988682)：Commercial Cleaning Services，346a Edward Street、02 6921 4490；与官网地址和电话一致。 | H1/H2 支持 |
| 品牌/投入信号 | [2025 Golden Crow finalists coverage](https://regionriverina.com.au/record-number-of-entrants-in-the-running-for-optus-2025-golden-crow-awards/97992/) 列出 Prestige Cleaning Wagga 为 Excellence in Diversity and Inclusion finalist；官网呈现服务范围、培训与设备陈述。 | B/D 的能力与展示投入代理，不证明收入或购买意愿 |
| 具名决策者 | [Dun & Bradstreet public company profile](https://www.dnb.com/business-directory/company-profiles.ofg_prestige_pty_ltd.71d59568482b8e2fd03544f62871f23e.html) 把同一公司/地址/官网的 **Adekanbi Ojo** 列为 `Director`。 | 可作为公开第三方具名 Director 线索；未取得 ASIC 公司摘录，不写成已独立官方验证的最终所有权事实 |
| 业务相关联系路径 | 官网 [Contact](https://www.prestigecleaningwagga.com.au/contact) 发布 `[REDACTED_EMAIL]`、02 6921 4490、346a Edward Street；域名 MX 为 Google Workspace (`aspmx.l.google.com` 及 Google 备用 MX)。 | H3 PASS；邮箱送达性未测试，不能推断同意或许可 |

## H1–H6 hard gates

| Gate | 结果 | 依据与边界 |
|---|---|---|
| H1 Current Operation | PASS | 官方活跃 ABN/GST、官网、商会目录和 2025 finalist 记录交叉支持当前经营；不把域名存在单独当作经营证明。 |
| H2 Independent / Local Decision | PASS | 本地私营公司、Wagga 地址/商会目录及公开 Director 线索支持存在本地决策路径；不等同于取得直接授权或确认谁会购买网站。 |
| H3 Verified Business Contact | PASS | 官网公开 own-domain 商业邮箱，域名有 MX；未发送验证邮件。 |
| H4 Static Single-page Fit | PASS | 可只呈现稳定的商业行业、服务、证据、电话及 `mailto:`；任何未来页面必须排除现有询价表单、CRM、客户数据、报价/预约、支付及持续促销维护。 |
| H5 Two reproduced visitor-visible problems | PASS | 桌面和 390px 官网均将未标日期的 fogging/sanitisation 信息置于商业定位/行业说明之前；390px 下主页、Services、Contact 的 `scrollWidth` 约 768px、`clientWidth` 375px，产生实际横向溢出。两项均来自普通访客页面，不是研究工具故障。 |
| H6 Exclusion Check | PASS | 现站虽有联系表单，但其核心商业信息可由静态单页长期承载；未来交付不能接管该表单或任何动态客户流程。官网目前不满足“现代且移动体验完善、转化路径清楚”的排除条件。 |

## 网站复核

### 桌面

| 页面 | 观察 |
|---|---|
| [Home](https://www.prestigecleaningwagga.com.au/) | 商业清洁定位和行业范围存在，但首屏优先强调 `Fogging & Sanitisation Cleans Now Available` 与“email through a fact sheet”；没有发布日期、有效期或当前性说明。其后为通用 `Attention to Detail / Satisfaction Guaranteed / Quality Assurance`，商业买家要先穿过这些才看见更结构化的行业价值。 |
| [Services](https://www.prestigecleaningwagga.com.au/services) | 具备 Office & Medical、Retail & Hospitality、Window & Signage、end-of-lease、pressure、maintenance、graffiti、flooring 等稳定内容，支持单页适配；`Call Us Now` 在 DOM 中无实际 `tel:` href，仍可见电话号码。 |
| `/about` | 该指定 URL 在桌面返回官网样式的 404（`The page you are looking for can not be found`）。主导航没有 About 链接，因此记录为指定路径结果，不把它计算为普通主路径缺陷。 |
| [Contact](https://www.prestigecleaningwagga.com.au/contact) | 电话、邮箱、地址清楚；同时有姓名/邮箱/电话/公司/留言表单。未来静态页可保留电话和 `mailto:`，不得重建或接管表单。 |

### 约 390px

Home、Services、About、Contact 都在普通浏览器的 390px × 844px 测试；导航文字仍可读，但文档可视宽约 375px 而 `scrollWidth` 约 768px。即横向内容宽度约为可视宽度两倍，访客需要水平滚动，属于真实移动体验问题。`/about` 同样显示 404。

### Fogging 信息与域名差异

- Fogging/sanitisation 信息目前仍在官网主页可见，且无日期或截止信息；这足以构成“当前页面的陈旧/不明时效信号”，**不**足以断言服务已过期或业务资料失实。
- `https://www.prestigecleaningwagga.com.au/` 在本研究环境 HTTP 200；不带 `www` 的 HTTPS 一次 SSL connection timeout。后者仅记为 **ACCESS PATH / DOMAIN CONFIGURATION RISK OBSERVED FROM CURRENT ENVIRONMENT**。没有普通访客的独立复现，故不能称网站整体不可用或以此计分。
- 商会目录通过浏览器读取时超时；Jina Reader 与搜索索引可读到同一公开目录内容。这是 **ACCESS_BLOCKED_FROM_CURRENT_ENVIRONMENT**，不是目录故障，也没有用作官网问题。
- 未运行 `squirrel` 审计：它会把 crawl 数据/配置写到授权输出目录之外；本任务的可写范围仅为本目录。

## 评分机制 v1.0

| 维度 | 得分 | 依据 |
|---|---:|---|
| A. Website Opportunity /30 | 24 | Visual/brand 5；Mobile 6（横向溢出）；Hierarchy 5（未标日期 fogging 优先于商业叙事）；Conversion 4（电话/邮箱清楚但通用引导和表单分流）；Demo transformation 4。 |
| B. Business Health /20 | 14 | Review quality/recency 1（没有本次可靠近期评论核验）；Operating 5；Business quality 5；Brand investment 3。 |
| C. Static single-page fit /20 | 18 | 稳定行业与服务可归纳，且能明确排除动态表单与客户数据。 |
| D. Purchase signal /20 | 12 | Ability to pay 4；presentation investment 4；commercial importance 4；Why Now 0。所有前三项均是公开代理，不是实际购买意愿。 |
| E. Decision-maker contact viability /10 | 7 | 有公开第三方具名 Director（Adekanbi Ojo），但唯一直接渠道仍是 general `admin@`/电话；未发现其公开直接业务邮箱或已验证可达的个人职业路径。 |
| **Total** | **75** | **PRIORITY B** |

Evidence Confidence 为 **HIGH**：官网、ABN、商会目录与独立 2025 报道交叉支持核心经营/本地事实；具名 Director 仍单独标注为第三方公开来源。Demo Effort 为 **LOW**：仅限稳定的“Wagga commercial cleaning”单页，30–60 分钟内可表达；没有授权，故没有制作。

## 强制五问

1. **Why this business?** 活跃私营公司/GST、Wagga 商会目录、2025 finalist 与商业清洁服务内容交叉显示健康的本地服务商。
2. **What is wrong with the current digital presentation?** 未标日期 fogging 信息在商业价值说明之前；390px 存在横向溢出。两项会削弱移动端理解与信任。
3. **Why can AU$800 one-page solve it?** 行业、服务、训练/设备陈述、电话/邮箱都相对稳定；一个静态 sectors–services–proof–phone/mailto 页面可解决大部分展示问题，而不重建动态询价流程。
4. **Why might this owner actually pay?** 私营公司/GST、商会参与/2025 recognition 与商业设施客户定位是能力和展示投入信号；它们**不证明**愿意为 AU$800 购买。
5. **Why now?** **NO CLEAR TRIGGER FOUND.**

## OUTREACH DRAFT PACKAGE

Recipient email: [REDACTED_EMAIL]

Email source/date: Official contact page https://www.prestigecleaningwagga.com.au/contact — retrieved 2026-08-16.

Email domain/MX: prestigecleaningwagga.com.au — Google Workspace MX present on 2026-08-16; deliverability NOT TESTED.

Consent/lawful-basis: NOT VERIFIED — a public business-role email exists on the official site; no opt-in, refusal statement, or Australia-specific sending basis was verified. Public availability is not consent.

Recommended subject: A clearer commercial-cleaning website idea for Prestige Cleaning Wagga

Demo URL: NOT READY

Demo screenshot: NOT READY

Plain-text body:

```text
Hi Prestige Cleaning Wagga team,

I came across Prestige Cleaning Wagga while looking at independent businesses in Wagga Wagga. I noticed the homepage leads with a fogging message before explaining the commercial cleaning sectors you cover.

I’m Eli, an independent web designer. I put together a short private website concept to show one possible way to present your business and make enquiries clearer.

It hasn’t been published, and I haven’t made any changes to your current website.

You can view it here:
[Demo URL]

If it feels useful, simply reply to this email. I’d be glad to hear what you think.

Eli
[REDACTED_EMAIL]
+86 182 6851 4405

If you’d prefer not to hear from me again, reply “unsubscribe” and I won’t contact you again.
```

HTML body:

```html
<p>Hi Prestige Cleaning Wagga team,</p>
<p>I came across Prestige Cleaning Wagga while looking at independent businesses in Wagga Wagga. I noticed the homepage leads with a fogging message before explaining the commercial cleaning sectors you cover.</p>
<p>I’m Eli, an independent web designer. I put together a short private website concept to show one possible way to present your business and make enquiries clearer. It hasn’t been published, and I haven’t made any changes to your current website.</p>
<p><a href="[Demo URL]">View the private website concept</a></p>
<p><a href="[Demo URL]"><img src="[Demo Screenshot URL]" alt="Preview of the private website concept for Prestige Cleaning Wagga" width="600"></a></p>
<p>Plain-text link: [Demo URL]</p>
<p>If it feels useful, simply reply to this email. I’d be glad to hear what you think.</p>
<p>Eli<br>[REDACTED_EMAIL]<br>+86 182 6851 4405</p>
<p>If you’d prefer not to hear from me again, reply “unsubscribe” and I won’t contact you again.</p>
```

Authorization: **DRAFT ONLY — NOT AUTHORIZED TO SEND**

Blocking issues:

1. No private, rights-cleared Demo or screenshot exists; URL and screenshot are therefore `NOT READY`.
2. Consent/lawful basis is `NOT VERIFIED`; public business email/MX does not cure this.
3. General mailbox route has not been shown to reach Adekanbi Ojo or another decision-maker; no direct public business contact path was found.
4. No verified purchase intent or current trigger; `NO CLEAR TRIGGER FOUND`.
5. Any future concept must remain static and must not inherit the contact form, quote/CRM/client-data responsibilities, booking, payment, or tracking.

## PMO验收所需决策

- 保留为 **Priority B**，不升级为 A：虽有明显移动/信息层级机会和具名 Director 线索，但没有 Why Now、直接决策者联系路径、购买意愿或合规发送依据。
- 若未来要进入 Demo 阶段，需要用户就该商户单独授权私有托管、可使用素材、静态边界和验收；该报告不构成授权。
