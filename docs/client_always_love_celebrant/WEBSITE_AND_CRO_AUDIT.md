# WEBSITE AND CRO AUDIT

> 状态：待 PMO 验收  
> 目标：判断是否存在足以支持 AU$800 静态单页购买的真实决策/联系问题，而不是罗列 SEO 分数

## 方法与边界

- Playwright CLI，真实 Chromium、无登录：桌面 `1440×900`，移动 `390×844`。
- 浏览首页、Services、Contact；未提交表单、未点击外部社交、未下载套餐 PDF。
- Squirrelscan `v0.0.85`：5 页 quick audit，`--refresh`，只作辅助。
- 公开网页用 Jina Reader 交叉读取。
- Exa 的 `agent-reach doctor` 显示可用，但三次调用均返回 `Unknown MCP server 'exa'`；停止重试、未安装/改配置，改用公开搜索与 Jina。该故障不计入网站问题。

## 现站已经做得好的部分

- 桌面首屏 5 秒内可理解：celebrant、婚礼/私奔/人生仪式、Mudgee 地域和服务入口。
- 品牌 Logo、专业婚礼摄影、Victoria 个人形象、服务分层、Testimonials、服务区、电话/邮箱/Contact form 均已存在。
- Services 页能解释服务方式，并列三类婚礼套餐和葬礼/纪念服务。
- 三份 2026-07 套餐 PDF 证明内容近期维护，不是弃置站。
- 首页 `mailto:` 实测正确；没有复现第三轮其它商户那类断裂联系链接。

## 最多 3 个核心问题

### 1. 移动首屏的主价值与 CTA 随轮播状态消失（High impact，High confidence）

**事实：** 在 `390×844` 点击首个轮播点后，首屏只显示婚礼照片和轮播箭头；“A celebrant for all occasions”、服务范围与 “Our Services” CTA 均不可见。轮到第二张时才显示 Victoria 身份和 “About Victoria”。桌面首屏则能看到完整定位与 CTA。

**为什么影响购买/联系：** 移动冷访客的第一屏无法稳定回答“她是谁、做什么、下一步是什么”，信息取决于自动轮播时机；社交图标和菜单不是等价的联系/询盘 CTA。

**静态单页可证明的 Before → After：** 固定、不轮播的移动 hero，始终显示一句明确定位、服务区和一个主 CTA（致电/邮件），同时保留真实品牌图像。

**缺口：** 没有真实用户、热图或转化数据，不能量化损失。

### 2. 套餐人数信息已出现跨页面冲突，内容责任是真实问题（High decision relevance，High confidence）

**事实：** 首页写 Petite Weddings “Up to 30 guests”，Services 当前页面写 “Micro Weddings Up to 25 guests”，并链接 2026-07 更新的套餐 PDF。三个 PDF 的 `Last-Modified` 为 2026-07-22。

**为什么影响购买/联系：** 客户在判断套餐是否适用时会遇到 25/30 人冲突。它也证明套餐、场地、费用/法律流程不是完全静态内容，需要持续 Owner。

**静态单页可做什么：** 只写客户确认过的稳定服务层级和“联系确认当前适用人数/价格/档期”，把详细套餐 PDF 作为客户自有外链。

**不能承诺：** 我方不维护价格、人数、档期、法律/证书费用或套餐 PDF；如果客户要求这些长期准确，纯静态交付不适配。

### 3. 页面负重可能增加移动摩擦，但尚不足以单独构成购买理由（Medium impact，Medium confidence）

**事实：** Squirrel 5 页 quick audit记录总跟踪资源约 `6199KB`、首页 16 个阻塞脚本、首页 TTFB 约 `1095ms`、多项缓存缺口；审计总分 45/F。真实 Chromium 能加载页面。

**为什么可能影响联系：** 图片和旧 WordPress/轮播脚本负重可能延迟移动首屏和交互。

**为什么不能过度解读：** 这是单次工具环境结果，不是 CrUX/真实用户数据；45/F、缺 meta、缺 H1、模板页本身都不能证明客户会为重做付费。

## 非核心但应记录的技术卫生

- 5 页 quick audit发现缺 meta description、标题短、H1 结构问题、`/about-us/` 与 `/team/` 孤立模板页，`/team/` 含隐藏 Lorem ipsum。
- Contact form 的 Cloudflare Turnstile 在自动化浏览器产生 403/iframe 拒绝；这只说明自动化路径受限，**不等于普通用户表单故障**。
- Sitemap 报告发现 45 个 URL；本轮没有 full crawl。

## CRO 判断

| 维度 | 当前判断 |
|---|---|
| Value proposition | 桌面清楚；移动首屏不稳定 |
| CTA | 有 Services/Contact；移动首屏第一张缺主 CTA，直接电话/邮箱在页底 |
| Trust | 已有 Victoria 身份、照片、自述资质、Testimonials；强于一般弱站 |
| Objection handling | 服务页已有较完整解释和套餐分层；详细内容在 PDF |
| Friction | 移动轮播、25/30 人信息冲突、页面负重 |
| 替代紧迫性 | 低到中；网站不是整体失效，问题可以被现供应商局部修复 |

## 审计结论

真正足以做 Demo 假设的问题只有两个：**移动 hero 的稳定信息/CTA** 与 **套餐信息单一真相源**。性能是辅助价值，不应当做销售主因。由于现站品牌、信任、服务和联系已相当完整，这些问题更像局部修复/内容治理，而不天然证明需要 AU$800 全新静态单页。

