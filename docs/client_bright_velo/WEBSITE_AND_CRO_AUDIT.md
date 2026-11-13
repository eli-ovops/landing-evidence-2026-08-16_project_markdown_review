# Bright Velo｜网站与 CRO 审计

retrieved_at：2026-08-14

## 方法与范围

- 桌面：Chrome，1440×1000，无登录。
- 移动：同一公开会话调整为 390×844，无登录。
- 关键路径：首页 → 餐饮入口；首页 → RMS Book Now；联系页表单。
- 技术审计：squirrel v0.0.85，fresh surface，最多 30 页；实际 30 页，非 full coverage。
- 未提交表单、未选择住宿日期、未购买。

## 三个最重要、可复现问题

### 1. 首页主餐饮入口仍导向过期 `Coming Soon` 页面

- 观察事实：首页的 `Delicious Dining` 卡片在桌面与 390px 的链接均为 `https://www.brightvelo.com.au/dining-in-bright`。
- 真实浏览器结果：该页只显示 `Dining at Bright Velo / Coming Soon`。
- 冲突事实：当前顶栏 `EAT | BASILS` 已导向 `https://www.brightvelo.com.au/basils`，后者公开营业时间、OpenTable 和联系信息。
- CRO 影响：从首页产生的餐饮兴趣被送到没有菜单、营业时间或订桌 CTA 的旧页，直接打断“住宿 + 餐饮”的价值叙事。
- 置信度：高。
- 推翻条件：首页卡片改链至 Basils 或旧页完成重定向/更新。

证据：`output/playwright/home-desktop.png`、`output/playwright/home-mobile-390.png`、`output/playwright/dining-coming-soon-mobile-390.png`。

### 2. 评论组件存在评分语义冲突

- 观察事实：视觉卡片显示五星，但真实浏览器可访问性树在首页与设施页输出 `average rating is 3 out of 5`。
- 外部交叉：Booking.com 当前公开住宿页显示 8.5/10，598 条评价；其公开评价页在不同抓取时点显示 574–582 条，说明计数会变化，但 8.5 评分稳定。
- CRO/信任影响：屏幕阅读器、搜索抓取层与视觉用户收到不同评分；同时浪费了更强的第三方社会证明。
- 置信度：高（语义冲突）；低于高（对实际转化损失的量化）。
- 推翻条件：组件的可访问名称/结构化评分与可见五星或可核第三方评分一致。

证据：Playwright 首页与设施页 snapshot；https://www.booking.com/hotel/au/bright-velo-bright1.html 。

### 3. 高价值咨询表单对一般询问要求过多

- 观察事实：联系页文案同时服务 accommodation、dining、cycle tours、curated experiences，但 390px 表单强制 First Name、Last Name、Email、Mobile Phone、Requested Date（日/月/年）和消息。
- CRO 影响：尚未确定日期的团体、活动或定制旅行线索也必须编造/决定手机号与日期，增加移动端放弃概率。
- 技术交叉：surface audit 同样识别为 7-field form，并提示缺少常见 autocomplete token；提交功能未测试。
- 置信度：高（摩擦存在）；中（对放弃率的影响方向）；没有真实漏斗数据，不能量化。
- 推翻条件：日期/手机改为可选或按咨询类型渐进显示，且实际数据证明现表单没有明显放弃。

证据：`output/playwright/contact-mobile-390.png`。

## 次要观察（不计入前三）

- 390px 首页首屏的超大 `Explore.` 文案发生横向裁切，但核心 `BOOK NOW` 仍可见。
- 页脚仍显示 `CYCLING OLD` 与 `© 2024`；属于维护感知问题，不单独证明收入损失。
- Jina/搜索抓取层仍能读到设施页隐藏的未发布编辑占位文字；真实桌面页面未显示该段，因此不应描述成所有访客都能看见。
- squirrel 总分 46/F 仅是 30 页规则扫描，不等于商业故障。较可信的人工交叉项包括：首页缺 H1、联系人页 HTML 很重、表单可访问性/自动填充问题。扫描器的潜在敏感项只应由站点 Owner 在 Wix 后台核实，不能据自动命中认定泄露。

## 可访问性、CTA 与预订路径结论

- 首页桌面与移动均可访问，首屏 Book Now 清晰可见。
- 多个 Book Now 均指向外部 RMS；实际跳转到 `https://betaibe12.rmscloud.com/EBF23A147D0A35BB/1`。
- 选择 `Reject All` 后，390px RMS 页显示 Dates、Guests、Promo Code、Search；搜索在未选日期时禁用，符合预订逻辑。
- 因未选日期/未购买，本研究只证明入口和初始表单可用，不证明库存、支付或订单闭环。

证据：`output/playwright/rms-booking-mobile-390.png`。
