# 联系与决策权证据

检索日期统一为 `retrieved_at=2026-08-14`。只记录公开商业入口；未发送、未拨打、未提交表单、未做 SMTP 探测。

| 渠道/人物 | 观察事实 | 来源 | 置信度 | 推翻/降级条件 |
| --- | --- | --- | --- | --- |
| Frank Ivone | 官网 Contact 页把 Frank Ivone 列在商户名称下方，并紧邻电话与邮箱 | https://www.brightbustours.com.au/contact.html | 高（“官网联系人”）/ 中低（“最终决策人”） | 商户或登记资料说明 Frank 不是网站/营销决策人 |
| 电话 `0458 922 518` | 官网与 2026 Buckley's Guide 同号公开 | https://www.brightbustours.com.au/contact.html；https://buckleysguidesaustralia.com.au/wp-content/uploads/2025/12/BGA2026-108PAGESCOVER-Art-web.pdf（PDF 页 105，印刷页 103） | 高（公开商业入口） | 号码停用、转给无关主体或商户否认 |
| 邮箱 `[REDACTED_EMAIL]` | 官网与 2026 地区指南同址公开；`bigpond.com` MX 为 `extmail.bigpond.com` | 同上；DNS `dig MX bigpond.com` | 高（公开来源）/ 中（可投递性） | 单地址退信、商户否认、官网更新；域有 MX 不能证明单地址存在 |
| 联系/预订表单 | 表单公开可见，有姓名、邮箱、电话、车辆、用途、日期、人数、备注和 reCAPTCHA | https://www.brightbustours.com.au/contact.html#contact-form；真实浏览器快照 | 高（表单存在）/ 未验证（提交成功） | 合规授权下的真实提交失败，或商户确认不接收 |
| Facebook | 官网链接到 `facebook.com/frank.ivone.31`，表现为个人名义链接，不是已确认的官方商户主页 | https://www.brightbustours.com.au/ | 中 | 页面公开信息显示其为正式商户主页且近期活跃 |
| Instagram | 公开网页搜索未找到可确认的官方 Bright Bus Tours 账号；因禁止登录，未使用复用登录态的 OpenCLI 深查 | 搜索边界：`site:instagram.com "Bright Bus Tours" Victoria` | 低（“未找到”不是“不存在”） | 商户官网新增链接或找到近 90 天活跃官方账号 |

## 本地/独立决策权

- **事实：** 官网自述商户 based in Bright，并给出单一具名联系人 Frank Ivone；当前 Tasman Holiday Parks 页面把该活动列在 Bright、35 Delany Ave、by appointment。
- **交叉线索：** SBS/AAP 公开报道曾把 Frank Ivone 描述为当地第五代居民和 Eagle Range Estate 业主：https://www.sbs.com.au/news/article/vic-fire-threat-escalates-with-cool-change/gzu1d59uo
- **推断：** Frank 很可能是本地经营相关人，且采购沟通链较短；未发现连锁/集团品牌控制迹象。
- **限制：** 没有查到可定位的 ABN/ASIC 法定所有权记录，也没有商户直接确认其网站预算权。结论只能是“本地决策可达性中等”，不能写成“已确认 Owner”。

## 邮箱合规边界

- 这是公开商业场景地址，但属于 ISP 域名而非商户自有域名。
- 仅保留来源 URL、日期和域级 MX；不猜测其他地址，不做 SMTP，不发送测试邮件。
- 若未来获联系授权，澳大利亚商业触达仍需明确发件主体、相关性与退出方式；本文件不是发送授权或法律意见。

