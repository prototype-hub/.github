# PrototypeHub

**轻量、可自托管的原型管理与交付平台。**

PrototypeHub 面向产品经理、UI/UX 设计师、研发与测试团队，将设计工具导出的静态 HTML 原型整理为可管理的项目与版本，让需求评审、原型预览和交付沟通拥有统一入口。

**导出 HTML → 上传 ZIP → 在线预览与 Inspect → 可控分享 → 研发与测试交付**

## 项目导航

| 仓库 | 职责 | 从这里开始 |
| --- | --- | --- |
| [proto-bridge](https://github.com/prototype-hub/proto-bridge) | 后端：项目与版本、ZIP 校验与存储、原型交付、分享及系统管理 API | [快速开始](https://github.com/prototype-hub/proto-bridge#快速开始) · [配置与部署](https://github.com/prototype-hub/proto-bridge#服务器部署) |
| [proto-bridge-ui](https://github.com/prototype-hub/proto-bridge-ui) | 前端：管理界面、页面树、预览与元素检查、分享和个人中心 | [本地体验](https://github.com/prototype-hub/proto-bridge-ui#五分钟启动) · [连接后端](https://github.com/prototype-hub/proto-bridge-ui#连接真实后端) |

产品名称为 **PrototypeHub**，前后端工程分别沿用 `proto-bridge` 与 `proto-bridge-ui`，前端部分文档中也使用 ProtoBridge 名称。

## 能做什么

- **集中管理原型**：按项目维护版本，上传或替换 Axure 等工具导出的完整 HTML ZIP，自动处理页面与资源。
- **预览与检查**：在浏览器中浏览页面树、体验交互，使用 Inspect 查看和复制元素属性、CSS、HTML、图片及 SVG 信息。
- **受控分享**：通过独立链接分享原型，设置访问密码、有效期及启用状态，服务于评审与交付。
- **系统管理**：提供用户、角色、组织、职位、菜单与按钮权限、数据字典、品牌配置、个人中心及日志管理。
- **自主部署**：基础运行使用 PostgreSQL 与本地文件存储；Redis、Elasticsearch 可按需要启用，支持 JAR、Docker 与 Nginx 部署。

### 当前使用边界

平台接收静态 HTML 原型包，不提供设计源文件编辑、Figma 原生文件导入或多人实时协同编辑。当前原型业务采用**共享工作区，尚未按项目成员或创建者隔离数据**；部署前请结合团队的数据访问需求评估。

前端 Mock 用于本地体验与契约回归，真实后端联调和生产部署需按目标版本及环境验收。详细兼容边界以两个仓库的 README 和发布文档为准。

## 功能清单与开发计划

以下清单展示当前已实现的功能与后续开发计划，按基础版本和高级版本分别维护。✅ 表示已完成，🗓 表示规划中；规划内容不代表已上线或确定的发布时间。

| 版本 | 已完成 | 规划中 | 完整清单 |
| --- | --- | --- | --- |
| 基础版本 | 8 项 | 15 项 | [基础版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md) |
| 高级版本 | 0 项 | 17 项 | [高级版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_ADVANCED.md) |

## 技术栈

| 层次 | 主要技术 |
| --- | --- |
| 前端 | Vue 3、TypeScript、Vite、Ant Design Vue、Pinia、Vue Router、vue-i18n |
| 后端 | Java 21、Spring Boot 3、Spring WebFlux、Project Reactor、hsweb、EasyORM |
| 数据与存储 | PostgreSQL、R2DBC、本地文件存储；可选 Redis 与 Elasticsearch |
| 构建、部署与验证 | Maven Wrapper、pnpm、Docker、Nginx、Vitest、Playwright、Testcontainers |

## 开始使用

1. **准备环境**：后端使用 JDK 21 和仓库自带的 Maven Wrapper；前端使用 Node.js 22.12+ 与 pnpm 9.0.6。Docker 可用于运行依赖和容器部署。
2. **启动后端**：按[后端快速开始](https://github.com/prototype-hub/proto-bridge#快速开始)准备 PostgreSQL、本地配置和存储目录，设置自己的管理员密码，再构建并运行服务。首次体验可关闭 Redis 与 Elasticsearch。
3. **连接前端**：按[前端联调说明](https://github.com/prototype-hub/proto-bridge-ui#连接真实后端)安装依赖、设置 API 代理并运行 `pnpm dev`。也可按[本地体验指南](https://github.com/prototype-hub/proto-bridge-ui#五分钟启动)使用 `pnpm dev:mock` 查看界面。
4. **交付第一个原型**：创建项目，将包含 HTML、脚本、样式及图片的完整导出目录打成 ZIP，上传后检查页面、资源和交互，再创建分享。

生产部署、HTTPS、反向代理、大文件上传及备份恢复请参阅[后端部署说明](https://github.com/prototype-hub/proto-bridge#服务器部署)与[前端部署说明](https://github.com/prototype-hub/proto-bridge-ui#docker-部署)。

## 一起完善

欢迎贡献问题复现、文档、可公开分发的原型样本和代码改进。开始前请阅读[后端贡献说明](https://github.com/prototype-hub/proto-bridge/blob/main/CONTRIBUTING.md)或[前端贡献说明](https://github.com/prototype-hub/proto-bridge-ui/blob/main/CONTRIBUTING.md)，每次变更聚焦一个问题，并说明行为变化与验证结果。

可共同推进的功能与计划详见[基础版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_BASIC.md)和[高级版本功能清单](https://github.com/prototype-hub/.github/blob/main/profile/FEATURES_ADVANCED.md)。

安全问题请先阅读对应仓库的 [SECURITY.md（后端）](https://github.com/prototype-hub/proto-bridge/blob/main/SECURITY.md)或 [SECURITY.md（前端）](https://github.com/prototype-hub/proto-bridge-ui/blob/main/SECURITY.md)，按其中说明使用私密报告渠道。

## 开源许可与致谢

前后端仓库有权授予的原创贡献采用 **Apache License 2.0**，具体以各自的 [LICENSE（后端）](https://github.com/prototype-hub/proto-bridge/blob/main/LICENSE)、[LICENSE（前端）](https://github.com/prototype-hub/proto-bridge-ui/blob/main/LICENSE)及 NOTICE 为准；第三方组件和用户上传内容遵循各自的权利与许可。

感谢 [Spring](https://github.com/spring-projects/spring-framework)、[Project Reactor](https://github.com/reactor/reactor-core)、[hsweb](https://github.com/hs-web/hsweb-framework)、[Vue](https://github.com/vuejs/core)、[Ant Design Vue](https://github.com/vueComponent/ant-design-vue)、[PostgreSQL](https://github.com/postgres/postgres)、[Redis](https://github.com/redis/redis)、[Elasticsearch](https://github.com/elastic/elasticsearch)、[Nginx](https://github.com/nginx/nginx) 等开源项目。
