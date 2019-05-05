.gitconfig 設定檔
=======


> <span style="color: red;">此篇僅為筆者個人習慣，僅供參考。</span>


```
[user]
    name = <GitHub 帳號>
    email = <GitHub 信箱>
[push]
    default = simple
[color]
    ui = true
[alias]
    st = status
    brmv = !sh -c \"git checkout -b $2 $1 && git branch -D $1\"
    rtv = remote -v
    rtmv = !sh -c \"git remote remove $1 && git remote add $1 $2\"
    hist = log --pretty=format:'%C(yellow)%h %C(white)%ad | %s%C(yellow)%d %C(white)[%an]' --graph --date=short
    histall = log --pretty=format:'%C(yellow)%h %C(white)%ad | %s%C(yellow)%d %C(white)[%an]' --graph --date=short --all
    histinfo = log --pretty=format:'%C(yellow)%h %C(white)%ad | %s%C(yellow)%d %C(white)[%an]' --graph --date=short --stat
    histdiff = log --pretty=format:'%C(yellow)%h %C(white)%ad | %s%C(yellow)%d %C(white)[%an]' --graph --date=short -p
    lookfor = log --pretty=format:'%C(yellow)%h %C(white)%ad | %s [%an]' --date=format:'%Y-%m-%d %H:%M:%S' --stat --all-match --grep
[core]
    excludesfile = ~/.gitignore_global
    editor = vim
```

