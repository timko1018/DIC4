# DIC4 · Overleaf Draft for Conference using MCP and OpenSpec

以家庭食材批次與晚餐規劃為案例，撰寫 IEEE 雙欄英文會議論文草稿。草稿提出可追溯的食材分配方法與評估計畫，沒有實驗結果。作者資訊暫以佔位文字呈現。

## Overleaf

下載 [DIC4-overleaf.zip](DIC4-overleaf.zip)，在 Overleaf 選擇 **Create a new project → Existing project (.zip)** 並上傳。主檔為 `main.tex`，編譯器使用 pdfLaTeX。也可直接閱讀 [LaTeX 原始碼](paper/main.tex)。[Overleaf 匯入說明](https://www.overleaf.com/learn/latex/Kb/Uploading_a_project)。

## OpenSpec

- [現行規格](openspec/specs/conference-draft/spec.md)
- [變更提案、設計、任務與差異規格](openspec/changes/prepare-ieee-draft/)
- [GitHub Actions 工作流程](.github/workflows/validate.yml)

在儲存庫根目錄使用 Node.js 22 以上版本執行

```sh
npx --yes --package @fission-ai/openspec@2.1.0 openspec validate --all --strict
```

## MCP 與參考來源

本作業透過 GitHub MCP 讀取參考儲存庫與確認交付儲存庫。草稿中的食材工具介面是研究設計。Overleaf 專案可由上方 ZIP 建立。

參考 Wesley Chen 的 [DIC4 成果展示庫](https://github.com/Wesley0628c/DIC4-overleaf-draft-for-conference-using-MCP-and-openspec)，沿用家庭食材管理的題材與章節模組化方式，重新撰寫方法、評估計畫與規格。
