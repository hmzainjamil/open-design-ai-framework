# Open Design

Open Design 是一款本地优先的设计工作台，可将已安装的 coding-agent CLI 或配置好的 BYOK 服务连接到可复用的 Skills 和 Design Systems。生成的产物可在预览中查看并保存。

> **状态：** 已检查源码结构和 package scripts。本次 README 更新未验证安装、测试、外部服务、部署、安全隔离或生成质量。

## 组成

- apps/daemon/：本地服务和 CLI
- apps/web/：设计工作区和预览
- apps/desktop/：桌面应用外壳
- skills/ 与 design-systems/：可复用流程和设计资料

## 环境与启动

根 package 指定 Node.js 24.x 和 pnpm 10.33.2。Quickstart 将 macOS、Linux 和 WSL2 列为主要环境。

    corepack enable
    pnpm install
    pnpm tools-dev run web

命令来自仓库 Quickstart，本次未运行。桌面端启动和其他选项请参阅[英文 Quickstart](QUICKSTART.md)。

## 数据与限制

输入和项目上下文可能会发送到所选 Agent CLI 或 BYOK 服务。使用本地 CLI 不代表推理一定只在本机完成。复用前请检查生成产物。本 README 不构成安全或隔离认证。

- [文档索引](docs/README.md)
- [架构](docs/architecture.md)
- [贡献指南](CONTRIBUTING.md)
- [许可证](LICENSE)