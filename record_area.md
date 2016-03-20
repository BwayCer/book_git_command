Git 紀錄區
=======


> Git 裡的三種紀錄區：
>   - 工作目錄（Working Directory）
>   - 暫存區（Staging Area）
>   - 儲存庫（Repository）
>
> 本節所提語法：
>   - git status
>   - git add <檔名_1>[ <檔名_2>]\[ ...]
>   - git commit -m "<自定義名稱>"
>   - git commit -am "<自定義名稱>"
>   - git checkout -- <檔名_1>[ <檔名_2>]\[ ...]
>   - git reset HEAD <檔名_1>[ <檔名_2>]\[ ...]
>   - git log



## 顯示目前桌面

```sh
$ git status
```

顯示訊息：

  - 所在分支： On branch 分支名稱
  - 未被追蹤： Untracked files
  - 檔案已被修改： Changes not staged for commit
  - 檔案可被提交： Changes to be committed
  - 檔案未完成合併（合併時互相衝突）： Unmerged paths
  - 各種訊息 ...

___顯示各種提示訊息，建議動作前先查看桌面狀態。___



## 提交檔案流程

```
未追蹤 | 儲存庫 | 修改 | 暫存區
  o -------------------> |   ( git add <檔案> )
          o ----> |          ( 編輯檔案 )
                  o ---> |   ( git add <檔案> )
          | <---- o          ( git commit -am "<自定版本名稱>" )
          | <----------- o   ( git commit -m "<自定版本名稱>" )
                  | <--- o   ( git checkout -- <檔案> )
  | <------------------- o   ( git reset HEAD <檔案> )
```



## 工作目錄

```sh
$ git status
> Changes not staged for commit :
>   檔案名稱 ...
```


將檔案移至「暫存區」存放：

```sh
$ git add <檔名_1>[ <檔名_2>][ ...]
```


略過暫存區，直接將全部檔案（_不包含未追蹤的檔案_）作為版本提交至儲存庫紀錄：

```sh
$ git commit -am "<自定義名稱>"
# git commit -am = git add -A + git commit -m "<自定版本名稱>"
```


復原檔案回修改前的紀錄：

```sh
$ git checkout -- <檔名_1>[ <檔名_2>][ ...]
```



## 暫存區

紀錄著修改且準備提交的檔案清單。<br />
暫存區可看作一個還在修改中的暫時提交紀錄，譬如在對比檔案差異 ``` git diff ``` 時，其可與工作目錄裡未提交的檔案做比較。



```sh
$ git status
> Changes to be committed :
>   檔案名稱 ...
```


提交此檔案清單作為版本紀錄於儲存庫：

```sh
$ git commit -m "<自定版本名稱>"
```



## 儲存庫

```sh
$ git log
> commit 版本號碼
> Author: 作者 <信箱>
> Date:   日期時間
>
>    版本名稱
```


## 參考資料

  - [Git - 基礎要點](https://git-scm.com/book/zh-tw/v1/開始-Git-基礎要點)
  - [Git - 提交更新到儲存庫](https://git-scm.com/book/zh-tw/v1/Git-基礎-提交更新到儲存庫)

