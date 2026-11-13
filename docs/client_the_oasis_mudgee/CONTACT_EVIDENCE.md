# The Oasis Mudgee｜联系人证据

> 状态：待项目 PMO 验收。没有发送邮件、DM、电话、表单或 SMTP 探测。

## 有效公开联系路径

| 项目 | 结论 | 来源 URL | retrieved_at | 置信度 | 证据缺口 |
|---|---|---|---|---|---|
| 商业邮箱 | `[REDACTED_EMAIL]` 由官方首页、About、Services 页公开。 | https://theoasismudgeee.squarespace.com/；https://theoasismudgeee.squarespace.com/about；https://theoasismudgeee.squarespace.com/services | 2026-08-14 | High（来源） | 未验证具体邮箱账户是否收信；不声称 deliverable。 |
| MX | `yahoo.com` 有 3 条 MX：`mta5/6/7.am0.yahoodns.net`。 | https://dns.google/resolve?name=yahoo.com&type=MX | 2026-08-14 | High（域级路由） | MX 只证明域可路由，不证明此邮箱存在或会回复。 |
| Instagram | 官方站指向 `@theoasismudgeee`；OpenCLI 读到近 90 天且近 6 个月持续活动。 | https://www.instagram.com/theoasismudgeee/ | 2026-08-14 | High | 仅只读最近 12 条，不代表完整经营数据。 |
| 电话（官网页脚） | 可见文本 `637291 82`，链接为 `tel:02 637 291 82`，均少一位。 | https://theoasismudgeee.squarespace.com/ | 2026-08-14 | High | 明确不可直接作为最终号码。 |
| 电话（官网 Services 正文） | “call 6372 9182” 给出完整 8 位本地号码。 | https://theoasismudgeee.squarespace.com/services | 2026-08-14 | High | 同页页脚仍错误，官网内部冲突。 |
| 电话（Timely） | 公开选择服务页显示 “please call 6372 9182”。 | https://bookings.gettimely.com/theoasismudgee/book | 2026-08-14 | High | 未拨打。 |
| 电话（二级交叉） | Cylex 与当前目录聚合均列 `(02) 6372 9182`。 | https://www.cylex-australia.com/mudgee/personal-care-services/；https://hairdressersmudgee.pages.dev/ | 2026-08-14 | Medium | 二级目录可能过期，不替代客户确认。 |

## 联系结论

- **有效联系人：** `[REDACTED_EMAIL]`（公开商业语境邮箱；MX 存在但邮箱账户未投递验证）与官方 Instagram `@theoasismudgeee`（近 90 天活跃）。
- **最可能正确电话：** `(02) 6372 9182`，因为官网 Services 正文、Timely 与两个目录一致。
- **仍需硬确认：** 在任何页面、Demo 或外联脚本使用电话前，必须由客户/具名决策人确认最终号码；当前官网首页与页脚错误不能被自动纠正为事实。
- **合规边界：** 免费 Yahoo 邮箱虽为官方公开商业联系渠道，仍不做邮箱猜测、SMTP 探测或个人画像；若未来外联，需记录来源/日期、合法利益依据、身份与退订机制。

