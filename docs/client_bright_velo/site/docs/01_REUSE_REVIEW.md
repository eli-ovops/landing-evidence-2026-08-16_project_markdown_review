# 可复用方案核查（L0 本地概念站）

更新：2026-08-14。目的：在实现前确认是否应复用成熟方案，而非把功能性酒店网站替换为不必要的重型预订系统。

| 候选 | 证据与许可证 | 判断 |
|---|---|---|
| [QloApps](https://github.com/Qloapps/QloApps) | OSL-3.0；酒店 PMS/预订后台，14k+ GitHub stars（核查日） | 不采用：范围远超单页概念站，且会引入住宿库存、支付、后台与迁移风险。 |
| [Codrops Background Scale Hover Effect](https://github.com/codrops/BackgroundScaleHoverEffect) | MIT；交互实验 | 不复制代码：仅借鉴“克制的图片/背景层次变化”这一抽象方向，以原生 CSS 自行实现。 |
| 通用 hotel-template 仓库 | 多数缺乏清晰许可证、维护信号或适配的可访问性/品牌边界 | 不 fork：避免无授权复用和把通用住宿模板伪装成客户成品。 |

## 最小充分实现

- 本地 Vite + React 静态单页；不接数据库、CMS、支付、账户或真实表单。
- 将“可用性/预订”导向现有 RMS；餐饮导向现有 Basils 页面；团体咨询导向当前联络页。
- 只使用原创 CSS 几何光影和文字，不复制 Bright Velo 既有照片、Logo、页面文案或第三方模板代码。

## 复核条件

若客户以后明确要求库存、价格、支付或内容编辑，先重新评估现有 RMS 的嵌入/API/条款与 CMS 方案；本原型不得被当作该类授权。
