檢視版本紀錄
=======


> 如果想查閱更多請參閱 [git-log 指令（英文版）](https://git-scm.com/docs/git-log)。
>
> 本節所提語法：
>   - git log



## 版本線圖


指令加旗標 `--graph` 可在終端機上以 ASCII 畫出分支的分歧及合併的文字線圖。


```sh
$ git log --graph --oneline
* cer7777 版本 v1.0
|\
| * bway333 編寫 檢視版本紀錄
|/
* 99c5079 v0.0 書籍 Git 基礎操作教程
```


### 自訂格式


當需要輸出給電腦做分析而必須訂定明確地規則格式，又或者習慣以 Git 完全工作，都可以使用此指令來訂製一套專屬的版本線圖輸出格式。

_實際案例可見 [.gitconfig 設定檔](/set_gitconfig.html)。_

```sh
$ git log --pretty=format:"<自訂格式>"

$ git log --graph --pretty=format:'%h %ad | %s%d [%an]' --date=short
* cer7777 2016-08-03 | 版本 v1.0 [BwayCer]
|\
| * bway333 2016-07-09 | 編寫 檢視版本紀錄 [BwayCer]
|/
* 99c5079 2016-03-20 | v0.0.0 書籍 Git 基礎操作教程 [RAiww]
```


 參數 | 說明
:---- |:----
%H    | 該更新的SHA1雜湊值
%h    | 該更新的簡短SHA1雜湊值
%T    | 存放該更新的根目錄的Tree物件的SHA1雜湊值
%t    | 存放該更新的根目錄的Tree物件的簡短SHA1雜湊值
%P    | 該更新的父更新的SHA1雜湊值
%p    | 該更新的父更新的簡短SHA1雜湊值
%an   | 作者名字
%ae   | 作者電子郵件
%ad   | 作者的日期 (格式依據 date 選項而不同)
%ar   | 相對於目前時間的作者的日期
%cn   | 提交者的名字
%ce   | 提交者的電子郵件
%cd   | 提交的日期
%cr   | 相對於目前時間的提交的日期
%s    | 標題
%d    | HEAD 指針及各分支所在位置


※ ___<span style="color: gray;">關於在這裡指的「作者」與「提交者」之間的差別請參閱 [Git - 分散式 Git](https://git-scm.com/book/zh-tw/v1/分散式-Git)。</span>___


### 塗色


```sh
git log --graph --pretty=format:'%C(yellow)%h %C(white)%ad | %s%d [%an]' --date=short
```


 參數                | 說明
:----                |:----
%C(&lt;顏色代碼&gt;) | 顏色代碼例如： yellow、#FFFF00。
%Cred               | 顯示紅色。
%Cgreen              | 顯示綠色。
%Cblue               | 顯示藍色。


### 常用選項


 選項           | 說明
:----           |:----
--pretty        | 設定顯示格式。其選項包含 oneline、short、full、fuller 及可自訂格式的 format。
--oneline       | 同 `--pretty=format:'%C(yellow)%h %s%d'` 的簡短用法。
--abbrev-commit | 僅顯示SHA1查核值的前幾位數，而不是顯示全部的40位數。
--date          | 其選項有short及可自訂格式的 format。
--relative-date | 以相對於目前時間方式顯示日期（例如：“2 weeks ago”），而不是完整的日期格式。
-p              | 顯示每個更新與上一個的差異。
--stat          | 顯示每個更新更動的檔案的統計及摘要資訊。
--shortstat     | 僅顯示 `--stat` 提供的的訊息中關於更動、插入、刪除的文字。
--name-status   | 顯示新增、更動、刪除的檔案列表。
--name-only     | 在更新的訊息後方顯示更動的檔案列表。
--word-diff     | 使用 word diff 格式顯示 patch 內容。



## 搜尋


 選項             | 說明
:----             |:----
-&lt;n&gt;        | 僅顯示最後 n 筆更新
--since, --after  | 列出特定日期後的更新。
--until, --before |	列出特定日期前的更新。
--author          | 列出作者名稱符合指定字串的更新。
--committer       | 列出提交者名稱符合指定字串的更新。
--grep            | 列出版本描述符合指定字串的更新。
--all-match       | 比對多個字串（否則只會列出符合任一條件的更新）。
-- &lt;檔名&gt;   | 過濾路徑。一般會在前方加上 `--` 用以區別。


關於指定時間範圍的方式：

關於 `--since` 及 `--until` 指令選項可指定特定或相對的日期。

```sh
# 特定日期
$ git log --since=1911-10-10

# 相對日期 如： years day minutes 等
$ git log --since=2.weeks
```



## 參考資料

  - [Git - 檢視提交的歷史記錄](https://git-scm.com/book/zh-tw/v1/Git-基礎-檢視提交的歷史記錄)
  - [多种颜色和自定义log格式 - 纯粹互联网](https://www.pureweber.com/article/git-pretty-output/)

