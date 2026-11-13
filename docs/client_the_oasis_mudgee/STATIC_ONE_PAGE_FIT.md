# The Oasis Mudgee｜纯静态单页适配

## 门禁结论

| 维度 | 结论 | 置信度 | 条件 |
|---|---|---|---|
| Static-only fit | **YES，条件成立** | Medium-High | 页面只承载长期稳定的品牌、服务理解、信任、地点和联系。 |
| Backend dependency | **NONE for our page** | High | 不建数据库、CMS、后台、账号、自建预约、支付、电商或服务端表单。 |
| Content stability | **稳定核心存在；运营细节高度动态** | High | 稳定核心与 Timely/IG 动态内容必须分层。 |
| Ongoing content owner | **CLIENT；我方 NONE** | High | 客户一次性确认稳定内容；后续变更属于另行报价，不承诺持续更新。 |
| External-system boundary | **Timely only as final action; social/map/contact links optional** | High | 我方不登录、配置、定价、排班、维护或保证第三方可用性。 |

## 可放入静态页的稳定内容

- 品牌定位与 Mudgee 门店地点。
- 三个高层服务家族及各自解决的稳定需求，不列完整动态目录。
- founder Gabrielle 的稳定品牌故事（须客户确认仍准确）。
- 团队级的资质/训练表述（必须由客户给出准确措辞和证据；不自行推导资格）。
- 经客户授权的少量长期护理结果、常见顾虑、服务流程与精选评价。
- 正确电话、公开邮箱、地址、可选地图及官方 Instagram。
- 最终 “View live services & availability / Book with Timely” 外链。

## 必须留在 Timely / IG 的动态内容

- 每项治疗的实时名称、价格、时长、附加项和组合。
- 各员工可提供的具体项目、人员排班、休假、回店状态和 last-minute slots。
- 可约日期/时段、客户登录、支付、取消规则和预约账户。
- 限时活动、促销、新品、库存、临时护理空档和日常社交内容。

## 内容波动判断

- 官方 IG 最近内容包含 Gabrielle 回店、多个团队成员、临近空档、活动和护理结果，证明人员与 availability 是高频运营内容。
- About 页还列出 cosmetic nurse、hair dresser、naturopath、iridologist 等角色；是否仍全部在店未知，不应未经确认固化到新静态页。
- Timely 公共页展示至少 13 个服务组，说明具体服务目录比官网三大类更细，可能随定价/人员/设备调整。
- 因此：**静态页不能承担完整美容菜单或完整团队名册，但可以承担稳定的三大结果类别和品牌信任。**

## 外部系统边界

```text
静态单页
  ├─ 品牌 / 服务家族 / 信任 / 地点 / 联系（我方一次性交付）
  ├─ tel: / mailto: / 地图 / Instagram（纯链接）
  └─ Timely（客户既有外部系统）
       ├─ 动态服务目录与价格
       ├─ staff / availability
       ├─ 客户登录与预约
       └─ 支付、取消及账户规则
```

## 会推翻适配的条件

- 客户要求页面显示或持续同步实时价格、完整服务菜单、员工名册或 availability。
- 客户要求我方登录/配置/维护 Timely，或承担第三方故障与数据准确性。
- 客户要求 CMS、服务端表单、支付、电商、库存、礼券或会员账号。
- 访客的主要选择必须依赖每位员工、每项疗程和实时价格，且客户拒绝把这些留在 Timely。

命中任一项：`HOLD`；若为不可谈判的核心需求：`DROP`。

