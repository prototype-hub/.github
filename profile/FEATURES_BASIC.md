# 基础版本功能清单

[返回组织主页](https://github.com/prototype-hub) · [高级版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_ADVANCED.md)

核对日期：**2026-10-31**。✅ 表示已完成，🔄 表示部分完成，🚧 表示开发中，🗓 表示规划中。当前共 23 项功能，其中 15 项已完成、3 项部分完成、0 项开发中、5 项规划中；规划内容不代表已上线或确定的发布时间。

| 功能 | 功能说明 | 开发状态 |
| --- | --- | --- |
| 项目与版本管理 | 创建、编辑、删除项目，管理多个原型版本及版本说明 | ✅ 已完成 |
| HTML / Axure 原型上传 | 上传 ZIP，新建逻辑版本或上传新修订并保留历史，自动发现入口和页面目录，校验压缩包与资源路径；并发更新冲突提示刷新确认 | ✅ 已完成 |
| 在线原型预览 | 页面树导航、页面切换、交互预览及桌面与窄屏布局，已改进沙箱内嵌套页面兼容性；内部预览绑定固定修订，采用 5 分钟授权，到期重新申请 | ✅ 已完成 |
| 基础 Inspect | 查看元素尺寸、字体、颜色和间距，复制 CSS / HTML，查看图片及复制、下载 SVG | ✅ 已完成 |
| 原型分享 | 创建独立分享链接，默认固定修订、可选跟随最新，设置密码和有效期，复制或删除分享，支持免平台账号访问 | ✅ 已完成 |
| 账号与平台权限 | 登录、可选“记住我”与经服务端验证的会话恢复，个人中心、用户、角色、菜单和按钮权限管理 | ✅ 已完成 |
| 系统管理 | 组织、职位、数据字典、品牌配置、访问日志和系统日志 | ✅ 已完成 |
| 私有化部署 | 后端 JAR / Docker 部署、前端静态部署、本地文件存储及备份恢复操作指引 | ✅ 已完成 |
| 网页文件夹上传 | 选择已导出的 HTML 文件夹，由浏览器 Worker 打包，确认后上传；提供进度、取消和 ZIP 回退，支持新建逻辑版本或上传新修订并保留历史 | ✅ 已完成 |
| 项目成员与数据隔离 | 所有者、编辑者、查看者角色、成员增改删及服务端权限隔离；项目和版本列表支持服务端分页、名称筛选与排序，记录和总数均按当前权限及筛选条件过滤 | ✅ 已完成 |
| 不可变历史与版本对比 | 保留不可变修订、历史列表与固定页面链接、页面查找及并发冲突提示；同一逻辑版本的两份固定修订可人工双窗并排预览，查看页面与文件的新增、删除、变化及不变状态、完整统计及独立分页 | ✅ 已完成 |
| 分享管理增强 | 编辑已有分享的说明、密码与有效期，暂停与恢复、链接轮换及永久撤销，固定指定历史修订或跟随最新；并发配置冲突时刷新核对，不自动覆盖 | ✅ 已完成 |
| 外部客户批注 | 邮箱验证码身份、根页面打点与矩形/椭圆圈选、文字及单张图片投稿、网页回复、内部备注隔离、解决/重开、线程深链、成员负责人及跨页反馈总览；几何位置按根文档与视口尺寸匹配，不跟踪语义元素 | ✅ 已完成 |
| 基础评审与发布 | 针对固定修订记录评审结论、批准状态和发布快照 | 🗓 规划中 |
| 项目整理与恢复 | 已支持项目与版本软删除、统一回收菜单的项目/版本标签页及按权限逐项恢复、30 天保留与到期清理及配套前端提示；分组、业务标签、收藏、封面管理和归档仍待实现 | 🔄 部分完成 |
| 资料与附件管理 | 关联图片稿、PRD、PDF、链接及标准导出包，记录来源与版本关系 | 🗓 规划中 |
| 设计资产与规范 | Inspect 测距、颜色字体汇总、批量资产导出、组件代码映射与设计 Token 规范包 | 🗓 规划中 |
| 研发交付说明 | 元素功能说明、页面交付状态、状态与异常验收矩阵、视口自测记录及 Markdown / HTML 说明书 | 🗓 规划中 |
| 需求追踪与检索 | 已支持固定修订页面手动关联 HTTP(S) 工作项地址与纯文本备注，新增、编辑、取消关联及服务端分页；页面与需求关系、全文检索及文案清单导出仍待实现 | 🔄 部分完成 |
| 演示与体验验证 | 任务演示脚本、视频时间点说明、可用性任务与问卷反馈 | 🗓 规划中 |
| 原型包质量检查 | 对明确历史修订检查入口与清单文件存在性、支持的本地 HTML/CSS 静态引用、缺失资源、失效内部链接和路径问题，展示范围与完成状态，并导出同一份 JSON 报告 | ✅ 已完成 |
| 容量与用量管理 | 已实现同一部署默认 5 个项目、每项目 5 个逻辑版本的服务端原子配额校验、真实用量展示、幂等创建、软删除释放及恢复重占额度；新增与恢复按当前有效容量准入，上传新修订不增逻辑版本用量，历史超限保留活动内容；公共权益接口分别返回免费权益、已验证声明和实际容量 | ✅ 已完成 |
| 发行与运维完善 | 已完成独立 JAR 启动与重启、双进程配额竞争、数据库与原型及系统文件联合恢复、真实后端 Chrome 流程隔离验证、九表评审与回复原图恢复核验，以及工作项专项联调与非空恢复；补齐兼容依赖补丁，修正许可材料及超时审计判定；完整漏洞扫描、许可归属、真实 Axure 样本、目标生产环境与镜像验收仍待完成 | 🔄 部分完成 |

## 统计与安装权益边界

统计概览提供当前权限范围内的项目、逻辑版本与有效分享数量，以及近 7/30 天分享访问趋势和最多 10 个项目的排行，已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/37)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/48)。分享外壳成功打开后确认一次访问，同票重放去重；同次切页、内部预览和资源请求不计，刷新重新打开可产生新访问。历史未采集与真实零值分开显示；访问次数不代表独立人数，尽力采集失败不阻断浏览，也不包含用户研究与行为漏斗。

