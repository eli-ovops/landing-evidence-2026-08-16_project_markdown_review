# Cairns Pressure Cleaning｜独立客户深度研究

读取/核验日期：2026-08-16（Australia/Brisbane 可能仍为 2026-08-16；本报告统一记录本机读取日）  
范围：公开只读研究、普通浏览器核验；没有登录、联系、发送、提交、填写报价/联系表、上传、下载/复用商户资产、制作 Demo、部署或付费。  
结论状态：**研究完成，待 PMO 验收。**

## 最终决定：ADVANCE TO DEMO

这只表示已满足“进入 AU$800 纯静态单页 **Demo 阶段**”的证据门槛；不表示已获 Demo 制作、素材使用、外联、发送或购买授权。

可证伪条件：若 PMO 或后续授权的 Owner 发现 ABN 24 167 780 390 并非现官网/电话的实际经营主体，或 Ian Roy Fanning 已不再控制该业务，立即降为 **HOLD**；若客户明确说明现有报价流程是唯一有效获客入口且不需要报价前的信息页，也降为 **DROP**。未获任何正向回复/预算信号时，Demo 仍不得被描述为已有订单。

## 1. 第一性原理与红队

| 最小充分前提 | 可被误用的推论 | 本次阻断/证据 | 残余风险 |
| --- | --- | --- | --- |
| 静态页要在报价前独立产生理解和信任价值 | 把静态页伪装成动态报价、预约或上传系统 | 方案只保留电话、mailto、地图和现有 quote 外链；不承接任何客户输入 | 业主可能只依赖电话/Google/报价问卷，认为新页无增量价值 |
| “当前经营/本地决策”须有独立证据 | 用在线官网或 Gmail 推定公司仍接单或某人有权决策 | ABN Lookup 显示同名 business name、活跃 ABN、QLD、Individual/Sole Trader；官网 About 将 owner 写为 Ian | ABR 记录最后更新为 2022；它支持当前注册状态，不直接证明今天有订单或邮箱控制 |
| 网站问题须是普通访客可见 | 用隐藏 DOM、翻译层或工具错误冒充访客问题 | 只采纳普通浏览器可见的促销、路径命名/跨域分流和年份不一致；不把控制台错误列为访客问题 | 页面可用且移动端无溢出，故不能夸大为 HIGH |
| 品牌/支付信号不等于购买意愿 | 把 GST、评价或现有站点当成 AU$800 购买承诺 | 将其仅记为能力/投入代理；购买可能性仍为中低置信度 | 无公开网站预算、采购、扩张或近期营销投入 |

## 2. Website redesign need：MEDIUM

### 普通浏览器复测（桌面与 390px）

| 路径 | 桌面核验 | 390px 核验 | 结论 |
| --- | --- | --- | --- |
| 首页 `/` | 标题、服务概述、电话、`Book Now` 和 `Get Quote` 可见；顶部显示 Christmas 折扣 | `Menu` 的 `aria-expanded` 由 `false` 变为 `true`，服务/Who We Are/Service Areas/Get Quote 可见；宽度 375px、scrollWidth 375px，无横向溢出 | 基本可用，不支持“移动端坏掉” |
| 服务 `/pressure-cleaning/` | 清楚列软洗/水喷洗和 PSI；可到 Contact/Quote | 未见横向溢出（本轮移动只做路径与首屏复核） | 服务说明稳定，可被静态页承载 |
| About `/who-we-are/` | 可见 `owner, Ian`、30+ years、Cairns/Cairns Beaches/Bentley Park 和直接联系 | 该路径可从已展开的移动菜单看到 | 为本地 owner 线索，也显示可静态表达的稳定信息 |
| Contact `/contact-us/` | 可见电话、Gmail 与 Contact 表单；电话/邮箱明确 | 电话与邮箱在首页和 Contact 可见 | 直接联系清楚；未来静态页不能复制该表单 |
| Quote `quote.pressurecleancairns.com.au/or-quote` | 同品牌报价首步，先问 Residential/Commercial，提供电话替代 | 375px、scrollWidth 375px；按钮可见、无横向溢出 | 可用的独立报价流程，不是“跨域坏链” |

浏览器自动注入了中文翻译层；所有判断基于源站可见的英文结构/链接，未把翻译文字作为商户问题。服务页记录到一个主题 JS 控制台 TypeError，但没有观察到对应可见故障，**不作为问题或销售论点**。

### 两项以上真实、可见、可复现的问题

