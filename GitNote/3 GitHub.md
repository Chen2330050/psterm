# GitHub

### clone

```bash
git clone url
git clone url path-name
```

### fetch & push

```bash
git fetch origin
git push origin master [-f]
```

### remote

```bash
# 顯示遠端分支 [顯示網址]
git remote [-v]
git remote add origin git@github.com:waynechen0220/psterm.git 
git remote rename origin origin2
git remote remove origin2
```

### GitHub

1. 檢查是否已有SSH密鑰

    bash: `ls -al ~/.ssh`

    pwsh: `get-childitem -path ~/.ssh`

    1.1 若有的話會顯示類似於下方的訊息

    > id_ed25519
    >
    > id_ed25519.pub

   1.2 若無，生成一個

   `ssh-keygen -t ed25519 -C "<waynechen0220@gmail.com>"`

2. 複製公鑰到GitHub設定頁面

    bash: `clip < ~/.ssh/id_ed25519.pub`

    pwsh: `cat ~/.ssh/id_ed25519.pub | clip`

3. 測試與GitHub ssh連線狀況

    `ssh -T git@github.com`

    3.1 連線成功:

    > Hi waynechen0220! You've successfully authenticated, but GitHub does not provide shell access.

    3.2 連線失敗:

4. 到GitHub頁面新增一個倉庫

5. 新增遠端倉庫

    `git remote add origin git@github.com:waynechen0220/psterm.git`

6. 推送本地分支到遠端分支

    `git push origin master`
