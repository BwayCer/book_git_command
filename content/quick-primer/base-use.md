基本流程
=======


> 本節所提語法：
>   - git config --global user.name <名稱>
>   - git config --global user.email  <信箱>
>   - git init
>   - git status
>   - git branch
>   - git branch <分支名>
>   - git branch -d <分支名>
>   - git branch -D <分支名>
>   - git checkout <分支名>
>   - git checkout -b <分支名>
>   - git add <檔名_1>[ <檔名_2>]\[ ...]
>   - git add .
>   - git commit -m "<自定版本名稱>"
>   - git log
>   - git merge <分支名>
>   - git rebase master
>   - git clone <GitHub 網址.git>
>   - git remote -v
>   - git remote add origin <GitHub 網址.git>
>   - git push origin <分支名>
>   - git pull origin



## Git 初始化

當 Git 套件完成安裝，先指定其使用者：

```sh
$ git config --global user.name <名稱>
$ git config --global user.email  <信箱>
```

__# 使用者是指在 GitHub 上註冊的帳號__


再來開啟專案資料夾，建立 Git 版本控制：

```sh
$ git init
```

如此一來就可以開始 Git 的旅程了~~~



## 本地端

### 第一筆 Git 紀錄

當修改好檔案後來查看工作桌面：

```sh
$ git status
```

工作桌面會顯示所在分支及檔案追蹤情形 ... 等其他資訊。

再來加入該檔案至暫存區：

```sh
$ git add <檔名_1>[ <檔名_2>][ ...]

# 加入所有檔案
$ git add .
```

提交版本至儲存庫紀錄：

```sh
$ git commit -m "<自定版本名稱>"
```

這樣就完成版本紀錄，來查看目前的版本訊息：

```sh
$ git log
```


### 使用分支

先創建分支：

```sh
$ git branch <分支名>
# 不需雙引號 不能有空白格

# 顯示分支清單
$ git branch
```

再切換至該分支：

```sh
$ git checkout <分支名>

# 也可以一次完成創建和切換
$ git checkout -b <分支名>
```

當我們完成修改並已提交版本紀錄，再來就要讓分支與主幹合併：

```sh
# 所在分支： master
$ git merge <分支名>
```

有時候當主幹上有較新的版本紀錄時，為了讓線圖更整潔而會先嫁接分支至主幹的最新版本再進行合併：

```sh
# 所在分支： 需做嫁接的分支
$ git rebase master
```

為了某目的創建的分支，在合併後功成身退，就可以刪除了：

```sh
$ git branch -d <分支名>
```

如果是未合併而半途作廢的分支則須強制刪除：

```sh
# 強制刪除分支
$ git branch -D <分支名>
```



## 遠程端

專案有可能是自己或別人發起，若是由他人發起則先至 GitHub 下載專案：

```sh
$ git clone <GitHub 網址.git>
```

否則則是先指定遠程主機的連結：

```sh
$ git remote add origin <GitHub 網址.git>

# 顯示主機連結
$ git remote -v
```

上傳至 GitHub：

```sh
$ git push origin <分支名>
```

當專案已在本機上，但遠端主機的版本比本地更新時則是要與 GitHub 同步：

```sh
$ git pull origin
```