1. **无日期的 Christmas/pensioner 促销（W1）。** 首页及 Contact 等共享页眉普通访客可见：`Ask about our 20% pensioner pre-clean Christmas discount!`；首页正文同时出现 pensioner/mates' rate/pre-sale specials。未见年份、截止日、适用条件或活动页。读取日为 2026-08-16，因此其当前性无法由页面判断。这不是“证明优惠过期”，而是会让非活动期访客怀疑维护状态的可信度风险。
2. **同一询盘意图的路径说明不足（W2）。** `Book Now`/`Call Now` 去站内 Contact，而导航和页脚 `Get Quote` 去 `quote.` 子域；两条路径均可见，但首页没有告诉访客“直接联系”和“进入预筛报价问卷”各适用何种情况。跨域本身合理，问题是报价前缺少预期管理，增加选择摩擦。
3. **可见年份信号相互不一致（W3）。** 主站页脚显示 `Copyright Cairns Pressure Cleaning 2024`，报价子域显示 `Copyright ... 2025`。它不证明业务停业，但与无日期季节促销共同造成维护/可信度疑虑。

**反证：** 移动导航能展开；390px 没有横向溢出；首屏的业务、电话与 CTA 均明确；Quote 首步和电话替代路径可用。因此是 **MEDIUM**，不是 HIGH。

## 3. 经营、本地决策与联系渠道

