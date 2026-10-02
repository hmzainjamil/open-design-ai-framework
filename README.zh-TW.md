# Open Design

Open Design 是一款以本機優先為主的設計工作台，可將已安裝的 coding-agent CLI 或已設定的 BYOK 服務連接到可重複使用的 Skills 與 Design Systems。產生的成果可在預覽中檢視並儲存。

> **狀態：** 已檢查原始碼結構與 package scripts。本次 README 更新未驗證安裝、測試、外部服務、部署、安全隔離或產出品質。

## 組成

- apps/daemon/：本機服務與 CLI
- apps/web/：設計工作區與預覽
- apps/desktop/：桌面應用外殼
- skills/ 與 design-systems/：可重複使用的流程與設計資料

## 環境與啟動

根目錄 package 指定 Node.js 24.x 與 pnpm 10.33.2。Quickstart 將 macOS、Linux 和 WSL2 列為主要環境。

    corepack enable
    pnpm install
    pnpm tools-dev run web

命令依據儲存庫 Quickstart 撰寫，本次未執行。桌面端啟動與其他選項請參閱[英文 Quickstart](QUICKSTART.md)。

## 資料與限制

輸入和專案內容可能會傳送至所選 Agent CLI 或 BYOK 服務。使用本機 CLI 不代表推理只在本機進行。重用前請檢查產出。本 README 不構成安全或隔離認證。

- [文件索引](docs/README.md)
- [架構](docs/architecture.md)
- [貢獻指南](CONTRIBUTING.md)
- [授權](LICENSE)