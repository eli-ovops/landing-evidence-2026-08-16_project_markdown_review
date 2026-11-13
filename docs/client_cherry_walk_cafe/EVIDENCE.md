# Cherry Walk Cafe｜证据台账

统一 retrieved_at：**2026-08-14**

## 来源

| ID | 来源 | URL | 层级 | 用途与限制 |
| --- | --- | --- | --- | --- |
| SRC-001 | 澳洲政府 ABN Lookup | https://abr.business.gov.au/ABN/View?id=33630806870 | A | 主体 Active、GST、业务名；不证明门店当天营业或现金流 |
| SRC-002 | Cherry Walk Cafe 官网 | https://cherrywalkcafe.com/ | A（仅证明其公开主张） | 地址、时间、电话、社交、菜单、CTA；不能自动证明内容正确 |
| SRC-003 | Yahoo/AAP 2026-03-30 报道 | https://au.news.yahoo.com/live/dezi-freeman-live-fugitive-killed-by-police-after-victorias-largest-ever-manhunt-230846497.html | C | 明确称 Leanne Boyd 为 owner，门店在事件中持续营业 |
| SRC-004 | Muck Rack / Border Mail 索引 | https://muckrack.com/ted-howes | C | 2026-03-30/04-01 报道索引称门店已反弹；正文受限，降权使用 |
| SRC-005 | Buckley's Guide 2026 | https://buckleysguidesaustralia.com.au/wp-content/uploads/2025/12/BGA2026-108PAGESCOVER-Art-web.pdf | C | 公开商业邮箱、6 号、7:00–17:00；指南信息可能由商户提交但未确认机制 |
| SRC-006 | Localista | https://melbournelocalista.com.au/listing/cherry-walk-cafe?place=bright%2C+vic%2C+au | C | 标注 2026-07-26 更新、6 号和另一套时段；聚合数据可能旧/自动回填 |
| SRC-007 | Wanderlog | https://wanderlog.com/place/details/562208/cherry-walk-cafe | C | 2026-05 评价、约 3.9/568、6 号；聚合 Google/Tripadvisor，非独立原始平台 |
| SRC-008 | AGFG | https://www.agfg.com.au/restaurant/cherry-walk-cafe-49752 | C | 8 号、50 seats、支付方式、7:00–17:30；目录事实仍需 Owner 核准 |
| SRC-009 | North East Directory | https://northeastdirectory.com.au/business-directory/8210/cherry-walk-cafe/ | C | `Shop 4/8 Anderson Street` 与固定电话 |
| SRC-010 | Localsearch | https://www.localsearch.com.au/find/takeaway-food/porepunkah-vic | C | `4/6-8 Anderson St`，可能解释门牌冲突但非权威地址登记 |
| SRC-011 | Tripadvisor | https://www.tripadvisor.co.uk/Restaurant_Review-g495047-d7111935-Reviews-Cherry_Walk-Bright_Victoria.html | C | claimed listing、8 号、7:30–16:00且周三关闭、4.4/269；近期性有限 |
| SRC-012 | Restaurant Guru | https://restaurantguru.com/Cherry-Walk-Bright | C | 2026 更新、A$20–40、约 3.9、6 号；聚合评价不可当独立原始样本 |
| SRC-013 | WowApps booking | https://bookings.wowapps.com/make-booking/cherrywalkcafe?src=web | A（实际测试） | 2026-08-14 390px 浏览器只显示加载错误；仅代表本次实测 |
| SRC-014 | 官网 sitemap/公开 URL | https://cherrywalkcafe.com/wp-sitemap.xml | A（实际测试） | users/post/meal sitemap；hello-world 与 author 页直接 HTTP 200 复核 |
| SRC-015 | The Queenslander/AAP | https://theqldr.com.au/crime-law-and-justice/2025/09/15/officer-40/ | C | 报道嵌入官方 Instagram 帖，证明账号归属/2025 活动，不证明近 90 天活跃 |

## 关键事实与判断卡

### CLM-001｜当前仍在经营

- FACT-001（observed）：SRC-003 在 2026-03-30 把 Cherry Walk Cafe 描述为当时仍营业的本地 cafe，并称 Leanne Boyd 为 owner。
- FACT-002（observed）：SRC-007 显示 2026-05-16 新评价；SRC-006 标注 2026-07-26 更新。
- FACT-003（observed）：SRC-001 的 2026-05 抽取记录显示 BOYDCO BAKERY PTY LTD Active、GST registered，Cherry Walk Cafe 业务名仍列示。
- 判断：当前经营成立。
- 置信度：高；新闻 + 新评价 + 新目录 + 主体状态跨源相互支持。
- 推翻条件：官方停业/清算/转手公告；现场或 Owner 证据显示已关门；2026 来源被证实为旧数据误标。

### CLM-002｜独立、本地决策权

- FACT-004（observed）：SRC-001 显示私营公司而非全国连锁主体；SRC-003 直接称 Leanne Boyd 为 owner。
- 判断：本地独立决策权较强，但签约权未直接验证。
- 置信度：中高。
- 推翻条件：发现加盟总部、物业/品牌方控制官网采购，或 Leanne 已不再参与经营。

### CLM-003｜唯一地址与营业时间

- FACT-005（observed）：SRC-002 = 8 号、每日 7:00–17:30；SRC-005 = 6 号、每日 7:00–17:00；SRC-009 = Shop 4/8；SRC-010 = 4/6–8；SRC-006/007/011/012 时段继续冲突。
- 判断：未核准；`Shop 4, 6–8` 是合理解释但不是事实。
- 置信度：高（冲突存在），低（冲突解释）。
- 推翻条件：产权/租约/官方门牌、商户原始账单或具名 Owner 书面确认 canonical 写法和逐日时间。

### CLM-004｜官网存在可承接的转化问题

- FACT-006（observed）：桌面与 390px Playwright 复现 Default About Image、空 `#`、错误菜单描述、拼写、testimonial 成组重复、无名移动按钮/CTA。
- FACT-007（observed）：SRC-013 本次只显示加载错误。
- FACT-008（observed）：SRC-014 及直接 HTTP 检查确认 hello-world/author 页 200；privacy-policy URL 404。
- 判断：问题真实且可复现，但第三方预订故障持续性未知。
- 置信度：内容/可访问性高；预订持续性中低。
- 推翻条件：站点发布新版本并通过桌面/390px/预订闭环复验。

### CLM-005｜AU$800 支付可能性

- FACT-009（observed）：主体 GST registered；SRC-008 声称 50 seats、刷卡；SRC-012 标注 A$20–40/人；官网、指南和外部订位说明已有数字投入。
- 反证：3.8–3.9 聚合评分、运营负面主题、旅游现金流波动、现有官网看似刚更新、无预算/意向证据。
- 判断：负担能力可能存在；购买意愿未知偏谨慎。
- 置信度：中低。
- 推翻条件：Owner 提供预算/意向/ROI；或公开财务、停业/欠费、供应商合同证明相反。

## 工具与搜索边界

- agent-reach doctor 报告 Exa 可用，但实际调用统一失败：`Unknown MCP server 'exa'`；未安装/修复，降级内置公开搜索 + Jina/直接网页。
- 社交后端依赖登录态；本任务禁止登录，因此未调用 OpenCLI。
- squirrel quick audit 限 10 页；工具未经授权自动升级并出现 `ZlibError`，仅保留经 Playwright/HTTP 独立复核的问题，不采用总分为最终事实。
- 未批量抓取 Google Maps、未保存 Place ID、未绕验证码/WAF、未发送或 SMTP 探测邮箱。
