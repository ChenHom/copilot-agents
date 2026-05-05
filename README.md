# copilot-agents

這個專案用來自動同步 [github/awesome-copilot](https://github.com/github/awesome-copilot) 的內容到本 repository。

## 已設定的自動同步

同步工作流程檔案：
- [.github/workflows/sync-awesome-copilot.yml](.github/workflows/sync-awesome-copilot.yml)

排程時間：
- 每天 UTC 00:00（台北時間 08:00）

觸發方式：
- 排程自動執行
- 在 GitHub Actions 頁面手動執行（workflow_dispatch）

## 會同步的資料夾

來源：
- [awesome-copilot/chatmodes](https://github.com/github/awesome-copilot/tree/main/chatmodes)
- [awesome-copilot/instructions](https://github.com/github/awesome-copilot/tree/main/instructions)
- [awesome-copilot/prompts](https://github.com/github/awesome-copilot/tree/main/prompts)
- [awesome-copilot/agents](https://github.com/github/awesome-copilot/tree/main/agents)

同步到本 repo：
- [.github/chatmodes](.github/chatmodes)
- [.github/instructions](.github/instructions)
- [.github/prompts](.github/prompts)
- [.github/agents](.github/agents)

## 參考來源

- [doggy8088/github-copilot-configs 的 sync-awesome-copilot workflow](https://github.com/doggy8088/github-copilot-configs/blob/main/.github/workflows/sync-awesome-copilot.yml)

## 建立與推送紀錄

目前已完成：
- 初始化 Git repository
- 建立初始 commit
- 建立 GitHub repository 並推送到遠端

Repository：
- [ChenHom/copilot-agents](https://github.com/ChenHom/copilot-agents)
