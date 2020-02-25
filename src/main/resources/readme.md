
###规范
```
开发
develop->拉取feature分支开发->版本号不变,建议提交远程仓库->开发完成finnish
->版本号不变,合并到develop分支,删除feature分支
提测
develop->拉取release分支提测->版本号依次+1,提交远程仓库->提测修改bug完毕,finnish
->合并到develop,同时合并到master master去掉snapshot版本号+1,删除release分支
紧急BUG
master->拉取hotfix分支修补bug->修改完毕 finish
->合并到master分支和develop分支，如果当前还有新功能release分支，也同步到release分支上
```

###常用命令
```
mvn jgitflow:feature-start

mvn jgitflow:feature-finish

mvn jgitflow:release-start

mvn jgitflow:release-finish

mvn jgitflow:hotfix-start

mvn jgitflow:hotfix-finish

```