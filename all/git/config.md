# 基本配置

## 配置用户信息

```bash
git config --global user.name "Tony Deng"
git config --global user.email 'wolf.deng@gmail.com'
```

## 查看配置

```bash
git config list
```

### 我的配置

#### Git全局配置

```bash
credential.helper=osxkeychain
user.name=Tony Deng
user.email=wolf.deng@gmail.com
core.editer=vim
core.color=true
core.excludesfile=~/.gitignore_global
color.branch=auto
color.diff=auto
color.status=auto
color.branch.current=yellow reverse
color.branch.remote=green
color.branch.local=yellow
color.diff.meta=yellow bold
color.diff.frag=magenta bold
color.diff.old=red bold
color.diff.new=green bold
color.status.added=yellow
color.status.changed=green
color.status.untracked=cyan
push.default=simple
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
core.precomposeunicode=true
```

#### Git命令别名配置

```bash
alias.co=checkout
alias.br=branch
alias.ci=commit
alias.st=status
alias.lg=log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen (%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --
alias.lga=log --graph --all
alias.mrg=merge --no-ff
```

#### 当前项目配置

```bash
remote.origin.url=git@git.cimyun.com:gitbook/cim-engineer-manual.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.master.remote=origin
branch.master.merge=refs/heads/master
gitflow.branch.master=master
gitflow.branch.develop=develop
gitflow.prefix.feature=feature/
gitflow.prefix.release=release/
gitflow.prefix.hotfix=hotfix/
gitflow.prefix.support=support/
gitflow.prefix.versiontag=
branch.develop.remote=origin
branch.develop.merge=refs/heads/develop
```