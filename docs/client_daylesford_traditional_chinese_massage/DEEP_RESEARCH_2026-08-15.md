# Daylesford Traditional Chinese Massage｜公开深度研究

**研究日期：**2026-08-15（仅公开页面、无登录）  
**授权边界：** 未联系、未发送、未提交表单、未创建 Demo、未部署、未付费。  
**状态：** **HOLD — 待 PMO 验收**

## 结论

暂不进入 AU$800 静态单页 Demo 制作。商户“仍在经营”、公开商业邮箱/MX、现站问题和品牌投入信号均有足够证据；但 **Tyler Tang 的公开记录仅足以证明其是商户目录联系人，不能证明其拥有购买或网站决策权**。更重要的是，现站将动态价格、时长、套餐、礼券与预约/联系放在访客决策核心；在未得到明确的“仅常青信息 + 客户提供的第三方预约链接”范围确认前，静态单页可能削弱而非改善转化。

**可证伪 go/no-go 条件：** 仅当公开或经后续获授权沟通可证实“Tyler Tang（或另一位明确本地授权人）可决定网站采购”，且该授权人书面确认新页只承载下述常青范围、把所有当前价格/时长/可用档期/礼券/支付和预约留在客户维护的外部路径时，才改为 **ADVANCE TO DEMO**；任一条件不成立或要求把这些动态内容放入我方页面，则 **DROP**。

## 1. 当前实际经营：有两类独立证据

| 证据 | 2026-08-15 观察 | 判定与限制 |
| --- | --- | --- |
| Hepburn Shire Council 本地商户目录 | 列出商户、Shop 1, 9 Howe Street, Daylesford、Tyler Tang、0481 115 675、公开 Gmail、官网及周日至周六 09:00–19:00。目录文字称为“Registered and Qualified Remedial Massage Practitioners”。 | 独立于商户官网的地方政府目录；强的当前经营信号，但未显示其最近维护日期。 |
| Google Maps 的单个手动查询页 | 同名商户显示为 Massage therapist，地址为 Shop 1/9 Howe St，电话 +61 481 115 675，评分 4.9，并显示“Closed · Opens 9 AM Sun”和每天营业时段。 | 独立平台且地址/电话/官网与政府目录相符；“Closed”是检索时营业状态，不是停业标记。未批量提取 Maps 数据。 |
| 官网 | `https://dtcms.com.au/` 返回 HTTP 200；首页响应 `Last-Modified: Sat, 15 Aug 2026 10:27:37 GMT`。 | 可达与近期缓存/内容更新时间支持网站仍维护；不单独证明实体营业。 |

**结论：** 经营状态为 **PASS（高置信度）**。未发现“permanently closed”冲突；但两处目录/平台的时段只代表其各自公开记录，不能替代现场或客户确认。

## 2. 独立性、本地决策权与 Tyler Tang

- 政府目录的 `Contact` 字段仅列 **Tyler Tang**，并与商户名称、地址、电话、Gmail、官网和社媒链接一起出现。
- Google Maps 与政府目录在地址、电话和官网方面一致；这支持一个本地单点门店，而不是可识别的连锁总部页面。
- **不能证明：** Tyler Tang 的法律所有权、雇佣职位、持股、隐私身份或对 AU$800 网站采购的授权；也没有找到可用的公开公司登记材料来确认这些事项。

**判定：** “独立或本地可决策” = **EVIDENCE GAP**，而非 PASS。没有证据可把 Tyler Tang 称为 owner。

## 3. 联系渠道与社媒

| 项目 | 结果 | 证据/限制 |
| --- | --- | --- |
| 公开商业邮箱 | **PASS：** `[REDACTED_EMAIL]` | Hepburn Shire Council 的商户目录在 Contact 区公开刊登；2026-08-15 重新读取。它是业务目录中的联系渠道，而非推断的私人邮箱。 |
| 域名 / MX | **PASS（路由层）：** `gmail.com` 的 MX 为 Google 邮件交换服务器 | `dig +short MX gmail.com` 于 2026-08-15 返回 `gmail-smtp-in.l.google.com` 及备份记录。MX 不能证明该具体收件箱存在、可投递、同意营销或可发送。 |
| 官方 Instagram | **官方归属有支持；近 90 天活跃 = UNKNOWN** | 政府目录链接到 `instagram.com/daylesfordchinesemassage/`。`agent-reach doctor --json` 显示 Instagram OpenCLI 需不可用的浏览器扩展/登录；未登录、未绕过。匿名页面也只呈现登录墙，未显示最近帖子。 |

## 4. 官网问题：可复现、并区分审美与转化/可用性

