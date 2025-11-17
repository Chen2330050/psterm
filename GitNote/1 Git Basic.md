# Git Basic

### init

```bash
git init
```

### add & rm & mv

```bash
git add file-name
git add -u # not include new file
git add .
git rm file-name
git mv old-file new-file
```

### restore

```bash
# unstage: Index -> Workspace
git restore --staged file-name | .
git reset

# discard changes: Workspace -> None
# !!! DANGER COMMAND !!!
git restore file-name | .
git checkout file-name
```

### commit

```bash
# 正常提交
git commit -m "message"

# 和上次合併提交
git commit --amend

# 修改上次提交內容(若工作區或預存區有改變將提交為新的commit)
git commit -a -m "message"
```

message:

 1. new, add
 2. modify, update
 3. remove, rename, move

### reset

```bash
# move HEAD&master
# Repo -> Index
git reset --soft commit

# Repo -> Workspace-Modified
git reset [--mixed] commit

#Repo -> Workspace-Unmodified
git reset --hard commit
```

note:

- 雖然 `git reset` = `git restore --staged .` 但建議不同類型的任務使用不同的指令
- commit可以是
  - SHA-1雜湊碼 (commit ID)
  - HEAD^ 或 HEAD~3
  - HEAD@{2} (reflog)

### stash

```bash
git stash
git stash list
git stash pop | apply # 套用並清除該歷史紀錄 | 不清除歷史(可以再次使用)
git stash drop stash@{n} # 清除指定stash
git stash clear # 清除所有stash
```
