# Git Branch

## 基本概念

1. 提交(commit)概念上等同於版本(version)
2. 分支(branch)是由一系列提交(commit)所構成的歷史線路，而分支名稱(branch name)就是指向這條線路最新提交(commit)的指標

## branch

```bash
# 顯示
git branch
git branch -all
git branch --merged | --no-merged

# 建立
git branch branch-name
git switch -c branch-name
git checkout -b branch-name

# 切換
git switch branch-name
git checkout branch-name

# 刪除與改名
git branch -d branch-name
git branch -m old-branch new-branch
```

## merge

```bash
# on branch main, dev -> main
git merge dev
```
