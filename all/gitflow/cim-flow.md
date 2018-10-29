# Git Flow规范

## 分支规范描述

### master

1. 无止境的生命周期
1. 稳定的分支，不允许有代码提交，只允许有Merge Requst和Merge
1. 用于版本发布及上线
1. 与线上运行的代码一致
1. 只接受`release`，`hotfix`的`Merge Request`
1. 版本发布完之后，产生tag，上线，并`merge`到`develop`分支及其他需要`merge`的分支

### develop

1. 无止境的生命周期
1. 不稳定的分支，用于开发阶段的分支，允许有代码提交，建议只使用`Merge Request`和`Merge`
1. 只允许发布到开发集成测试环境
1. 只接受`release`、`feature`、`bugfix`、`hotfix`和`master`的`Merge Request`

### release/version/{verisonNumber}

1. 变量 `{versionNumber}` 对应该项目接下来上线的版本号
1. 生命周期只在提交QA测试到本次版本上线之间
1. 不稳定的分支，用QA测试阶段的分支，允许有代码提交，建议只使用Merge Request或Merge
1. 只允许发布到QA集成测试环境
1. 可以接受`bugfix`、`hotfix`和`feature`的`Merge Requst`
1. 一般来说，基于`develop`分支来创建，特殊情况下（修复多个线上的bug），可以基于`hotfix`分支创建

### feature/issue/{issueNumber}

1. 变量 `{issueNumber}` 对应该项目在PPM上的一个 `issue number`
1. 生命周期只是开发一个功能的阶段，建议不要超过两天
1. 不稳定的分支，用于开发单个功能
1. 不允许提交到任何集成测试环境
1. 默认基于`develop`分支来创建，特殊情况下（已经提交QA测试，产品新增需求）允许基于`release`分支创建
1. 生命周期结束`Merge`到`develop`分支

### bugfix/issue/{issueNumber}

1. 变量 `{issueNumber}` 对应该项目在PPM上的一个 `issue number`
1. 生命周期只是解决一个bug的阶段，应该不超过一天
1. 不稳定的分支，用于解决QA环境单个`bug`
1. 不允许提交到任何集成测试环境
1. 默认基于`release`分支来创建
1. 生命周期结束`Merge`到`release`和`develop`分支

### hotfix/issue/{issueNumber}

1. 变量 `{issueNumber}` 对应该项目在PPM上的一个 `issue number`
1. 生命周期只是解决一个bug的阶段，应该不超过一天
1. 不稳定的分支，用于解决生产环境单个`bug`
1. 只允许发布到QA集成测试环境
1. 默认基于`master`分支来创建，特殊情况下（同时修复的不止一个生产环境的bug）允许基于`release`分支创建
1. 生命周期结束`Merge`到`master`或`release`分支