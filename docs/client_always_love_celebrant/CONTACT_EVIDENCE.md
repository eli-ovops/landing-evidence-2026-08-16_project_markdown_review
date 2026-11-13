# CONTACT EVIDENCE

> 状态：待 PMO 验收  
> retrieved_at：2026-08-14  
> 合规边界：只读公开来源；未发送、未 SMTP 探测、未猜测邮箱、未登录社交平台

## 有效联系人

| 字段 | 结果 | 证据 | 置信度 | 缺口 |
|---|---|---|---|---|
| 姓名 | Victoria Smith-Webb | [官网 About](https://mudgeecelebrant.com.au/about/) | High | 无 |
| 业务角色 | Always Love 的具名 celebrant/个人品牌主理人 | 官网第一人称；[本地婚礼目录](https://riverlearetreatmudgee.com.au/mudgee-wedding-servi/always-love-celebrant-services/) | High（业务身份） | 最终采购/网站审批权未确认 |
| 公开商业邮箱 | `[REDACTED_EMAIL]` | 官网首页 DOM 的 `mailto:`；本地婚礼目录 Contact | High（公开来源） | 未验证收件、阅读或回复 |
| 电话 | `0427 720 212` | 官网、Yellow Pages、True Local、本地目录 | High | 未拨打 |
| 官方 Instagram 链接 | `https://www.instagram.com/victoriasmithwebbcelebrant/` | 官网页头/页脚直接链接 | High（账号归属链接） | 因本任务禁止登录，未核近 90 天帖子；不把未核验写成活跃 |
| 官方 Facebook 链接 | `https://www.facebook.com/mudgeecelebrant` | 官网页头/页脚直接链接 | High（账号归属链接） | 未登录、未核活跃度 |

## 邮箱来源链

1. Playwright 无登录实测首页 footer 可访问名为 `[REDACTED_EMAIL]` 的链接，其 `href` 为同一 `mailto:` 地址。来源：[官网](https://mudgeecelebrant.com.au/)，retrieved_at=2026-08-14。
2. Riverlea Retreat Mudgee 的公开婚礼供应商目录也列出同一邮箱、电话与官网。来源：[目录页](https://riverlearetreatmudgee.com.au/mudgee-wedding-servi/always-love-celebrant-services/)，retrieved_at=2026-08-14。
3. 这是 ISP 域邮箱，但被明确发布在商业官网/商业目录中，因此本报告只将其认定为“公开业务联系地址”，不推断私人用途。

## DNS / MX

- `bigpond.com` 只读 DNS 查询返回：`10 extmail.bigpond.com.`
- `mudgeecelebrant.com.au` 只读 DNS 查询返回：`0 mx01.mudgee.host.`
- 结论：两个域均存在 MX 路由。候选邮箱使用的是 `bigpond.com`，故真正相关的验证是 bigpond.com MX present。
- MX 只证明域存在收信路由；**不证明该具体邮箱存在、可投递、有人阅读或适合发送**。

## Local SMB / 合规判断

- 联系信息来自商户官网与本地商业目录，有 URL 与采集日期；没有来自数据泄露、猜号、LinkedIn 批量抓取或联系人市场。
- 未保留 Google Maps Place ID，未批量抓取地图。
- 未发送邮件/DM/电话，未提交官网表单。
- 后续若要联系，必须由当前用户对具体渠道和目标另行授权，并在发送侧处理身份、退订/隐私说明及澳大利亚适用的 spam 合规；本报告不构成法律意见。

## 联系硬门槛

**PASS（基于公开邮箱 + MX）**。不依赖 Instagram 活跃度。Instagram 近 90 天状态保持 **未验证**。

