# 基本操作命令

## add

```bash
git add <file> # 将工作文件修改提交到本地暂存区
git add . # 将所有修改过的工作文件提交暂存区
```

## checkout

```bash
git checkout <file> 　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　
git checkout -am "some comments" #提交当前未提交的内容，并添加commit message
git checkout --amend # 修改最后一次提交记录
```


## show

```bash
git show <SHA1> # 显示某次提交的内容 git show 4940c99
```

## checkout

```bash
git checkout -- <file> # 抛弃工作区修改
git checkout . # 抛弃工作区修改
git checkout <file> # 抛弃工作区具体一个文件的修改
```

、找回，重置修改文件

## rm

```bash
git rm <file> # 从版本库中删除文件
git rm <file> --cached # 从版本库中删除文件，但不删除文件
```

## reset

```bash
git reset <file> # 从暂存区恢复到工作文件
git reset -- . # 从暂存区恢复到工作文件
git reset --hard # 恢复最近一次提交过的状态，即放弃上次提交后的所有本次修改
```

## revert

```bash
git revert <$id> # 恢复某次提交的状态，恢复动作本身也创建次提交对象
git revert HEAD # 恢复最后一次提交的状态
```

## diff

```
git diff <file> # 比较当前文件和暂存区文件差异 git diff
git diff <id1><
id2> # 比较两次提交之间的差异
git diff <branch1>..<branch2> # 在两个分支之间比较
git diff --staged # 比较暂存区和版本库差异
git diff --cached # 比较暂存区和版本库差异
git diff --stat # 仅仅比较统计信息
```

## log

```
git log git log <file> # 查看该文件每次提交记录
git log -p <file> # 查看每次详细修改内容的diff
git log -p -2 # 查看最近两次详细修改内容的diff
git log --stat #查看提交统计信息
```

## Git补丁管理(方便在多台机器上开发同步时用)

```bash
git diff > ../sync.patch # 生成补丁
git apply ../sync.patch # 打补丁
git apply --check ../sync.patch #测试补丁能否成功
```

## stash

```bash
git stash # 暂存
git stash list # 列所有stash
git stash apply # 恢复暂存的内容
git stash drop # 删除暂存区
```