| 门槛 | 证据（均读取 2026-08-16） | 判断 |
| --- | --- | --- |
| 当前经营（官网来源） | 官网与 quote 页面均可访问，显示一致品牌及电话 `0417 716 874` | 支持，但单独不充分 |
| 当前经营（独立政府来源） | [ABN Lookup — ABN 24 167 780 390](https://abr.business.gov.au/ABN/View?abn=24167780390) 显示 business name `Cairns pressure Cleaning`、ABN **Active from 12 Mar 2020**、主址 QLD 4879、GST registered from 01 Jul 2022 | **通过**当前注册/本地经营主体层；ABR last updated 2022 是残余时效风险 |
| 独立/本地决策 | ABR 显示实体为 **Individual/Sole Trader**、entity name **FANNING, IAN ROY**；官网 [Who We Are](https://pressurecleancairns.com.au/who-we-are/) 写 `owner, Ian` | **通过（公开、交叉一致）**；不推断私人联系方式或法律授权范围 |
| 第三方经营/口碑代理 | [Facilicom 目录](https://facilicom.au/directory/cleaning-services/solar-panel-cleaning/in/queensland/cairns/belvedere) 列同名、电话 `0417 716 874`、4.8 Google rating / 16 reviews | 支持品牌存在；该页没有评论日期，不能作为近期订单证明 |
| 公开业务邮箱 | 官网 [Contact](https://pressurecleancairns.com.au/contact-us/) 与首页 `mailto:` 公开 `[REDACTED_EMAIL]` | **通过公开业务邮箱来源** |
| MX | 2026-08-16 DNS `gmail.com MX`：Google `gmail-smtp-in.l.google.com` 及 alt1–alt4 | 域具邮件路由；不证明该具体邮箱可投递、由 Ian 控制或获发送同意 |
| 官方 Instagram / 近 90 天公开活跃 | 官网导航/页脚未见官方 Instagram；Agent Reach 的 Instagram backend 需要未配置的 Chrome extension，Exa 实际返回 `Unknown MCP server 'exa'`。未登录、未绕过或猜测账号。 | **UNKNOWN，非本次合格依据** |

Google Maps 的一个普通浏览器精确查询触发 Google `sorry` 反自动化验证页；未点击/绕过 CAPTCHA，也没有把该工具限制写成商户问题。此后采用现有独立目录与政府注册来源，没有重复探测 Google。

## 4. 品牌投入/支付能力代理（不是购买意愿）

| 类型 | 证据 | 强度与边界 |
| --- | --- | --- |
| 独立、政府 | 活跃 ABN、Individual/Sole Trader、QLD 主址，以及 GST registration 自 2022 | 对正式经营与 GST 注册构成强代理；不是营收或网站采购预算 |
| 独立、第三方 | Facilicom 的 4.8 / 16 reviews，与官网电话一致 | 中等代理；评论时间、归属及真实性不能由本次确认 |
| 商户自述/自有投入 | 独立 quote 子域、统一品牌/电话、清晰服务覆盖、车辆/工作图片、30+ years 叙述 | 可作为已有数字/品牌投入的补强；不可当独立付款能力证据 |

以上至少两类相互独立信号达到入 Demo 资格线，但没有公开证据证明其一定愿为 AU$800 购买。

## 5. 报价子域与静态页边界

**保留现有 quote 外链：YES。** 该首步先区分住宅/商业、给出 Cairns 服务范围与电话替代；后续报价工作可能需要动态分支、客户资料和图片上传。它是该商户合理的现有 intake，不应被静态 Demo 重做或接管。

静态介绍页在 quote 前的独立价值：用一次清楚的叙事解释服务类别、服务区域、Ian/owner-operated、30+ years（须客户批准）、工作方式、电话/mailto/地图，并把 CTA 解释为：`Call / SMS for a quick conversation` 与 `Get a tailored quote`（外链至现有 quote）。这解决 W1–W3，却不取代报价系统。

允许且仅在客户批准事实/素材后可承载：稳定服务类别、服务区域、过程、经批准的资质/评价、电话、mailto、地图、现有 quote 外链。  
明确禁止：价格、折扣、动态报价逻辑、上传、地址/客户资料、预约、支付、服务端表单、后台、持续内容维护。

## 6. AU$800 判断与最强红队

**支持：** 公开可见的、可复现的 W1–W3 可以由一张静态页以不接管 quote 的方式改善；ABR/官网 owner 线索降低了“总部站点”风险；其既有报价流程说明网站不是完全无关的渠道；GST、第三方评价和现有数字资产是小型服务商的支付/品牌投入代理。

**反对：** 网站的电话、移动菜单和报价首步已经工作；Google/电话/现有 quote 可能承担大部分询盘；动态 quote 流程可能正是核心业务；没有公开预算、扩张、网站采购或近期需求信号。网站“更旧”绝不等于业主会付 AU$800。

**购买可能性：中低、尚未验证。** 仍推进 Demo 是为了以最小、只读后的静态概念测试“报价前信息层是否有价值”，不是因为购买已被证明。

## OUTREACH DRAFT PACKAGE

Recipient email: [REDACTED_EMAIL]  
Email source/date: https://pressurecleancairns.com.au/contact-us/ — 2026-08-16; 页面可见并为 `mailto:`。  
Email domain/MX: gmail.com — Google MX（`gmail-smtp-in.l.google.com`, alt1–alt4）于 2026-08-16 DNS 核验；这是公开业务用途 Gmail，非自有域名邮箱。  
Consent/lawful-basis: NOT VERIFIED — 未找到营销同意或其他发送依据；公开刊登和 MX 不构成同意。未见可核验拒收声明；服务相关性只足以支持草稿个性化，不能代替法律依据。  
Recommended subject: A small website idea for Cairns Pressure Cleaning’s quote path  
Demo URL: NOT READY  
Demo screenshot: NOT READY

Plain-text body:

```text
Hi Cairns Pressure Cleaning team,

I came across Cairns Pressure Cleaning while looking at independent businesses in Cairns. Your existing quote path already separates residential and commercial work; I wondered whether a simpler page before that step could make the services and next action clearer.

I’m Eli, an independent web designer. I put together a short private website concept to show one possible way to present your business and make enquiries clearer. It hasn’t been published, and I haven’t made any changes to your current website.

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
<p>Hi Cairns Pressure Cleaning team,</p>
<p>I came across Cairns Pressure Cleaning while looking at independent businesses in Cairns. Your existing quote path already separates residential and commercial work; I wondered whether a simpler page before that step could make the services and next action clearer.</p>
<p>I’m Eli, an independent web designer. I put together a short private website concept to show one possible way to present your business and make enquiries clearer. It hasn’t been published, and I haven’t made any changes to your current website.</p>
<p><a href="[Demo URL]">View the private website concept</a></p>
<p><a href="[Demo URL]"><img src="[Demo Screenshot URL]" alt="Preview of the private website concept for Cairns Pressure Cleaning" width="600"></a></p>
<p>Plain-text link: [Demo URL]</p>
<p>If it feels useful, simply reply to this email. I’d be glad to hear what you think.</p>
<p>Eli<br>[REDACTED_EMAIL]<br>+86 182 6851 4405</p>
<p>If you’d prefer not to hear from me again, reply “unsubscribe” and I won’t contact you again.</p>
```

Authorization: **DRAFT ONLY — NOT AUTHORIZED TO SEND**  
Blocking issues: No actual, privately hosted/accepted Demo or screenshot; no approved rights for commercial images, testimonials, ratings or claims; consent/lawful basis NOT VERIFIED; specific user authorization to send absent; recipient inbox control remains unverified; no verified operational unsubscribe handling. The bracketed Demo URL and screenshot placeholders must remain until a real, PMO-accepted private Demo exists.

## Source and limitation register

- Official homepage: https://pressurecleancairns.com.au/ (2026-08-16)
- Official service: https://pressurecleancairns.com.au/pressure-cleaning/ (2026-08-16)
- Official About: https://pressurecleancairns.com.au/who-we-are/ (2026-08-16)
- Official Contact: https://pressurecleancairns.com.au/contact-us/ (2026-08-16)
- Existing quote: https://quote.pressurecleancairns.com.au/or-quote (2026-08-16; viewed to first question only, no selection or submission)
- Government ABN: https://abr.business.gov.au/ABN/View?abn=24167780390 (2026-08-16)
- Independent directory: https://facilicom.au/directory/cleaning-services/solar-panel-cleaning/in/queensland/cairns/belvedere (2026-08-16)
- Agent Reach: `doctor --json` completed; Exa tool call returned `Unknown MCP server 'exa'` despite doctor status; no retry. `check-update` could not check due GitHub API rate limit; no update/install.

