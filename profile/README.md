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
- **预览与检查**：在浏览器中浏览页面树、体验交互，使用 Inspect 查看和复制元素属性、CSS、HTML、图片及 SVG 信息。
- **受控分享**：通过独立链接分享原型，固定创建时的修订，设置访问密码与有效期，复制或删除分享，服务于评审与交付。
- **系统管理**：提供用户、角色、组织、职位、菜单与按钮权限、数据字典、品牌配置、个人中心及日志管理。
- **自主部署**：基础运行使用 PostgreSQL 与本地文件存储；Redis、Elasticsearch 可按需要启用，支持 JAR、Docker 与 Nginx 部署。

### 当前使用边界

平台接收静态 HTML 原型包，不提供设计源文件编辑、Figma 原生文件导入或多人实时协同编辑。项目访问由**成员范围与平台权限共同控制**，支持所有者、编辑者和查看者角色；管理员例外也按服务端权限校验。项目和版本列表的服务端分页、筛选仍待实现。

前后端需同步升级并停止旧写入节点：旧内部匿名预览凭证失效，历史项目需显式执行[归属迁移与认领](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/DATA.md#项目归属迁移与认领)，旧逻辑版本需显式完成[修订预检与迁移](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/DATA.md#不可变修订与旧内容迁移)。升级前联合备份数据库、全部历史原型与系统文件；迁移后旧分享绑定当时仍存的内容，过去已被覆盖的历史无法恢复。

前端 Mock 用于本地体验与契约回归，真实后端联调和生产部署需按目标版本及环境验收。详细兼容边界以两个仓库的 README 和发布文档为准。

## 功能清单与开发计划

核对日期：**2026-10-22**。以下清单展示当前已实现的功能与后续开发计划，按基础版本和高级版本分别维护。✅ 表示已完成，🔄 表示部分完成，🚧 表示开发中，🗓 表示规划中；规划内容不代表已上线或确定的发布时间。

| 版本 | 已完成 | 部分完成 | 开发中 | 规划中 | 完整清单 |
| --- | --- | --- | --- | --- | --- |
| 基础版本 | 9 项 | 5 项 | 0 项 | 9 项 | [基础版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md) |
| 高级版本 | 0 项 | 0 项 | 0 项 | 17 项 | [高级版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_ADVANCED.md) |

### 当前进展

- **项目成员与数据隔离**：已支持所有者、编辑者、查看者角色、成员增改删、待认领项目处理及服务端权限隔离。相关实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/9)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/14)；项目和版本列表的服务端分页、筛选仍待实现。
- **修订历史与固定分享**：已保留不可变历史，提供修订列表与游标加载、固定修订预览及并发更新冲突提示；新分享固定创建时的当前修订，后续上传不改变其内容。相关实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/10)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/16)。稳定页面深链、人工并排比较、页面与文件差异，以及分享编辑、启停、凭据轮换和跟随最新仍待实现，详见[修订与更新契约](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/API.md#不可变修订与更新冲突)。
- **内部预览授权**：采用绑定固定修订的 5 分钟授权，到期后需重新申请；成员变更会使旧授权失效，上传新修订后旧授权仍指向原修订直至到期。公开分享单独管理，移除成员不会自动撤销已有分享；已渲染或下载的内容无法远程清除。
- **容量与用量**：默认按同一部署总计 5 个项目、每项目 5 个逻辑版本执行服务端配额校验，提供真实用量展示与幂等创建；删除释放用量，同一逻辑版本上传新修订保留历史且不增加逻辑版本用量，历史超限仍保留已有内容的访问。容量实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/5)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/10)，公共权益接口仍在规划中。
- **网页文件夹上传**：已支持选择 HTML 导出目录、浏览器 Worker 打包、进度与取消，以及 ZIP 回退；打包完成后由用户确认上传。相关实现已合入[后端](https://github.com/prototype-hub/proto-bridge/pull/8)和[前端](https://github.com/prototype-hub/proto-bridge-ui/pull/13)，输入预算与兼容范围见[基础版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md)。
- **账号与预览**：已支持可选“记住我”和经服务端验证的会话恢复，并改进沙箱内嵌套页面的预览兼容性；原型继续受沙箱隔离，嵌套页面兼容性以实际导出包为准。
- **后端持久化**：已合入 [ORM 查询与结构化 DDL 改造](https://github.com/prototype-hub/proto-bridge/pull/11)，使用框架查询能力和 jOOQ 结构描述；当前配置与验证范围仍为 PostgreSQL，不代表已支持其他数据库。
- **发行与运维**：已完成独立 JAR 启动与重启、双进程配额竞争、数据库与原型及系统文件联合恢复、连接真实后端的 Chrome 流程隔离验证，并补齐兼容依赖补丁与审计门禁。完整漏洞扫描、许可归属、真实 Axure 样本、目标生产环境与镜像验收仍待完成，详见[后端发布指南](https://github.com/prototype-hub/proto-bridge/blob/main/doc/public/RELEASE.md)与[前端发布指南](https://github.com/prototype-hub/proto-bridge-ui/blob/main/docs/public/RELEASE.md)。

## 技术栈

| 层次 | 主要技术 |
| --- | --- |
| 前端 | Vue 3、TypeScript、Vite、Ant Design Vue、Pinia、Vue Router、vue-i18n |
| 后端 | Java 21、Spring Boot 3、Spring WebFlux、Project Reactor、hsweb、EasyORM、jOOQ（结构描述与 DDL） |
| 数据与存储 | PostgreSQL、R2DBC、本地文件存储；可选 Redis 与 Elasticsearch |
| 构建、部署与验证 | Maven Wrapper、pnpm、Docker、Nginx、Vitest、Playwright、Testcontainers |

## 开始使用

1. **准备环境**：后端使用 JDK 21 和仓库自带的 Maven Wrapper；前端使用 Node.js 22.12+ 与 pnpm 9.0.6。Docker 可用于运行依赖和容器部署。
2. **启动后端**：按[后端快速开始](https://github.com/prototype-hub/proto-bridge#快速开始)准备 PostgreSQL、本地配置和存储目录，设置自己的管理员密码，再构建并运行服务。首次体验可关闭 Redis 与 Elasticsearch。
3. **连接前端**：按[前端联调说明](https://github.com/prototype-hub/proto-bridge-ui#连接真实后端)安装依赖、设置 API 代理并运行 `pnpm dev`。也可按[本地体验指南](https://github.com/prototype-hub/proto-bridge-ui#五分钟启动)使用 `pnpm dev:mock` 查看界面。
4. **交付第一个原型**：创建项目，上传包含 HTML、脚本、样式及图片的完整 ZIP，或选择 HTML 导出文件夹由浏览器打包，确认后上传；检查页面、资源和交互，再创建分享。

生产部署、HTTPS、反向代理、大文件上传及备份恢复请参阅[后端部署说明](https://github.com/prototype-hub/proto-bridge#服务器部署)与[前端部署说明](https://github.com/prototype-hub/proto-bridge-ui#docker-部署)。

## 一起完善

欢迎贡献问题复现、文档、可公开分发的原型样本和代码改进。开始前请阅读[后端贡献说明](https://github.com/prototype-hub/proto-bridge/blob/main/CONTRIBUTING.md)或[前端贡献说明](https://github.com/prototype-hub/proto-bridge-ui/blob/main/CONTRIBUTING.md)，每次变更聚焦一个问题，并说明行为变化与验证结果。

可共同推进的功能与计划详见[基础版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md)和[高级版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_ADVANCED.md)。

安全问题请先阅读对应仓库的 [SECURITY.md（后端）](https://github.com/prototype-hub/proto-bridge/blob/main/SECURITY.md)或 [SECURITY.md（前端）](https://github.com/prototype-hub/proto-bridge-ui/blob/main/SECURITY.md)，按其中说明使用私密报告渠道。

## 开源许可与致谢

前后端仓库有权授予的原创贡献采用 **Apache License 2.0**，具体以各自的 [LICENSE（后端）](https://github.com/prototype-hub/proto-bridge/blob/main/LICENSE)、[LICENSE（前端）](https://github.com/prototype-hub/proto-bridge-ui/blob/main/LICENSE)及 NOTICE 为准；第三方组件和用户上传内容遵循各自的权利与许可。

感谢 [Spring](https://github.com/spring-projects/spring-framework)、[Project Reactor](https://github.com/reactor/reactor-core)、[hsweb](https://github.com/hs-web/hsweb-framework)、[Vue](https://github.com/vuejs/core)、[Ant Design Vue](https://github.com/vueComponent/ant-design-vue)、[PostgreSQL](https://github.com/postgres/postgres)、[Redis](https://github.com/redis/redis)、[Elasticsearch](https://github.com/elastic/elasticsearch)、[Nginx](https://github.com/nginx/nginx) 等开源项目。
