# Cherry Walk Cafe｜网站与 CRO 审计

对象：https://cherrywalkcafe.com/

retrieved_at：2026-08-14

## 验证范围

- 无登录 Playwright 真实 Chromium：1440×1000 桌面、390×844 移动端。
- 检查：首页可达性、可访问名称、CTA、菜单内容、联系/预订路径、控制台。
- 两个视口首页均可加载，标题为 `Cherry Walk Cafe – Bright, Victoria Australia`；控制台无 warning/error。
- 未绕过登录、CAPTCHA、WAF；未提交预订、表单或任何外写。

## 最重要且可复现的 3 组问题

### 1. 核心转化事实不可信，预订链本次不可完成

- 官网显示 `8 Anderson Street`、`Monday to Sunday 7:00AM - 5:30PM`；2026 Guide 和多个近期目录仍显示 6 号及不同时间。
- 主 CTA `Book a Table` 能打开：https://bookings.wowapps.com/make-booking/cherrywalkcafe?src=web
- 390px 实测新标签只显示：`Error loading. Please contact support.`，未出现可用预订表单。
- 类型：观察事实 + 冲突判断。
- 置信度：高（页面文本与浏览器路径直接观察）；第三方故障持续性仅低/中，不能外推为永久故障。
- CRO 影响：用户在最高意向动作处失败；错误地址/时间可能制造到店风险。
- 推翻条件：Owner 确认 canonical 事实并统一所有官方页面；WowApps 在两个独立时段、桌面与移动端均完成到选择时段步骤。

### 2. 内容完整性与专业可信度不足

- About 图片可访问名称为 `Default About Image`。
- `waffles` 的描述错误复用了 toasted muesli 文案。
- 可见拼写/录入错误包括 `sourgough`、`poached edd`、`parmeson`、`All Right Reserved`。
- testimonial 组件将同一组人名/文案重复渲染多轮；Holly Anderson、Sanjeev Kumar 等重复出现。
- WordPress 公共面仍暴露并返回 200：`/hello-world/`、`/author/admin/`、`/author/leanne/`；`wp-sitemap.xml` 收录 users、post、meal 等 sitemap。
- 类型：观察事实。
- 置信度：高。
- CRO 影响：削弱真实性、菜单可信度与“店主有在维护”的信号；搜索面混入模板/作者页。
- 推翻条件：同 URL 新版本中相关内容纠正，公共模板/作者页下线或正确 noindex，并经真实浏览器与 sitemap 复验。

### 3. CTA 与移动可访问性存在明显摩擦

- 首页多处设施链接与 `Visit Us` 实际指向空 `#`；点击不会进入有效内容或地图。
- 图标式主要 CTA 在可访问性树中没有名称；移动端 hamburger 按钮同样无名称。
- 社交图标链接缺少可访问文本；桌面和 390px 均复现。
- 类型：观察事实。
- 置信度：高。
- CRO 影响：视觉按钮与真实动作不一致，键盘/读屏用户无法理解，移动导航信任度下降。
- 推翻条件：所有交互元素有明确目的 URL/动作及 accessible name，并通过键盘与 390px 复验。

## squirrel quick audit（有保留地使用）

- 限制：quick、最多 10 页；工具报告 45/F、81 failed、291 warnings，并确认无名 hamburger、空社交链接、缺 meta description、公开 author/hello-world/meal 页面、缺隐私页等。
- 直接复核：`/hello-world/`、`/author/admin/`、`/author/leanne/` 均 HTTP 200；`/privacy-policy/` HTTP 404；`wp-sitemap.xml` 确实含 users/post/meal sitemap。
- 能力偏差：squirrel 在执行时未经授权自动从 v0.0.61 升级到 v0.0.80，并出现多次 `ZlibError`。因此 **不把 45 分当成完整或可比基准**；仅采用已被浏览器或直接 HTTP 独立复核的具体问题。

## CRO 判断

- 页面类型：首页/单页式门店官网。
- 主要转化：预订桌位；次级目标为看菜单、确认地址/时间、到店。
- 当前最大问题不是视觉，而是“事实与动作不可靠”。在 canonical 信息未确认前，优化文案或做漂亮 Demo 会放大错误。
- 优先顺序：事实统一与预订恢复 → 菜单/评价内容去错去重 → CTA 与移动可访问性 → SEO/性能。
