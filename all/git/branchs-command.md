# 分支相关命令


## branch

### 查看、切换、创建和删除分支

```bash
git branch -r # 查看远程分支
git branch <new_branch> # 创建新的分支
git branch -v # 查看各个分支最后提交信息
git branch --merged # 查看已经被合并到当前分支的分支
git branch --no-merged # 查看尚未被合并到当前分支的分支
git checkout <branch> # 切换到某个分支
git checkout -b <new_branch> # 创建新的分支，并且切换过去
git checkout -b <new_branch> <branch> # 基于branch创建新的new_branch
git checkout $id # 把某次历史提交记录checkout出来，但无分支信息，切换到其他分支会自动删除
git checkout $id -b <new_branch> # 把某次历史提交记录checkout出来，创建成一个分支
git branch -d <branch> # 删除某个分支
git branch -D <branch> # 强制删除某个分支 (未被合并的分支被删除的时候需要强制)
```

### 分支合并和rebase

```bash
git merge <branch> # 将branch分支合并到当前分支
git merge origin/master --no-ff # 不要Fast-Foward合并，这样可以生成merge提交
git rebase master <branch> # 将master rebase到branch，相当于： git checkout <branch> && git rebase master && git co master && git merge <branch>
```



### Git远程分支管理 Pull,Push & Merge

#### 首次提交和绑定分支
```bash
git push -u origin master # 客户端首次提交
git push -u origin develop # 首次将本地develop分支提交到远程develop分支，并且track
```

#### 常用的和远程分支相关的命令

```bash
git pull # 抓取远程仓库所有分支更新并合并到本地
git pull --no-ff # 抓取远程仓库所有分支更新并合并到本地，不要快进合并
git fetch origin # 抓取远程仓库更新
git merge origin/master # 将远程主分支合并到本地当前分支
git checkout --track origin/branch # 跟踪某个远程分支创建相应的本地分支
git checkout -b <local_branch> origin/<remote_branch> # 基于远程分支创建本地分支，功能同上
git push # push所有分支
git push origin master # 将本地主分支推到远程主分支
git push -u origin master # 将本地主分支推到远程(如无远程主分支则创建，用于初始化远程仓库)
git push origin <local_branch> # 创建远程分支， origin是远程仓库名
git push origin <local_branch>:<remote_branch> # 创建远程分支
git push origin :<remote_branch> #先删除本地分支(git br -d <branch>)，然后再push删除远程分支Git远程仓库管理
```

### 远程仓库管理

```bash
git remote -v # 查看远程服务器地址和仓库名称
git remote show origin # 查看远程服务器仓库状态
git remote add origin git@git.cimyun.com:gitbook/cim-engineer-manual.git # 添加远程仓库地址
git remote set-url origin git@git.cimyun.com:gitbook/cim-engineer-manual.git #设置远程仓库地址(用于修改远程仓库地址) 
git remote rm <repository> # 删除远程仓库创建远程仓库
```


### 绑定远程和本地分支

```bash
git branch --set-upstream master origin/master
git branch --set-upstream develop origin/develop
```