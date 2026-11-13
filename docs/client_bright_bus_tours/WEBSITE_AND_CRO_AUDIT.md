# 网站与 CRO 审计

## 验证范围

- 正常无登录真实浏览器：桌面 `1440x1000`、移动 `390x844`
- 页面：首页、Bus Tours、Our Buses、Contact；CTA 只点击到目标页，不填写、不提交、不处理 reCAPTCHA
- 公开读取：https://www.brightbustours.com.au/
- 状态：页面可访问。初始短暂“请稍候”验证后，真实浏览器正常进入内容；这不是网站故障。

## 最重要的 3 个可复现问题

### 1. `Book online now` 与 `Request a quote` 是同一路径，承诺与结果不一致

- 复现：桌面点击首屏 `Request a quote`，到 `https://www.brightbustours.com.au/contact.html#contact-form`；390px 点击首屏 `Book online now`，也到同一 URL。
- 观察：目标页明确写的是联系/预订通用表单，并承诺稍后联系讨论；没有库存、班次、即时确认、支付或“在线预订”能力。
- 影响：准备预订的人会误以为能即时完成；只想询价的人又看不到下一步时效。CTA 层级无法区分“查信息 / 询价 / 预订意向”。
- 最小修正方向：统一为一个主要 CTA，如 `Get a tailored charter quote`，旁边说明“告诉我们日期、人数与路线；人工确认可用性和报价”，并公开响应预期。

### 2. 关键决策信息不足，且车辆容量口径在页面与表单之间矛盾

- 复现：Our Buses/首页写“13 to 57 seaters”；联系表 `Type of Bus` 只有 `12 Seater Bus` 和 `21 Seater Bus`。
- 观察：Our Buses 页面只有笼统舒适/保养说明，没有把 13–57 座拆成可选车型，也未说明行李、自行车/雪具、无障碍、适用场景或人数建议；Bus Tours 多为长段描述，缺少典型路线、时长、包含/不包含、价格或报价影响因素。
- 影响：高客单询价前最重要的“是否适合我的团、需要提供什么、费用为何变化”无法在页面自助判断；矛盾选项还可能让 30–57 人团体误以为不可服务。
- 最小修正方向：一页呈现容量区间/车型卡、典型用途、服务范围、报价由哪些变量组成，并把表单改为人数优先或与真实车队一致。

### 3. 390px 首屏转化优先级弱，并有可量化横向溢出

- 复现：390x844 首页首屏先显示大 Logo、Facebook、电话、Menu、主图和长标题，询价 CTA 不在首屏；浏览器测得 `documentElement.clientWidth=375`、`scrollWidth=388`，横向溢出 13px。
- 观察：标题在窄屏拆成多行，首段较长；用户需要明显下滑才看到 CTA。菜单本身可展开，联系表在 390px 下未测得横向溢出。
- 影响：移动端高意向访客第一屏没有明确的询价入口；轻微横向滑动削弱完成度与信任感。
- 最小修正方向：首屏压缩品牌区，保留点击拨号和唯一主要询价 CTA；短标题 + 3 个关键证明点；消除造成 13px 溢出的容器/媒体宽度。

## 正向证据

- 首页在 5 秒内能理解“Bright 本地团体包车/旅游”；电话在桌面和移动头部都明显。
- 服务范围广，公开 13–57 座、1980 年开始经营、资质/安全带/雪地驾驶等信任主张。
- 移动菜单可打开，表单字段有可访问名称；真实浏览器未发现站点整体不可用。

## 技术观察（不纳入前三项）

- 浏览器控制台可复现两个字体文件 404：`OpenSans-CondBold-webfont.woff2` 与 `OpenSans-CondLight-webfont.woff2`，浏览器会回退字体。
- 首页存在指向 `tours.html#airport-transfers` 的旧链接口径，而真实内容页是 `bus-tours.html`；需在下一阶段逐项验证是否形成 404。
- `squirrel` surface 抓到验证页而非真实内容，报告 `/output/squirrel-surface.llm` 仅作失败层证据，不能引用其 37 分评价商户网站。

## 浏览器证据

- 桌面首页：`output/playwright/desktop/.playwright-cli/page-2026-08-14T12-18-52-793Z.png`
- 桌面联系表：`output/playwright/desktop/.playwright-cli/page-2026-08-14T12-19-08-910Z.png`
- 移动首页：`output/playwright/mobile/.playwright-cli/page-2026-08-14T12-19-33-510Z.png`
- 移动菜单：`output/playwright/mobile/.playwright-cli/page-2026-08-14T12-19-45-485Z.png`
- 移动联系表：`output/playwright/mobile/.playwright-cli/page-2026-08-14T12-20-10-920Z.png`

