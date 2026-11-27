# PrototypeHub

**轻量、可自托管的原型管理与交付平台。**

PrototypeHub 面向产品经理、UI/UX 设计师、研发与测试团队，将设计工具导出的静态 HTML 原型整理为可管理的项目与版本，让需求评审、原型预览和交付沟通拥有统一入口。

**导出 HTML → 上传 ZIP 或选择 HTML 文件夹打包 → 在线预览与 Inspect → 可控分享 → 研发与测试交付**

## 项目导航

| 仓库 | 职责 | 从这里开始 |
| --- | --- | --- |
| [proto-bridge](https://github.com/prototype-hub/proto-bridge) | 后端：项目与版本、ZIP 校验与存储、原型交付、分享及系统管理 API | [快速开始](https://github.com/prototype-hub/proto-bridge#快速开始) · [配置与部署](https://github.com/prototype-hub/proto-bridge#服务器部署) |
| [proto-bridge-ui](https://github.com/prototype-hub/proto-bridge-ui) | 前端：管理界面、页面树、预览与元素检查、分享和个人中心 | [本地体验](https://github.com/prototype-hub/proto-bridge-ui#五分钟启动) · [连接后端](https://github.com/prototype-hub/proto-bridge-ui#连接真实后端) |

产品名称为 **PrototypeHub**，前后端工程分别沿用 `proto-bridge` 与 `proto-bridge-ui`，前端部分文档中也使用 ProtoBridge 名称。

## 能做什么

- **集中管理原型**：按项目维护逻辑版本，上传完整 HTML ZIP 或为同一版本上传新修订并保留历史；也可选择 Axure 等工具已导出的 HTML 文件夹，由浏览器打包后确认上传。
- **预览与检查**：在浏览器中浏览与查找页面、体验交互，复制固定修订的当前页面链接；使用 Inspect 查看和复制元素属性、CSS、HTML、图片及 SVG 信息。
- **修订比较与质量体检**：人工并排比较同一版本的两份固定修订，查看页面与文件差异；检查包内静态资源、内部链接和路径问题，下载 JSON、Excel 或 Word 报告。
- **资产与文案交付**：按固定修订选择并导出原始图片、SVG 和对账清单；为固定页面提取及维护文案、业务词汇与需求链接，导出 CSV 或 JSON。
- **受控分享**：通过独立链接分享原型，默认固定修订，也可选择跟随最新；设置密码与有效期，并支持编辑、暂停与恢复、链接轮换及永久撤销，服务于评审与交付。
- **页面反馈**：围绕固定修订页面收集客户反馈，支持根页面几何批注、固定 DOM 身份与显式包内 frame 定位、文字及单张图片投稿、网页回复、内部备注、解决与重开、线程链接、成员负责人及跨页总览。
- **评审与交付**：对固定修订显式批准与发布，维护区域功能说明和六类人工验收记录，组装并导出 Markdown/离线 HTML 说明书。
- **任务演示**：按固定修订真实页面编排目标、前置条件和讲解步骤，排练或按原分享权限开放只读脚本。
- **统计概览**：查看权限范围内的项目、逻辑版本及有效分享数量，以及近 7/30 天的分享访问趋势和项目排行。
- **系统管理**：提供用户、角色、组织、职位、菜单与按钮权限、数据字典、品牌配置、个人中心及日志管理。
- **自主部署**：基础运行使用 PostgreSQL 与本地文件存储；Redis、Elasticsearch 可按需要启用，支持 JAR、Docker 与 Nginx 部署。

### 当前使用边界

平台接收静态 HTML 原型包，不提供设计源文件编辑、Figma 原生文件导入或多人实时协同编辑。项目访问由**成员范围与平台权限共同控制**，支持所有者、编辑者和查看者角色；管理员例外也按服务端权限校验。项目和版本列表支持服务端分页、名称筛选与排序，返回记录和总数均限定于当前用户的权限范围与筛选条件。

前后端需配套升级并停止旧写入和清理节点：旧内部匿名预览凭证失效，历史项目需显式执行[归属迁移与认领](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/DATA.md#项目归属迁移与认领)，旧逻辑版本需显式完成[修订预检与迁移](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/DATA.md#不可变修订与旧内容迁移)。升级前在同一维护窗口联合备份数据库、全部历史原型与系统文件；迁移后旧分享绑定当时仍存的内容，过去已被覆盖的历史无法恢复。升级前已有的删除记录也按原删除时间计算 30 天，已到期数据可能立即进入清理，回收站不能代替备份。

分享可固定指定历史修订，或在每次打开、验证密码时解析一次最新修订；同次已授权的页面树、HTML 与资源保持同一快照，后续上传不会使当前预览漂移。配置变更使旧资源授权失效，暂停后恢复不会复活旧授权；轮换使旧链接失效，永久撤销不可恢复。公开分享与项目成员授权独立，移除成员后仍需单独撤销公开分享；浏览器已接收的内容无法远程收回。

前端 Mock 用于本地体验与契约回归，真实后端联调和生产部署需按目标版本及环境验收。详细兼容边界以两个仓库的 README 和发布文档为准。

## 功能清单与开发计划

核对日期：**2026-11-27**。以下清单展示当前已实现的功能与后续开发计划，按基础版本和高级版本分别维护。✅ 表示已完成，🔄 表示部分完成，🚧 表示开发中，🗓 表示规划中；规划内容不代表已上线或确定的发布时间。

| 版本 | 已完成 | 部分完成 | 开发中 | 规划中 | 完整清单 |
| --- | --- | --- | --- | --- | --- |
| 基础版本 | 18 项 | 5 项 | 0 项 | 0 项 | [基础版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md) |
| 高级版本 | 5 项 | 1 项 | 0 项 | 11 项 | [高级版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_ADVANCED.md) |

### 当前进展

- **项目成员与数据隔离**：所有者、编辑者、查看者角色、成员增改删、待认领项目处理及服务端权限隔离已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/9)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/14)。项目和版本列表现已支持服务端分页、名称筛选与排序，记录和总数均按权限与条件过滤，用量独立查询；分页实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/13)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/18)。
- **修订历史与版本对比**：已保留不可变历史、固定修订预览、并发更新冲突提示及[固定页面定位](https://github.com/prototype-hub/proto-bridge-ui/blob/main/docs/public/API.md#固定页面链接与页面目录)。同一逻辑版本的两份固定修订现可人工双窗并排预览，查看页面与文件的新增、删除、变化和不变统计，两个差异列表独立分页；比较实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/18)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/23)。比较依据路径与文件摘要，不代表自动视觉比较；页面查找仍只覆盖授权页面树的名称和路径。
- **原型包质量检查**：历史修订已提供“质量体检”，检查入口、清单文件存在性与支持的本地 HTML/CSS 静态引用，报告缺失资源、失效内部链接和路径问题。初始实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/19)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/24)，JSON、真实 Excel/Word 报告及导出前权限复核已配套合入[后端](https://github.com/prototype-hub/proto-bridge/pull/54)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/68)。各格式保留同一扫描全部已返回结果和限制，不重新扫描；不包含企业模板或批量报告，具体范围见[修订对比与质量检查范围](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md#修订对比与质量检查范围)。
- **项目整理与恢复**：项目与版本已支持软删除、回收站及逐项恢复；统一回收菜单的项目、版本两个标签页已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/23)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/28)，按当前权限查询与恢复，可在授权的活动项目范围筛选版本。恢复保留原 ID、历史与文件；项目沿用已占名额，版本恢复重新检查当前版本容量，旧分享与内部授权不复活。分组、业务标签、收藏、封面管理和归档仍待实现。
- **回收站保留期**：各条记录自删除起固定保留 30×24 小时，到期即不可恢复，即使文件仍在磁盘上；后台通过持久队列异步回收原型快照，实际磁盘回收可延后。后端规则已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/17)，保留期提示与配套契约回归已合入[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/22)；需配套更新，避免旧版本“持续保留”提示造成误解。操作边界见[回收站与逐项恢复](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/API.md#回收站与逐项恢复)及[基础功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md#回收站与保留期)。
- **分享管理增强**：已支持编辑说明、密码与有效期，暂停与恢复、链接轮换、永久撤销，固定指定历史修订或跟随最新；并发配置冲突时刷新核对，不自动覆盖。相关实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/12)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/17)，授权与撤销行为见[分享生命周期](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/API.md#分享生命周期)。
- **访客身份与邀请**：分享可选邮箱验证码或显式获准的未验证身份，两类访客分别分页及启停；未验证入口已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/24)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/29)。固定分享的定向邀请已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/25)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/30)，手动复制链接，指定邮箱仍须重新验证。访客停用不等于撤销匿名分享；基础验证码与可选高级业务通知分别管理，部署需按[邮箱身份与 SMTP](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/OPERATIONS.md#邮箱身份与smtp)验证真实收件。
- **固定页面反馈**：文字线程、网页回复、内部备注隔离、解决/重开、线程深链、私有图片回复与成员负责人已实现。初始投稿附图已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/31)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/36)，根页面打点与矩形/椭圆圈选已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/32)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/37)。跨页总览及状态、成员责任组合筛选已合入[后端总览](https://github.com/prototype-hub/proto-bridge/pull/33)、[前端总览](https://github.com/prototype-hub/proto-bridge-ui/pull/38)、[后端责任筛选](https://github.com/prototype-hub/proto-bridge/pull/34)和[前端责任筛选](https://github.com/prototype-hub/proto-bridge-ui/pull/39)；客户查看本人或当前有效人工授权范围内的对客线程，分派不授予权限或发送通知。固定 DOM 身份与显式包内 frame 定位另已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/63)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/78)，不推断动态重复元素或跨修订迁移；定位与图片限制见[页面反馈边界](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md#固定页面反馈边界)。
- **历史反馈人工授权**：所有者或有效管理员可经线下核实，将旧未验证访客在原分享及固定修订内的历史对客反馈授权给已有启用邮箱访客，并记录依据、授权与撤销。已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/41)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/52)；保留原作者，不合并身份或恢复旧会话，内部备注仍隔离。具体范围见[人工核实后的历史评审授权](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/API.md#人工核实后的历史评审授权)。
- **固定页面工作项与文案**：页面手动关联 HTTP(S) 工作项及备注已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/35)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/46)。固定页静态文案提取、人工维护、业务词汇与需求链接、分页筛选及全页 CSV/JSON 导出已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/42)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/53)。上传新修订不迁移旧引用或清单；页面与需求关系仍待实现，提取范围见[固定页文案清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md#固定页文案清单)。
- **权限内内容搜索**：文案、修订资料与页面反馈可分别分页检索，限定项目、版本或固定修订，并回到原内容，已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/50)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/62)。检索仅覆盖已收录内容，反馈仍要求项目编辑权限；文档正文范围见[基础功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md#权限内内容搜索)。
- **原始资产导出**：固定修订的独立图片与 SVG 可按路径搜索、跨页选择，下载原文件、所选或全部 ZIP 及 JSON 对账清单，已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/40)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/51)。仅供有权内部成员使用，不包含内联或外部资源；组件映射与 Token 规范仍待实现，详见[原始资产导出边界](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md#原始资产导出边界)。
- **Inspect 测距与页面样式**：根文档 A/B 元素测距及有界颜色、字体汇总已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/44)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/56)。结果为运行时 CSS 快照，扫描达到预算会显示部分结果，失效后需重新选取或读取；不跨 frame 或 Shadow DOM，也不代表设计 Token。
- **修订资料与人工来源**：标准 HTML ZIP、文件夹导入及其来源关联实际固定修订，支持私有图片与文档、分类分页、来源维护及鉴权下载，已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/48)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/60)。有界文档正文提取、只读阅读及搜索已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/53)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/66)。独立 HTTP(S) 链接维护、图片尺寸切换及 PDF 按页静态查看已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/56)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/71)。来源为人工声明，不抓取链接或验证工具身份；Office 不原生渲染，正文提取不识别扫描图片，详见[修订资料边界](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md#修订资料与来源边界)。
- **固定页面视口自测**：已支持人工设置 CSS 视口、记录各类场景的预期与观察、步骤、文字证据及结果，并按分类和结果分页筛选，已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/46)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/59)。六类状态/异常记录由成员人工填写，不代表真机、自动截图或正式批准。
- **固定页面交付**：草稿、待交付、研发中、已完成四态，人工说明、可选成员负责人及分页筛选已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/55)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/69)。记录属于固定修订，不随新修订复制；分派不授予权限，也不等于审批、反馈解决或通知，详见[页面交付边界](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md#固定页面人工交付状态)。
- **区域说明与交付说明书**：固定修订根页面可维护人工区域功能说明，已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/61)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/76)。选真实页面、说明、资料、图片及人工自测记录组装，会话内编辑并导出 Markdown ZIP 或离线 HTML 已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/62)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/77)；不自动推断业务语义、截图或生成审批结论，范围见[基础功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md#固定修订交付说明书)。
- **基础评审与发布**：固定修订的显式批准、撤销、发布、撤回及历史已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/64)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/79)。客户沿原分享权限只读脱敏状态；浏览、反馈解决或页面人工交付不会自动批准，发布不部署、不改变分享或回收保留期，详见[批准与发布边界](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md#固定修订批准与发布)。
- **固定修订演示脚本**：任务目标、前置与人工重置说明、有序页面讲解、成员排练及按权只读分享已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/65)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/80)。对客开放默认关闭，开启后沿已有同修订分享授权；不自动控制原型或同步主持，视频时间点、可用性任务与问卷仍待实现，详见[演示脚本边界](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md#固定修订演示脚本)。
- **本地运行诊断**：管理员可主动读取五类运行摘要并导出当前同一脱敏 JSON，已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/60)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/75)；只读无遥测、不发信或触发清理，不等于备份完整性或安全扫描，详见[诊断边界](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md#本地运行诊断)。
- **界面体验**：已改进[反馈草稿与列表详情](https://github.com/prototype-hub/proto-bridge-ui/pull/40)、[批注抽屉](https://github.com/prototype-hub/proto-bridge-ui/pull/43)、[分享工具栏与身份流程](https://github.com/prototype-hub/proto-bridge-ui/pull/44)、[反馈总览](https://github.com/prototype-hub/proto-bridge-ui/pull/45)及[项目、版本和历史工作区](https://github.com/prototype-hub/proto-bridge-ui/pull/46)，完善 390px 窄屏布局、键盘操作与草稿保护。[分享管理体验](https://github.com/prototype-hub/proto-bridge-ui/pull/70)补齐响应式布局与冲突保稿；[预览与下载修复](https://github.com/prototype-hub/proto-bridge-ui/pull/73)使相同授权地址重试时实际重载页面，并避免成功二进制下载被整包解码成文本，[后端](https://github.com/prototype-hub/proto-bridge/pull/58)同步修复资源传输异常的重复响应处理。
- **内部预览授权**：采用绑定固定修订的 5 分钟授权，到期后需重新申请；成员变更会使旧授权失效，上传新修订后旧授权仍指向原修订直至到期。公开分享单独管理，移除成员不会自动撤销已有分享；已渲染或下载的内容无法远程清除。
- **容量与用量**：免费默认同一部署总计 5 个项目、每项目 5 个逻辑版本，提供真实用量展示与幂等创建。所有保留项目（含回收站与到期待清理项目）均占项目名额，项目恢复沿用名额；只有依赖数据和文件清理完成、项目根记录移除后才释放。版本软删除释放逻辑版本名额，恢复按当前有效容量重新准入；上传新修订不增加逻辑版本用量，历史超额活动内容保留。统一计量与恢复规则已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/49)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/61)，[公共权益接口](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/API.md#installation-credential-verification)分别返回免费权益、已验证声明与实际容量。
- **统计与分享访问**：已支持权限内项目、逻辑版本及有效分享数量，近 7/30 天访问趋势与最多 10 个项目的排行，已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/37)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/48)。只记录成功打开分享外壳的访问，同票重放去重，同次切页、内部预览与资源请求不计；刷新重新打开可产生新访问。历史未采集与真实零值分别显示，访问次数不代表人数；尽力采集失败不阻断浏览，也不代表已实现用户研究或行为漏斗。
- **安装凭证与永久容量**：已提供安装请求下载、导入验签、离线签发换证、永久容量及 30 天高级试用。项目与每项目版本两项容量是独立的完整绝对上限，不叠加免费 5/5；缺少有效凭证或未加载高级容量模块时按免费容量执行。首次成功导入有效 schema 3 试用凭证即开始 30×24 小时计时，重放、换证或重启不重置；容量与高级 feature 授权分别判定。公共接口与状态展示已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/51)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/63)，完整范围见[离线授权实现边界](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_ADVANCED.md#离线授权实现边界)。
- **高级同步、视觉与登录**：已实现 Windows Java 客户端监听 HTML 导出目录并向已有逻辑版本上传稳定快照、受限固定视口的异步截图与像素差异，以及单一 OIDC 的既有账号映射与会话撤销。公共配套入口分别为[客户端](https://github.com/prototype-hub/proto-bridge-ui/pull/64)、[比较工具](https://github.com/prototype-hub/proto-bridge-ui/pull/65)与[登录工具](https://github.com/prototype-hub/proto-bridge-ui/pull/67)，客户端现已提供当前用户 MSI 构建及同族手动升级、修复与卸载状态保留，验证仍限 Windows 10 x64 虚拟机，未签名或正式分发。具体部署条件与验证范围见[高级功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_ADVANCED.md)。Axure 本地预览一键采集仍待技术验证，当前继续使用 HTML 导出目录或手工 ZIP。
- **高级通知**：可选高级模块已支持邮件、企业微信与站内通知，按事件规则及显式产品经理绑定选择单渠道或多渠道，并提供模板、订阅、个人收件箱、静默汇总及可靠投递控制。阿里云短信仍待实现；未知结果不盲目重发，已受理渠道不重发，受理不代表送达。基础验证码独立运行，[公共邮件传输](https://github.com/prototype-hub/proto-bridge/pull/57)与[前端讨论扩展入口](https://github.com/prototype-hub/proto-bridge-ui/pull/72)已合并，完整事件、订阅与验证范围见[通知边界](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_ADVANCED.md#通知与可靠投递边界)。
- **网页文件夹上传**：已支持选择 HTML 导出目录、浏览器 Worker 打包、进度与取消，以及 ZIP 回退；打包完成后由用户确认上传。相关实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/8)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/13)，并在[前端体验改进](https://github.com/prototype-hub/proto-bridge-ui/pull/27)中增加逐路径冲突诊断；输入预算与兼容范围见[基础版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md)。
- **账号与预览**：已支持可选“记住我”和经服务端验证的会话恢复，并改进沙箱内嵌套页面的预览兼容性；[前端体验改进](https://github.com/prototype-hub/proto-bridge-ui/pull/27)还包括 390px 窄屏紧凑预览及查询、分页布局调整。[内置超级管理员保护](https://github.com/prototype-hub/proto-bridge/pull/47)已补齐有效资源权限及删除、停用和绑定移除保护，普通 ADMIN 仍需显式授权。[会话权限刷新](https://github.com/prototype-hub/proto-bridge-ui/pull/74)在保存角色授权后重新读取资源权限与菜单。原型继续受沙箱隔离，嵌套页面兼容性以实际导出包为准。
- **后端持久化**：已合入 [ORM 查询与结构化 DDL 改造](https://github.com/prototype-hub/proto-bridge/pull/11)，使用框架查询能力和 jOOQ 结构描述；当前配置与验证范围仍为 PostgreSQL，不代表已支持其他数据库。
- **发行与运维**：已完成独立 JAR 启动与重启、双进程配额竞争、数据库与原型及系统文件联合恢复，以及真实后端 Chrome 流程验证。[业务图联合恢复](https://github.com/prototype-hub/proto-bridge/pull/43)已覆盖当时非空的人工授权、文案、访问统计、负责人和几何锚点，另补充[视口自测专项](https://github.com/prototype-hub/proto-bridge/pull/46)与[修订资料专项](https://github.com/prototype-hub/proto-bridge/pull/48)。2026-11-03 已使用真实 Windows 导出的 Axure 包，在 macOS 浏览器验证 ZIP/目录上传、多页交互、Inspect、分享、反馈及独立联合恢复；不代表 Windows 真机或复杂嵌套 frame 验收。[邮件健康检查](https://github.com/prototype-hub/proto-bridge/pull/45)、[反馈焦点恢复](https://github.com/prototype-hub/proto-bridge-ui/pull/57)和[前端依赖修复](https://github.com/prototype-hub/proto-bridge-ui/pull/58)已合入，当次前端生产及全部依赖审计无命中、严格许可材料检查通过。后端官方 Trivy 扫描仍有告警待闭环，许可权属、其他系统与真机、目标部署和镜像验收仍待完成；验证范围见[恢复说明](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md#评审数据与恢复验证)及[后端](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/RELEASE.md)、[前端发布指南](https://github.com/prototype-hub/proto-bridge-ui/blob/main/docs/public/RELEASE.md)。

## 技术栈

| 层次 | 主要技术 |
| --- | --- |
| 前端 | Vue 3、TypeScript、Vite、Ant Design Vue、Pinia、Vue Router、vue-i18n |
| 后端 | Java 21、Spring Boot 3、Spring WebFlux、Project Reactor、hsweb、EasyORM、jOOQ（结构描述与 DDL） |
| 数据与存储 | PostgreSQL、R2DBC、本地文件存储；可选 Redis 与 Elasticsearch |
| 构建、部署与验证 | Maven Wrapper、pnpm、Docker、Nginx、Vitest、Playwright、Testcontainers |

## 开始使用

1. **准备环境**：后端使用 JDK 21 和仓库自带的 Maven Wrapper；前端使用 Node.js `^22.13.0 || >=24.0.0` 与 pnpm 9.15.9。Docker 可用于运行依赖和容器部署。
2. **启动后端**：按[后端快速开始](https://github.com/prototype-hub/proto-bridge#快速开始)准备 PostgreSQL、本地配置和存储目录，设置自己的管理员密码，再构建并运行服务。首次体验可关闭 Redis 与 Elasticsearch。
3. **连接前端**：按[前端联调说明](https://github.com/prototype-hub/proto-bridge-ui#连接真实后端)安装依赖、设置 API 代理并运行 `pnpm dev`。也可按[本地体验指南](https://github.com/prototype-hub/proto-bridge-ui#五分钟启动)使用 `pnpm dev:mock` 查看界面。
4. **交付第一个原型**：创建项目，上传包含 HTML、脚本、样式及图片的完整 ZIP，或选择 HTML 导出文件夹由浏览器打包，确认后上传；检查页面、资源和交互，再创建分享。

生产部署、HTTPS、反向代理、大文件上传及备份恢复请参阅[后端部署说明](https://github.com/prototype-hub/proto-bridge#服务器部署)与[前端部署说明](https://github.com/prototype-hub/proto-bridge-ui#docker-部署)。

## 一起完善

欢迎大家加入QQ群进行沟通交流。

[点击链接加入群聊【prototype-hub】](https://qm.qq.com/q/8WYYFTzS24)

欢迎贡献问题复现、文档、可公开分发的原型样本和代码改进。开始前请阅读[后端贡献说明](https://github.com/prototype-hub/proto-bridge/blob/main/CONTRIBUTING.md)或[前端贡献说明](https://github.com/prototype-hub/proto-bridge-ui/blob/main/CONTRIBUTING.md)，每次变更聚焦一个问题，并说明行为变化与验证结果。

可共同推进的功能与计划详见[基础版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md)和[高级版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_ADVANCED.md)。

安全问题请先阅读对应仓库的 [SECURITY.md（后端）](https://github.com/prototype-hub/proto-bridge/blob/main/SECURITY.md)或 [SECURITY.md（前端）](https://github.com/prototype-hub/proto-bridge-ui/blob/main/SECURITY.md)，按其中说明使用私密报告渠道。

## 开源许可与致谢

前后端仓库有权授予的原创贡献采用 **Apache License 2.0**，具体以各自的 [LICENSE（后端）](https://github.com/prototype-hub/proto-bridge/blob/main/LICENSE)、[LICENSE（前端）](https://github.com/prototype-hub/proto-bridge-ui/blob/main/LICENSE)及 NOTICE 为准；第三方组件和用户上传内容遵循各自的权利与许可。

感谢 [Spring](https://github.com/spring-projects/spring-framework)、[Project Reactor](https://github.com/reactor/reactor-core)、[hsweb](https://github.com/hs-web/hsweb-framework)、[Vue](https://github.com/vuejs/core)、[Ant Design Vue](https://github.com/vueComponent/ant-design-vue)、[PostgreSQL](https://github.com/postgres/postgres)、[Redis](https://github.com/redis/redis)、[Elasticsearch](https://github.com/elastic/elasticsearch)、[Nginx](https://github.com/nginx/nginx) 等开源项目。
