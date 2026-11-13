# 联系与决策权证据

## 有效公开联系渠道

| 渠道 | 值 | 来源 | retrieved_at | 证据状态 | 限制 |
|---|---|---|---|---|---|
| 商业邮箱 | `[REDACTED_EMAIL]` | https://www.photographymudgee.com.au/ ; https://mudgee.travel/functions-weddings/ | 2026-08-14 | 公开来源 High | 旧站链接协议误写为 `maitlo:`；邮箱属于已结束商业名称的旧入口，是否仍有人读取未知。 |
| MX | `photographymudgee.com.au` 有 MX，目标为 `mail.photographymudgee.com.au` | 只读 DNS `dig +short MX photographymudgee.com.au` | 2026-08-14 | High | MX 只证明域存在收信路由，不证明具体邮箱可投递或有人阅读。 |
| Instagram | `@colboydphotography` | https://www.instagram.com/colboydphotography/ | 2026-08-14 | High | OpenCLI 只读最近 12 条；未发 DM。 |
| 电话 | `0414 738 824` | 旧站、当前站/目录、本地婚礼目录 | 2026-08-14 | High | 未拨打。 |

本轮没有 SMTP 探测、发送验证邮件、调用邮箱验证服务、提交表单、打电话或发私信。

## Instagram 近 90 天活跃证据

- OpenCLI 返回 2026-05-15、05-22、06-06、06-27、07-05、07-08、07-21、07-22 等公开帖。
- 内容涵盖婚礼季、婚礼行业奖项/入围、作品与本地活动，足以满足“近 90 天活跃官方 IG”的联系硬门槛。
- 账号用户名、显示名、电话/业务描述与站点互相一致。
- 限制：互动数和发布时间为平台公开快照；未验证每项奖项主张，也不推导成交。

## 邮箱来源与风险

- 官网正文公开显示该邮箱，Mudgee Travel 的公开婚礼供应商页也列出同一邮箱；来源谱系成立。
- 真实 Chromium 验证：可见文本正确，但 `href` 是 `maitlo:[REDACTED_EMAIL]`，点击不会按标准 `mailto:` 打开邮件客户端。
- 由于旧商业名称于 2024 年结束，邮箱应标为“公开但使用状态未知”，不能写成已验证可达。
- 若未来获联系授权，合规做法是优先使用公开商业渠道，并保留来源、日期、用途和退出机制；本轮不执行联系。

## 决策权判断

| 主张 | 类型 | 证据 | 置信度 | 推翻条件 |
|---|---|---|---|---|
| Col 是业务所有者/直接商业决策者 | 推断 | ABR 为个人独资；商业名称 Col Boyd Photography current；站点以第一人称运营 | High | 发现实际业务已转让或网站/品牌由其他实体控制。 |
| Col 可单独批准网站替换 | 未知 | 没有账户、合同或客户原始回答 | Low/Unknown | 客户或供应商出示明确控制/授权。 |
| 现有供应商可能参与网站决策 | 推断 | 当前站署名 Sheridan Burns Studio，且公开 testimonial 表示继续使用其服务 | Medium-High | 现有合作已结束或只涵盖一次性设计。 |

## 结论

- 有效联系人：`@colboydphotography` 为当前、近 90 天活跃的官方渠道；`[REDACTED_EMAIL]` 为公开商业邮箱且域有 MX，但属于旧品牌入口并存在错误链接，状态需降级。
- 决策权：业务决策权很可能在 Col；直接网站控制权和既有供应商审批路径未证实。
