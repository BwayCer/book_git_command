.gitconfig 設定檔
=======


> <span style="color: red;">此篇僅為筆者個人習慣，僅供參考。</span>


```sh
[user]
        name = <GitHub 帳號>
        email = <GitHub 信箱>
[push]
        default = simple
[color]
        ui = true
[alias]
        hist = log --pretty=format:'%C(yellow)%h %C(white)%ad | %s%d [%an]' --graph --date=short
        histall = log --pretty=format:'%C(yellow)%h %C(white)%ad | %s%d [%an]' --graph --date=short -all
        histinfo = log --pretty=format:'%C(yellow)%h %C(white)%ad | %s%d [%an]' --graph --date=short --stat
        histdiff = log --pretty=format:'%C(yellow)%h %C(white)%ad | %s%d [%an]' --graph --date=short -p
        lookfor = log --pretty=format:'%C(yellow)%h %C(white)%ad | %s [%an]' --date=format:'%Y-%m-%d %H:%M:%S' --stat --all-match --grep
[core]
        excludesfile = ~/.gitignore_global
        editor = vim
```

