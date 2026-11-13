# 证据台账

所有互联网来源均记录 `retrieved_at=2026-08-14`。来源等级只表示直接性；官网营销主张只能证明“公开这样宣称”，不能证明实际运行绩效。

## 来源

| ID | 来源与 URL | 层级 | 用途/边界 |
| --- | --- | --- | --- |
| SRC-001 | 官网首页 https://www.brightbustours.com.au/ | A（主体公开页） | 定位、服务、13–57 座、1980 年、CTA、电话/邮箱；营销主张未独立审计 |
| SRC-002 | Bus Tours https://www.brightbustours.com.au/bus-tours.html | A | 服务场景、路线与长文结构 |
| SRC-003 | Our Buses https://www.brightbustours.com.au/our-buses.html | A | 13–57 座、车辆舒适/安全主张 |
| SRC-004 | Contact https://www.brightbustours.com.au/contact.html | A | Frank、电话、邮箱、表单字段、12/21 座选项 |
| SRC-005 | Buckley's Guide 2026 https://buckleysguidesaustralia.com.au/wp-content/uploads/2025/12/BGA2026-108PAGESCOVER-Art-web.pdf | C（地区指南/广告） | PDF 页 105（印刷页 103）完整广告：服务、13–57 座、电话、邮箱；证明 2026 投放，不证明订单或营业许可 |
| SRC-006 | Tasman Holiday Parks https://tasmanholidayparks.com/au/retreat-on-delany/ | C（当前合作/目的地页面） | 当前列出 Bright Bus Tours 酒吧/酒庄包车、by appointment、35 Delany Ave |
| SRC-007 | SBS/AAP https://www.sbs.com.au/news/article/vic-fire-threat-escalates-with-cool-change/gzu1d59uo | C（媒体） | Frank Ivone 的本地性与另一经营身份；年代较早，不证明当前 Bus Tours 所有权 |
| SRC-008 | DNS MX `bigpond.com` → `10 extmail.bigpond.com.` | A（实时 DNS） | 域级邮件接收基础设施；不证明单地址存在或会读信 |
| SRC-009 | 无登录 Playwright 桌面/390px 快照，见 `output/playwright/` | A（实际测试） | 可访问性、CTA 目标、表单选项、移动布局、控制台字体 404 |
| SRC-010 | `output/squirrel-surface.llm` | A（失败层测试） | 只证明 crawler 命中验证页；内容/SEO评分无效，不用于客户判断 |

## 事实与判断

| ID | 类型 | 陈述 | 来源 | 置信度 | 推翻条件 |
| --- | --- | --- | --- | --- | --- |
| FACT-001 | observed | 正常真实浏览器在桌面与 390px 均能进入官网内容 | SRC-009 | 高 | 多网络/时段重复正常浏览器失败且排除本地环境 |
| FACT-002 | observed | 首页的 Quote 与 Book Online CTA 都到同一联系表 | SRC-001, SRC-004, SRC-009 | 高 | 网站更新为不同路径/真实在线预订 |
| FACT-003 | observed | 官网称 13–57 座；表单只提供 12、21 座 | SRC-001, SRC-003, SRC-004, SRC-009 | 高 | 表单/车队口径更新并一致 |
| FACT-004 | observed | 390px 首页 `clientWidth=375`、`scrollWidth=388`，溢出 13px；首屏无询价 CTA | SRC-009 | 高 | 同设备宽度复测不再出现 |
| FACT-005 | observed | 官网与 2026 指南同列电话、邮箱和 13–57 座 | SRC-001, SRC-005 | 高 | 指南被撤回/更正或官网更换主体 |
| FACT-006 | observed | `bigpond.com` 有 MX | SRC-008 | 高（域级） | DNS 记录撤销 |
| FACT-007 | observed | Tasman 当前页面列出该活动为 by appointment | SRC-006 | 中高 | 合作方页面过期或商户否认 |
| JUD-001 | inferred | 商户当前高概率仍经营 | FACT-001, FACT-005, FACT-007 | 高（非监管级） | 官方停业/注销或商户直接确认停业 |
| JUD-002 | inferred | Frank 是本地、可直接触达的经营相关人，但最终决策权未确认 | SRC-004, SRC-007 | 中 | 商户/登记资料显示其无采购权 |
| JUD-003 | inferred | 仅在不含表单、价格/可用性、日历和后台时，纯静态一页可独立解决“品牌、服务匹配、信任与直接联系”价值 | FACT-001, FACT-002, FACT-004, FACT-005 | 中 | 商户要求站内线索采集、实时信息、后台或持续更新，或稳定内容不足 |
| JUD-004 | inferred | AU$800 有合理回收路径，但支付意愿未验证 | SRC-001, SRC-005, JUD-003 | 中低 | 毛利/询盘数据表明无回收空间或经营者明确无预算 |
| JUD-005 | inferred | 新产品硬门槛下适配评分从 86 下调至 72，结论为条件 KEEP 而非无条件 KEEP | JUD-003, FACT-002, FACT-003 | 中 | 商户确认内容静态且接受直接链接边界可上调；反之转 HOLD/DROP |

## 搜索边界与未知

- 没有批量抓取 Google Maps，也没有保存 Place ID。
- 未登录 Instagram、Facebook、LinkedIn；未绕 CAPTCHA/WAF。公开搜索未确认近 90 天官方 Instagram。
- 未找到可定位的 ABN/ASIC 记录，法定主体、所有权和最终采购权仍未知。
- 未验证表单提交、电话接通或单邮箱投递；这些需要新的联系/测试授权。
- 没有订单量、客单价、毛利、询盘量、转化率、现有供应商合同或预算数据。
- 未确认内容是否需要高频更新，也未确认商户是否接受无站内表单的直接电话/邮件转化路径；这是纯静态产品的阻断性未知。
- 浏览器初始出现验证页后正常进入；自动化/HTTP crawler 的验证页不能写成网站故障。

## PDF 核验

- 本地只读副本：`tmp/pdfs/Buckleys_Guide_2026.pdf`
- `pdfinfo`：112 页，创建日期 2025-11-13，修改日期 2025-12-03。
- `pdfplumber` 定位：PDF 第 105 页；`pdftoppm` 渲染并人工核对，广告包含 Bright Bus Tours、13–57 座、`0458 922 518`、`[REDACTED_EMAIL]`。
