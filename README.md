# DIC4 · Overleaf Draft for Conference using MCP and OpenSpec

本作業以家庭食材批次與晚餐規劃為案例，提出可追溯的食材分配方法與評估計畫。作者及系所暫以佔位文字呈現。

## 論文與 Overleaf

- [修訂版 IEEE 雙欄 PDF](artifacts/DIC4-paper.pdf)
- [Overleaf 匯入 ZIP](DIC4-overleaf.zip)
- [LaTeX 主檔](paper/main.tex)
- [初稿與修訂版對照](docs/revision.md)

登入 Overleaf，選擇 **Create a new project → Existing project (.zip)**，上傳 ZIP 並以 `main.tex` 為主檔。選用 XeLaTeX 可對應本機驗證所用的引擎。ZIP 已在本機解壓並編譯成兩頁 PDF。Overleaf 專案頁要求登入，線上編譯待驗證。[Overleaf 匯入說明](https://www.overleaf.com/learn/latex/Kb/Uploading_a_project)

## OpenSpec 章節對應

| 章節 | LaTeX | 現行規格 |
| --- | --- | --- |
| 摘要 | [原始碼](paper/sections/abstract.tex) | [驗收條件](openspec/specs/paper-abstract/spec.md) |
| 緒論 | [原始碼](paper/sections/background.tex) | [驗收條件](openspec/specs/paper-introduction/spec.md) |
| 相關研究 | [原始碼](paper/sections/related-work.tex) | [驗收條件](openspec/specs/paper-related-work/spec.md) |
| 方法 | [原始碼](paper/sections/design.tex) | [驗收條件](openspec/specs/paper-method/spec.md) |
| 評估 | [原始碼](paper/sections/evaluation.tex) | [驗收條件](openspec/specs/paper-evaluation/spec.md) |
| 結論 | [原始碼](paper/sections/conclusion.tex) | [驗收條件](openspec/specs/paper-conclusion/spec.md) |
| 參考文獻 | [原始碼](paper/sections/references.tex) | [驗收條件](openspec/specs/paper-references/spec.md) |

每章的提案、設計、差異規格及任務保留在 [OpenSpec 變更封存](openspec/changes/archive/)。[GitHub Actions](https://github.com/timko1018/DIC4/actions/workflows/validate.yml) 執行嚴格驗證。

```sh
npx --yes --package @fission-ai/openspec@2.1.0 openspec validate --all --strict
```

## MCP 與參考來源

透過 GitHub MCP 讀取參考儲存庫並發布交付檔案。草稿中的食材存量與分配 MCP 工具是研究設計，工具實作與重播評估尚未進行。

參考 [Wesley0628c 的 DIC4 成果展示庫](https://github.com/Wesley0628c/DIC4-overleaf-draft-for-conference-using-MCP-and-openspec)的章節組織與修訂展示方式。本文的方法、示例、評估計畫和規格另行撰寫。