审查条件：2026-08-15，公开 URL `https://dtcms.com.au/`；桌面内容由直接 HTTP/Jina Reader 读取，移动/交互技术检查由同日 `squirrel` quick browser-emulated audit（5 页）完成，报告见 `audit_2026-08-15.llm`。审计器提示 Cloudflare 可能造成覆盖不完整，故不把未发现的问题当通过。

| 问题 | 可复现观察 | 类型与影响 |
| --- | --- | --- |
| 首屏后的治疗选择信息混杂 | 首页依次出现 Facial、Remedial、Deluxe 与三段不同价格的重复 “Couples Massage Packages”；例如 90/120 分钟 couples 价格分别为 $370/$450 与 $350/$430。访客无法仅凭内容确定它们是替代套餐、不同条件还是内容重复。 | **真实转化/可用性问题。** 对价格敏感的访问者会增加比较成本，也提高价格失真的风险；不是单纯审美偏好。 |
| 关键行动路径被价格、礼券、联系表单和健康主张绑在一起 | 首页称“Advance booking is required”、引导联系或购买礼券；又称下班后填写站内 contact form。首页也出现 HICAPS/health-fund rebates、疼痛/孕期/慢性痛等健康相关表述。 | **真实交付边界问题。** 这些信息需要持续维护或谨慎合规；把它们复制进静态 Demo 会越界。移除它们又可能改变现有路径，故必须先确认外部预约和内容边界。 |
| 移动端可达性小问题 | 审计在首页及另外 3 页均标出至少一个可能过小的 tap target (`mobile/tap-targets`)；同一审计还发现 34 个位于 `aria-hidden` 内却可聚焦的元素，涵盖首页、blog、contact 和文章页。 | **真实移动/无障碍问题。** 小触控目标影响手机操作；焦点可达性问题影响键盘/辅助技术用户。不是视觉风格偏好。 |
| 内容密度与性能 | 审计抓到首页的 “massage” 密度 6.3%、页面结构中有 71 个子元素的复杂块；两篇被抓取的内容页 TTFB 为 2.56s 和 2.59s。 | **可能的转化/性能问题（中等证据）。** 这支持“路径冗长且 SEO 文本密集”，但没有真实用户漏斗数据，不能声称已造成流失。 |

补充审计事实：整体评分 50/F；Accessibility 48、Performance 54、Mobile 85。移动分类 85 不等于没有移动问题；它确实报告了 tap target 警告。审计还发现站内联系表单字段缺少合适 autocomplete、以及缺少 Privacy Policy 页面；这些是风险线索，不构成法律结论。

## 5. 静态单页适配性与交付边界

### 现站的动态依赖

当前官网明显依赖：价格、不同分钟数、套餐、礼券、预约/联系、HICAPS/健康基金资格与健康结果主张。它也含站内表单。这些均不应被我方静态页承载或维护。

### 条件式长期价值

一个纯静态单页可以长期独立提供价值，**仅当** 它作为稳定的品牌与到店说明页，而不是套餐/预约替代品：清晰说明服务类别、Daylesford 地址、地图、电话、公开邮箱、经批准的评价与资质，并只链接到客户提供且客户维护的第三方预约渠道。

| 允许（经客户批准/核实后） | 不允许 |
| --- | --- |
| 常青品牌叙事、服务类别、地址、地图、电话、邮箱、经批准评价与资质、客户提供的第三方预约外链 | 动态价格、时长、套餐、促销、礼券、可用档期、支付、站内表单、任何患者/客户数据、健康承诺或未证实的 HICAPS/基金资格 |

**Static HTML/CSS/light JS only：** 条件性 YES。  
**Backend dependency：** NONE（仅上述边界成立时）。  
**Ongoing content responsibility：** CLIENT / NONE FOR US；第三方预约由客户维护。

## 6. 支付能力/品牌投入信号（不等于购买意愿）

1. **独立信号：** Google Maps 与政府目录一致的实体门店、电话、官网和固定营业时段；官网使用专用 `.com.au` 域并部署在 WordPress/WP Engine/Cloudflare。此类持续的线下与数字存在是品牌投入信号，不是预算证明。
2. **独立信号：** Google Maps 公开显示 4.9 评分；这证明存在公开评价足迹，但当前页面未提供可审计的完整评价数量或时间线。
3. **商户自述，须复核：** 官网宣称 4.9/617 reviews、HICAPS/health-fund rebates 与多个行业协会/注册资格。可说明其试图传递信任与服务定位，**不得**在任何 Demo/外联中当作已验证卖点。

## 7. AU$800 购买可能性

**支持：** 单点本地商户、专用域与实体地址、公开评价足迹，以及可复现的信息架构和移动无障碍问题，使一个不含后台的“常青介绍 + 清晰预约外链”概念可能有合理价值。

