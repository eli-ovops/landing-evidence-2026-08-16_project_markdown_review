# Bright Velo｜证据台账

统一 retrieved_at：2026-08-14。互联网事实均区分事实/推断、置信度与推翻条件。

## 可证伪初始假设

> Bright Velo 是仍在经营、由本地 owner 可决策的独立商户；官网虽能预订，但存在足以让 AU$800 单页优化具备经济合理性的转化泄漏。

该假设的“经营/主体/问题存在”得到支持；“会支付 AU$800”仍未验证。

## 来源登记

| ID | 来源与 URL | 类型/等级 | 支持范围 |
|---|---|---|---|
| SRC-001 | Bright Velo 官网 https://www.brightvelo.com.au/ | 商户一手公开主张/A | 产品、owner Tim、地址、邮箱、电话、CTA、首页结构 |
| SRC-002 | 联系页 https://www.brightvelo.com.au/contact-bright-cycling-hotel | 商户一手页面/A | 表单、渠道、服务范围 |
| SRC-003 | Basils 页 https://www.brightvelo.com.au/basils | 商户一手页面/A | 当前餐饮内容、营业时间、OpenTable |
| SRC-004 | 旧餐饮页 https://www.brightvelo.com.au/dining-in-bright | 商户一手页面/A | `Coming Soon` 现状 |
| SRC-005 | RMS https://bookings12.rmscloud.com/Search/Index/EBF23A147D0A35BB/1/ | 第三方实际初始流程/A | 预订跳转与初始输入项 |
| SRC-006 | Booking.com https://www.booking.com/hotel/au/bright-velo-bright1.html | 成熟第三方平台/B | 8.5/10、598 reviews、2026 近期评价 |
| SRC-007 | ABN Lookup https://abr.business.gov.au/ABN/View?id=97634145583 | 政府登记/A | CYCLE PLAN PTY LTD、Active、VIC 3741、Bright Velo business name |
| SRC-008 | Bright & Surrounds https://www.visitbright.com.au/listing/bright-velo-bright/ | 地方官方旅游目录/B | 地址、价格、渠道、预订链接、社媒 |
| SRC-009 | Nine/Getaway https://9now.nine.com.au/getaway/australia-and-new-zealand/2025-bright-cycling-hotel-victoria-catriona-rowntree/811eca07-5709-4c5c-b383-fa15c4991ed4 | 媒体/C | 2025 年 owner Tim Briggs 身份 |
| SRC-010 | DNS MX 实测 `dig +short MX brightvelo.com.au` | 实际测试/A | Google Workspace MX 存在 |
| SRC-011 | 本地 Playwright 证据 `output/playwright/` | 实际测试/A | 桌面/390px 可见内容、CTA、表单、RMS 初始页 |
| SRC-012 | squirrel v0.0.85 surface audit，30 页 | 自动规则测试/A（需人工解释） | SEO、性能、表单与结构线索；非 full coverage |

## 关键事实

### FACT-001｜当前经营

- observed：ABN 97 634 145 583 的主体 CYCLE PLAN PTY LTD 状态 Active，Bright Velo 商业名称自 2022-11-17 登记，主营业地 VIC 3741（SRC-007）。
- observed：Booking.com 当前页有 2026 年近期住宿评价、8.5/10 与 598 reviews（SRC-006）。
- observed：RMS 初始预订页可加载，且 Bright & Surrounds 仍列出 Book now 与 AU$120–600（SRC-005/008/011）。
- judgment：当前经营成立，置信度高。
- 推翻条件：官方登记转为取消/失效、预订入口关闭，且近期第三方经营证据被证实错误。

### FACT-002｜独立/本地决策权

- observed：ABN 主体为 Australian Private Company，地址口径 VIC 3741（SRC-007）。
- observed：官网称 `Owner Tim`；Nine 2025 年报道明确称 `Bright Velo hotel owner Tim Briggs`（SRC-001/009）。
- inferred：Tim Briggs 很可能具备商户级营销决策权，置信度中高。
- 未知：谁持有 Wix 管理员权限、是否受既有代理合同约束。
- 推翻条件：现 owner 已变更，或网站/品牌由第三方总部/物业方控制。

### FACT-003｜有效联系

- observed：官网与官方旅游目录一致公开 info@、电话、联系表单与同一 Instagram（SRC-001/002/008）。
- observed：域名存在 5 条 Google Workspace MX（SRC-010）。
- judgment：公开商业联系渠道成立；邮箱单地址可投递性未验证。
- 推翻条件：官网/目录更新为其他渠道，或后续合法验证显示地址无效。

### FACT-004｜三个问题

- observed：主页餐饮卡指向 `Coming Soon`，而顶栏 Basils 页已有当前餐饮内容（SRC-001/003/004/011）。
- observed：评论视觉五星与可访问性文本 3/5 冲突；Booking.com 为 8.5/10（SRC-001/006/011）。
- observed：联系页一般询问也要求 7 字段，含必填手机与具体日期（SRC-002/011/012）。
- judgment：问题存在，置信度高；收入影响大小未量化。

### FACT-005｜AU$800 合理性

- calculated：AU$800 ÷ AU$600 = 1.33 房晚；AU$800 ÷ AU$120 = 6.67 房晚。价格区间来自 SRC-008。
- inferred：若单页修复带来少量额外直订或一笔团体询盘，成本可能回收。
- counterevidence：现站已可预订、已有强口碑，问题可能被现有 Wix 管理者低成本修复。
- judgment：经济合理性中置信；真实支付意愿低置信。
- 推翻条件：官网流量/转化接近零、维护方可免费修复、或范围被扩大到后台/素材/部署。

## 第一性原理与对抗式审查

### 前提与必要条件

根目标不是证明“网站有 bug”，而是判断是否值得 PMO 为 AU$800 单页升级投入下一阶段。必要条件为：经营真实、决策路径可达、联系合法、问题影响转化、单页能闭合、价格相对潜在收益合理。

### 攻击/误用方式

1. 把 Booking.com 评论数当成官网转化证据；
2. 把 ABN Active 当成 Wix 权限证据；
3. 把自动审计 F 分当成必须重建网站；
4. 把隐藏/抓取层文字当成所有访客可见；
5. 把一两个房晚的算术回本当成商户会付款；
6. 把 KEEP 当成可联系或可制作 Demo。

### 阻断证据

- 浏览器证明现站视觉与 RMS 核心链可用，反驳“整站失效”。
- Wix 权限、流量、漏斗、预算均没有公开证据，阻断付款确定性结论。
- 真实浏览器区分可见页面与 Jina/搜索抓取层，避免把隐藏占位内容写成普通访客故障。
- KEEP 明确只进入 PMO 考虑，不扩张联系、Demo 或发布授权。

### 残余风险与闭环验证

- 残余风险：owner 已变更、Basils 关系变化、官网并非主要订单渠道、表单后端提交异常、RMS 库存/支付闭环未验证。
- 修正：结论为 KEEP，但付款意愿保持未验证，下一步只能补证。
- 闭环：由 PMO 决定是否另行授权 owner/权限/90 天漏斗/预算确认；没有补证不得升级为“已验证客户机会”。

## 搜索与工具缺口

- agent-reach Exa 实际不可调用；错误为 `Unknown MCP server 'exa'`，未继续重试或安装。
- Instagram 近 90 天活跃度未核，因为可用后端依赖登录态，与本任务“无登录”冲突。
- Booking.com 评论数随时间和页面口径变化；本次主页面为 598，历史/语言版抓取为 574–582，报告保留时间口径。
