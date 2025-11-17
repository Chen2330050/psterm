# Readme

## Why psterm?

1. 基於傳統

   psterm 為基於傳統的 Prompt 的基礎進行功能延伸，不會影響到原有的工作流程與使用習慣。

2. 即時 Git 狀態

   在提示字元中即時掌握當前 Git 倉庫的快照狀態（分支、修改、未追蹤等）。

3. 清晰的 I/O 環境

   採用兩行式輸入環境，將輸入區與前一行輸出結果分離，讓指令的輸入與輸出檢視更加清晰明瞭。

## How psterm?

1. 開啟個人設定檔

    `notepad $profile`

2. Load psterm

    `oh-my-posh init pwsh --config ~/psterm.omp.json | Invoke-Expression`