**反对：** 无公开 AU$800 预算、采购意图或决策权证据；现站并非不存在，且已把价格、礼券、联系表单和 WhatsApp（首页内嵌评价文字提及）纳入旅程。商户可能依靠既有评价、电话/WhatsApp 和现站获得足够预约；若老板重视即时套餐价格和站内联系，静态页反而删弱必要信息。

**购买可能性判定：** **UNKNOWN / 不足以推进。** 支付能力或既有技术投入不能被当作购买意愿。

## 8. 最强红队

- **可能完全不需要新站：** Google Maps 已给出地址、营业时间、电话、官网与高评分；回头客可能直接电话或 WhatsApp，访客也能在当前网站查到丰富的套餐/价格。
- **现有 SEO/评价/预约路径可能已足够：** 大量内容页与关键词虽然冗长，却可能仍带来自然搜索；评价/礼券/现有联系表单可能构成有效工作流。没有分析数据或老板反馈，不能假设“更简洁”会带来更多预约。
- **静态单页可能降低效果：** 不能安全、长期地复制套餐价格、时长、健康基金资格、礼券、实时可用性或站内联系；若把它定位为完整替代品，访客会失去他们当前用于决策的内容。任何 Demo 必须明确是补充性常青入口，而非替代或迁移。

## OUTREACH DRAFT PACKAGE

Recipient email: `[REDACTED_EMAIL]`  
Email source/date: Hepburn Shire Council public business directory; https://www.hepburn.vic.gov.au/Council/Find-a-local-directory/Find-a-local-business/Daylesford-Traditional-Chinese-Massage ; retrieved 2026-08-15.  
Email domain/MX: `gmail.com`; Google MX records present 2026-08-15; no mailbox-delivery test.  
Consent/lawful-basis: **NOT VERIFIED** — public business-directory source and relevance only; no marketing consent, refusal statement or applicable lawful basis has been verified.  
Recommended subject: A small website idea for Daylesford Traditional Chinese Massage  
Demo URL: **NOT READY**  
Demo screenshot: **NOT READY**

Plain-text body:

```text
Hi Daylesford Traditional Chinese Massage team,

I came across Daylesford Traditional Chinese Massage while looking at independent businesses in Daylesford. Your public directory listing makes the location and contact details clear; a focused page could help visitors understand the main service categories before following your existing appointment route.

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
<p>Hi Daylesford Traditional Chinese Massage team,</p>
<p>I came across Daylesford Traditional Chinese Massage while looking at independent businesses in Daylesford. Your public directory listing makes the location and contact details clear; a focused page could help visitors understand the main service categories before following your existing appointment route.</p>
<p>I’m Eli, an independent web designer. I put together a short private website concept to show one possible way to present your business and make enquiries clearer. It hasn’t been published, and I haven’t made any changes to your current website.</p>
<p><a href="[Demo URL]">View the private website concept</a></p>
<p><a href="[Demo URL]"><img src="[Demo Screenshot URL]" alt="Preview of the private website concept for Daylesford Traditional Chinese Massage" width="600"></a></p>
<p>Plain-text link: [Demo URL]</p>
<p>If it feels useful, simply reply to this email. I’d be glad to hear what you think.</p>
<p>Eli<br>[REDACTED_EMAIL]<br>+86 182 6851 4405</p>
<p>If you’d prefer not to hear from me again, reply “unsubscribe” and I won’t contact you again.</p>
```

Authorization: **DRAFT ONLY — NOT AUTHORIZED TO SEND**  
Blocking issues: decision authority/local procurement authority not verified; consent/lawful basis not verified; no private Demo or screenshot; no rights-cleared approved content; no customer-approved external booking URL and static-content boundary; operational unsubscribe mechanism not verified.  

## Sources and method notes

- Official site: https://dtcms.com.au/ (retrieved 2026-08-15)
- Hepburn Shire Council directory: https://www.hepburn.vic.gov.au/Council/Find-a-local-directory/Find-a-local-business/Daylesford-Traditional-Chinese-Massage (retrieved 2026-08-15)
- Manual Google Maps search link: https://www.google.com/maps/search/?api=1&query=Daylesford+Traditional+Chinese+Massage+9+Howe+Street+Daylesford (retrieved 2026-08-15; one direct business lookup, no bulk extraction)
- Instagram: https://www.instagram.com/daylesfordchinesemassage/ (anonymous result was a login wall; activity not asserted)
- Website audit: `audit_2026-08-15.llm` in this folder; 5-page quick scan, browser-emulated, not a full accessibility or legal audit.
- `agent-reach doctor --json` was run first. Exa was advertised as available but its actual `mcporter` call returned `Unknown MCP server 'exa'`; it was not installed or retried. Instagram OpenCLI was unavailable because its required browser extension/login was unavailable. These are recorded capability gaps, not negative findings about the business.

**Final status: HOLD — 待 PMO 验收。**