[公共权益接口](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/API.md#installation-credential-verification)已提供免费权益、已验证凭证声明与实际容量的独立读取。管理员可下载安装请求、导入凭证并查询本地验签状态，已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/38)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/49)。验签成功不自动扩容、启用高级功能或启动试用；基础浏览、分享和邮箱身份验证码不依赖商业凭证。高级部分的已实现与待项见[离线授权实现边界](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_ADVANCED.md#离线授权实现边界)。

## 修订对比与质量检查范围

比较限定于同一活动逻辑版本的两份明确修订，按区分大小写的路径配对，文件变化依据 SHA-256 或大小，页面变化依据主名称或关联文件；重命名表现为删除与新增，不进行像素或 HTML 语义识别。左右预览独立导航，点击差异行才按路径同时定位；缺失页面显示空态，没有稳定标识的旧页面仅展示比较信息。比较与质量报告均需满足当前项目读取范围及平台查询动作权限，不扩大公开分享或其他修订的访问范围。行为详见[同版本修订比较](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/API.md#同版本修订比较)。

质量体检针对选定的历史修订检查入口、清单文件存在性与支持的本地 HTML/CSS 静态引用，不执行 JavaScript、不联网，也不验证动态交互或替代 ZIP 上传安全检查。外部引用、根绝对路径、页内锚点及不支持的协议单列为未检查项；缺失文件、读取失败、扫描预算或问题收录截断会使报告不完整。`complete` 只表示支持的本地检查范围是否完成，不表示没有错误或所有页面正确。

当前扫描预算为单文档 **2 MiB**、累计 **32 MiB**、最多 **10 万条引用**及 **1000 项已收录问题**，以报告实际限制为准。界面展示未检查、跳过及遗漏数量；JSON 下载使用当前已加载的同一报告，不重新扫描，也不补造遗漏结果。报告行为见[固定修订交付包质量报告](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/API.md#固定修订交付包质量报告)。

## 修订与升级边界

同一逻辑版本上传新修订会保留历史，不增加逻辑版本用量。内部预览绑定固定修订，上传新修订后旧授权仍读取原修订直至到期；成员变更仍会撤销旧授权。公开分享独立管理，移除成员不会自动撤销分享。固定快照不代表已经完成评审结论、批准状态或发布流程。

页面链接固定修订与唯一页面标识（`revisionId`、`pageId`），可刷新、前进后退与复制；复制内容不包含运行态凭据、密码或平台令牌。旧页面没有唯一标识时仍可按路径浏览，但不能生成稳定页面链接；未知或不合法目标报错，不回退到其他页面。公开页面链接继续服从当前分享授权，不能借跟随最新的分享访问历史修订。页面查找只覆盖已授权页面树的名称与路径，不代表全文检索。具体行为见[页面定位契约](https://github.com/prototype-hub/proto-bridge-ui/blob/main/docs/public/API.md#固定页面链接与页面目录)。

前后端需配套升级并停止旧写入和清理节点，在同一维护窗口联合备份数据库、全部历史原型与系统文件。历史项目按[归属迁移与认领](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/DATA.md#项目归属迁移与认领)处理，旧逻辑版本先完成[修订预检与迁移](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/DATA.md#不可变修订与旧内容迁移)；旧分享绑定迁移时仍存的内容，过去已被覆盖的历史无法恢复。升级前已有的删除记录也按原删除时间计算 30 天，已到期数据可能立即进入清理；恢复数据必须同时恢复数据库与文件，回收站不能代替备份。

## 回收站与保留期

项目与版本删除后从活动列表、分页总数和用量中排除，原 ID、历史修订与文件在保留期内保留。项目有活动版本时不可删除，需先删除这些版本。统一回收菜单提供项目、版本两个标签页，仅显示具备相应查询权限的标签页，支持分页、名称筛选与排序；版本可在当前授权的活动项目范围内筛选。恢复按当前权限重新检查当前有效容量（默认同一部署 5 个项目、每项目 5 个逻辑版本），容量不足等冲突不改变回收记录。先恢复父项目，再到版本标签页逐个恢复其子版本；恢复父项目不会延长子版本各自的保留期。旧公开分享保持撤销，旧内部预览授权不复活，恢复后需重新授权预览或创建分享。删除与恢复接口见[项目与版本软删除](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/API.md#项目与版本软删除)和[回收站与逐项恢复](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/API.md#回收站与逐项恢复)。

每条记录从自己的删除时间起固定保留 **30×24 小时**。期满立即不可恢复，即使物理文件尚未清理；后台永久清理数据库记录，并通过持久队列异步回收原型快照，实际磁盘回收可延后。父项目等待子版本清理，不提前移除较新或仍活动的子版本；封面、头像与品牌资源不在原型快照清理范围内。不提供手动永久删除或单独删除修订的入口。

保留期与自动清理规则已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/17)，保留期提示及配套契约回归已合入[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/22)，应配套升级，避免旧版本“持续保留、不自动清理”提示与服务端规则不一致。前端恢复遇到 404 时刷新列表与用量、保留真实错误的行为已在[回收站恢复实现](https://github.com/prototype-hub/proto-bridge-ui/pull/21)中合入，不会自动重试恢复。

## 邮箱身份与访客边界

邮箱身份是分享可选能力，只证明访问者持有该邮箱，姓名与公司为自述信息，不创建平台用户。项目分别提供邮箱与未验证访客的脱敏分页及启停；停用使对应访客的旧会话失效，邮箱访客的验证码也失效，重新启用不复活旧会话或验证码。身份开关与访客启停不构成匿名预览门禁，也不等于撤销分享，具体见[分享邮箱身份](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/API.md#分享邮箱身份)。

未验证入口须管理员显式允许，姓名必填、公司可选，不收集邮箱；身份有效期自首次签发起固定为 8 小时。退出、丢失、到期或被撤销后，不能凭姓名或邮箱找回原身份，也不会与后来验证的邮箱身份自动合并。SMTP 未配置或发送失败不会自动降级为未验证身份。相关实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/24)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/29)。

固定分享可创建、分页管理及撤销指定邮箱邀请，链接由用户手动复制分发；邀请最长有效 24 小时，且受分享到期时间约束，收件人仍须输入指定邮箱并重新完成验证码验证。邀请不把分享变为仅受邀者可访问，也不替代分享密码；撤销待用邀请不撤销已签发身份，后者需通过访客管理停用。相关实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/25)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/30)，行为见[固定分享邀请](https://github.com/prototype-hub/proto-bridge-ui/blob/main/docs/public/API.md#固定分享邀请)。

当前邮件仅用于验证码，不自动发送邀请邮件，也不提供业务通知。未配置可用邮件时不跳过邮箱验证；部署需按[邮箱身份与 SMTP](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/OPERATIONS.md#邮箱身份与smtp)验证真实投递，连接或认证成功不代表收件成功。

## 固定页面反馈边界

公开反馈需活动、有效的固定修订分享，并开启身份与反馈许可；目标为外壳当前选择的固定修订及唯一页面标识，不跟随原型 iframe 内部导航。访客可创建纯文本线程、网页回复及重开，仅查看同分享、同身份范围内的本人线程；有项目编辑能力且具备相应版本动作权限的成员可处理客户线程、对客回复、内部备注及解决/重开。内部备注由服务端隔离，不向客户展示。文字反馈已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/26)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/31)，具体见[固定页面文字反馈](https://github.com/prototype-hub/proto-bridge-ui/blob/main/docs/public/API.md#固定页面文字反馈)。

线程深链固定修订、页面与线程，仅用于定位；打开后仍须满足当前分享密码、身份验证或成员权限，不能凭链接找回已丢失的未验证身份。复制不包含访问凭据、正文或邀请片段；相关实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/28)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/33)。

访客初始投稿与已有线程的每条回复均可手动附一张 PNG/JPEG，最多 **5 MiB**，文字仍必填；图片继承该消息的公开/内部可见性，按当前权限手动读取，不包含通用附件或自动截图。图片回复与安全查看已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/29)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/34)，初始投稿附图已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/31)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/36)。

