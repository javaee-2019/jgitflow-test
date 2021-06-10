
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


加强版:
mvn jgitflow:feature-start -DallowSnapshots=true          ：DallowSnapshots 参数不给会报错。

mvn jgitflow:feature-finish -DallowSnapshots=true -Dmaven.test.skip=true      需要加-D频闭测试阶段

mvn jgitflow:release-start -DallowSnapshots=true -DautoVersionSubmodules=true -Dmaven.test.skip=true

mvn jgitflow:release-finish -DallowSnapshots=true -Dmaven.test.skip=true -Dmaven.javadoc.skip=true

-DallowSnapshots=true:是指允许在release finish时，在pom中包含为SNAPSHOT的依赖包。

如果编译报javadoc插件注解异常，则加该参数解决-Dmaven.javadoc.skip=true

mvn jgitflow:release-start -DallowSnapshots=true -DautoVersionSubmodules=true -Dmaven.test.skip=true
```