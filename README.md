# DIC4｜Food Guardian 會議論文與 OpenSpec

這個工作區整理 Food Guardian 的 IEEE 會議論文草稿，以及對應的 OpenSpec 規格。論文探討如何用家庭食材庫存、食譜份量與限制條件規劃餐點。評估章節描述預定的實驗設計。

**從這裡開始** · [閱讀論文 PDF](papers/Food_Guardian__An_Inventory_Aware_AI_Agent_for_Household_Food_Management_and_Waste_Reduction__1_.pdf) · [查看 LaTeX](paper_completed/main.tex) · [瀏覽 OpenSpec](openspec/specs/)

## 01｜論文與 Overleaf

[完整稿的 LaTeX](paper_completed/) 依摘要、緒論、相關研究、設計、評估、結論和參考文獻拆成多個檔案。若要在 Overleaf 編輯，先在儲存庫根目錄用 PowerShell 建立匯入包：

```powershell
Compress-Archive -Path paper_completed/main.tex,paper_completed/references.bib,paper_completed/sections -DestinationPath DIC4-overleaf.zip -Force
```

登入 Overleaf 後，選擇 **Create a new project → Existing project (.zip)**，上傳產生的 ZIP。主檔選 `main.tex`，編譯器選 pdfLaTeX。 [Overleaf 匯入說明](https://www.overleaf.com/learn/latex/Kb/Uploading_a_project)

## 02｜從論文章節追到規格

| 想核對的內容 | OpenSpec 入口 |
| --- | --- |
| 摘要、研究問題與文獻脈絡 | [摘要](openspec/changes/000-abstract/) · [緒論](openspec/changes/001-introduction/) · [相關研究](openspec/changes/002-related-work/) |
| 系統怎麼運作、預計怎麼評估 | [設計](openspec/changes/003-proposed-design/) · [實驗規劃](openspec/changes/004-experiment/) |
| 研究限制、引用與整稿組裝 | [結論](openspec/changes/005-conclusion/) · [參考文獻](openspec/changes/006-reference/) · [整稿](openspec/changes/write-iceb-paper/) |

每個變更目錄包含提案、設計、任務和差異規格。使用 Node.js 22 時，可從儲存庫根目錄安裝工具並執行嚴格驗證：

```powershell
npm ci --prefix tooling
$env:OPENSPEC_TELEMETRY = '0'
node tooling/node_modules/@fission-ai/openspec/bin/openspec.js validate --all --strict --no-interactive
```

[GitHub Actions](https://github.com/timko1018/DIC4/actions/workflows/openspec-validate.yml) 會在推送或 PR 指向 `main` 或 `master` 時執行同一套規格檢查。

## 03｜修訂對照與來源

### 論文初稿瑕疵 vs. 完成版逐頁對照分析

每張圖左側為初稿，右側為完成版。兩版 PDF 可從[論文索引](papers/README.md)開啟。

#### 第 1 頁｜首頁版面

![第 1 頁對照，左為初稿，右為完成版](assets/paper_comparison/comparison_page_1.jpg)

兩版首頁一致，皆以 IEEE 雙欄呈現標題、摘要、關鍵詞和緒論。緒論包含研究動機、問題定義與主要貢獻。

#### 第 2 頁｜系統設計與份量換算

![第 2 頁對照，左為初稿，右為完成版](assets/paper_comparison/comparison_page_2.jpg)

初稿介紹四個子系統後直接進入決策流程，缺少食譜份量換算的數學定義。完成版補上第 III-B 節與公式（1），說明如何依人數換算食材用量，以及如何處理無法確認的單位。

#### 第 3 頁｜評估設計與參考文獻

![第 3 頁對照，左為初稿，右為完成版](assets/paper_comparison/comparison_page_3.jpg)

兩版都呈現文獻比較與評估設計。初稿的引文 [1]–[8] 集中在第 3 頁底部。完成版加入方法段落後，本頁保留 [1]–[3]，其餘引文移到下一頁。

#### 第 4 頁｜演算法與雙欄平衡

![第 4 頁對照，左為初稿，右為完成版](assets/paper_comparison/comparison_page_4.jpg)

初稿第 4 頁左欄只有 Algorithm 1，右欄留白。完成版左欄仍呈現演算法，右欄接續參考文獻 [4]–[8]，改善末頁的欄位平衡。

### 參考來源

本儲存庫的 Food Guardian 論文、規格與比較素材來自 Wesley0628c 的 DIC4 參考作業，匯入版本為 `d5295e5`。此頁重新整理檔案入口、Overleaf 打包方式和 OpenSpec 檢查步驟。 [參考儲存庫](https://github.com/Wesley0628c/DIC4-overleaf-draft-for-conference-using-MCP-and-openspec)