成员端可为当前选中的已有线程设置或清除负责人，候选仅为本项目当前启用的所有者或编辑者。分派不授予访问权限、不发送通知，也不提供全局分派队列；撤员或停用后显示负责人不可用，不自动转交。相关实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/30)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/35)。

访客新建反馈可明确选择根页面的点、矩形或椭圆位置快照，已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/32)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/37)。定位要求当前根文档与视口尺寸均精确匹配，尺寸不匹配时不定位；不读取子 frame 内部坐标、不跨 frame 转换，也不跟踪语义元素，动态内容即使尺寸相同仍可能变化。

全部页面反馈总览已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/33)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/38)，成员可组合状态与“全部负责人／分派给我／未分派”筛选，相关实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/34)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/39)。总览使用服务端分页，客户仍只能查看同一分享、本人身份范围的线程；成员责任筛选不授予权限、不自动转交或发送通知。线程的问题状态不代表评审结论、批准或发布流程，回复图片也不代表已实现资料与附件管理。

## 固定页面工作项边界

固定修订页面可手动关联 HTTP(S) 地址和纯文本备注，支持新增、编辑、取消关联与服务端分页；已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/35)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/46)。查看者只读，编辑者仍需相应平台动作与当前项目权限；上传新修订不复制或迁移旧引用，取消关联不会删除外部工作项。网络结果不明时保留原请求与键，先核对再由用户明确重试，不自动写入。页面与需求关系、全文检索及文案导出仍待实现，不抓取链接或调用外部系统，也不包含高级 API、Webhook 与通知能力。接口见[固定页面工作项引用](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/API.md#固定页面工作项引用)。

升级需先部署后端再配套前端，停止旧写入和清理节点；同窗口整库备份需包含 `p_work_item`、固定修订和相关 `p_creation_receipt`，并保留全部原型与系统文件。工作项地址和备注属于项目私有资料，引用本身不生成外部网站的文件副本。操作要求见[固定页面工作项引用升级](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/OPERATIONS.md#固定页面工作项引用升级)。

## 评审数据与恢复验证

联合备份应涵盖数据库中的全部 **9 张评审表**、请求回执与分享配置，以及全部原型、系统文件和 `review-images` 原图目录。已合入[九表评审恢复核验](https://github.com/prototype-hub/proto-bridge/pull/27)与[恢复后浏览器联验](https://github.com/prototype-hub/proto-bridge-ui/pull/32)，覆盖恢复后的邀请与文字反馈；另已完成[回复原图恢复专项](https://github.com/prototype-hub/proto-bridge/pull/29)。另已完成[固定页面工作项专项](https://github.com/prototype-hub/proto-bridge/pull/35)的真实后端浏览器联调、非空工作项与相关回执及原型/系统双文件存储恢复核验；该结果仅覆盖本功能，不代表全平台恢复或发行验收。现有恢复核验尚未覆盖非空负责人或非空几何锚点记录，目标生产环境与镜像仍需单独验收，完整发行缺口见[后端发布指南](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/RELEASE.md)与[前端发布指南](https://github.com/prototype-hub/proto-bridge-ui/blob/main/docs/public/RELEASE.md)。

发行工具已修正[主许可证全文与附属 NOTICE 区分](https://github.com/prototype-hub/proto-bridge-ui/pull/41)及[超时审计结果判定](https://github.com/prototype-hub/proto-bridge-ui/pull/42)，防止以附属声明替代主许可证或将超时后的结果认定成功。这些修复不替代完整漏洞扫描、许可权属审核、真实 Axure 样本及目标部署与镜像验收。

## 分享授权边界

新分享默认固定创建时的当前修订，编辑时可选择其他历史修订或跟随最新。跟随模式在每次打开、验证密码时解析一次当前修订，同次已授权的页面树、HTML 与资源固定为同一快照；后续上传不会使当前预览混用新旧内容。

配置变更使旧资源授权失效，暂停后恢复不会复活旧授权；链接轮换使旧链接及旧授权失效，永久撤销保留管理记录且不可恢复。公开分享与项目成员授权独立，移除成员不会自动撤销分享；浏览器已接收的内容无法远程收回。具体行为见[分享生命周期](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/API.md#分享生命周期)。

## 文件夹上传范围

浏览器文件夹输入预算为最多 **5000 个文件、合计 128 MiB、单文件 64 MiB**；不支持目录选择或超限时可使用原 ZIP 入口，服务端仍独立执行上传校验。当前仅 macOS Chrome 与合成 HTML 已验证，真实 Axure 导出包及其他浏览器、操作系统尚未验证。

文件夹须先由设计工具导出 HTML；此入口不读取 `.rp`，不监听目录，也不提供 Java 同步或 Axure 本地预览一键采集。操作语义与兼容边界见[前端上传说明](https://github.com/prototype-hub/proto-bridge-ui/blob/main/docs/public/API.md#html-文件夹与-zip-上传)。

路径冲突与不合法路径会给出逐路径拒绝原因并拒绝整次选择，不会跳过问题文件继续打包。
