# Git

## 基本術語

1. 區域section=階段
   1. 工作目錄working tree/工作區workspace
   2. 預存區staging area/index
   3. 本地倉庫local repository
   4. 遠端倉庫remote repository/upstream repository
2. 對檔案操作中英文對照
   1. 建立(new)
   2. 修改(modify)
   3. 刪除(remove)
   4. 移動(move)、改名(rename)
3. Git指令中英文對照(git command)
   1. Snapshot 快照
   2. `git status` 查詢倉庫快照
   3. `git add` 紀錄內容快照
   4. `git commit` 按快照提交版本
4. `git status` 的狀態如下(中英文對照)
   1. new file 新檔案
   2. modified 已修改
   3. deleted 已刪除
   4. renamed 已改名
  
   - Untracked 未追蹤
   - unmodified 未追蹤

### 檔案的生命週期

對檔案進行操作時，Git會對檔案的快照進行追蹤與管控，以下描述檔案的生命週期，與其在不同階段(生命週期)時的狀態(`git status` 與 `git status -s`)

類型一: 剛新增的檔案或剛初始化的目錄

|階段|操作|`git s`|`git ss`|
|-|-|-|-|
|Workspace|建立|Untracked|？？|
||修改|modified|&emsp;M|
|Index|預存|staged|A |
|Repo|提交|clean||

note:

- 剛建立的檔案若還沒預存，依舊是untracked的狀態下，若此時進行修改git不會追蹤變化，檔案狀態依舊是untracked(`git ss` : `??`)；若先預存，檔案的狀態會變成 `A ` ，此時做修改會變成 `AM`；在預存變成 `A `；最後提交就 `clean`

類型二: 已被控管的檔案或目錄

|階段|操作|`git s`|`git ss`|
|-|-|-|-|
|Workspace|修改|modified|&emsp;M|
||刪除|deleted|&emsp;D|
|||untracked|？？|
|Index|預存|staged|M |
||改名|renamed|R |
||刪除|deleted|D|
|Repo|提交|clean||

說明:

1. 移動(move)或改名(rename)對Git來說是刪除原有檔案再進行操作，所以在工作區會有兩個狀態(`D`與`??`)，預存後就只會有一個狀態(`R`)

### Git commands

```bash
git status
git status -s
# ==================================
git diff
git diff --staged
git diff HEAD
# ==================================
git log [--oneline | --graph | -n 3]
git reflog
```

notes:

1. `git ss` 在workspace為紅色，在index為綠色(理解為紅燈停綠燈行)

### 解除管控

> 找出 `.git` 所在位置並刪除

```bash
rm -rf .git # bash
remove-item -force .git # pwsh
```

## 安裝

- Installing on Linux\
  `sudo apt install git-all`
- Installing on Windows\
  [Download link][1]

## 設定

```bash
git help | -h | --help
git version | -v | --version
git config list
```

note:

- 如果 Git 發現檔案 B 的內容與檔案 A 的內容高度相似（預設相似度門檻是 50%），它就會自動判定這個操作是 Renamed，而不是 Deleted 後再 Added。
  - 調整相似度: `git config diff.renameThreshold 100`
  - 關閉此功能: `git config diff.renames false`

## Aliases

- [gitalias.txt][2]
- 將檔案放置於 `C:\Users\User`
- 使設定生效 `git config --global include.path ~/gitalias.txt`

## References

- [Cheat Sheet](https://git-scm.com/cheat-sheet)
- [Visual Git Cheatsheet](https://ndpsoftware.com/git-cheatsheet.html#loc=index;)
- [Official Git Reference](https://git-scm.com/docs)
- [Oh My Posh Git Segments](https://ohmyposh.dev/docs/segments/scm/git)
- [GitHub ssh](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh)
- [Pro Git 中文翻譯、對照表與規範](https://gist.github.com/fntsrlike/cf1e96d60b6f34fab725599b06dfcb2a)

[1]: <https://git-scm.com/downloads>
[2]: https://github.com/GitAlias/gitalias?tab=readme-ov-file
