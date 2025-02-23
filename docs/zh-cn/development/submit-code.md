#### 提交代码流程

* 首先从远端仓库*https://github.com/apache/incubator-dolphinscheduler.git* fork一份代码到自己的仓库中

* 远端仓库中目前有三个分支：
    * master 正常交付分支
	   发布稳定版本以后，将稳定版本分支的代码合并到master上。
    
	* dev    日常开发分支
	   日常dev开发分支，新提交的代码都可以pull request到这个分支上。
	   
    * branch-1.0.0 发布版本分支
	   发布版本分支，后续会有2.0...等版本分支，版本分支只修改bug，不增加新功能。

* 把自己仓库clone到本地
  
    ` git clone https://github.com/apache/incubator-dolphinscheduler.git`

*  添加远端仓库地址，命名为upstream

    ` git remote add upstream https://github.com/apache/incubator-dolphinscheduler.git `

*  查看仓库：

    ` git remote -v`

> 此时会有两个仓库：origin(自己的仓库)和upstream（远端仓库）

*  获取/更新远端仓库代码（已经是最新代码，就跳过）
  
    ` git fetch upstream `


* 同步远端仓库代码到本地仓库

```
 git checkout origin/dev
 git merge --no-ff upstream/dev
```

如果远端分支有新加的分支比如`dev-1.0`,需要同步这个分支到本地仓库

```
git checkout -b dev-1.0 upstream/dev-1.0
git push --set-upstream origin dev1.0
```

* 在本地修改代码以后，提交到自己仓库：
  
    `git commit -m 'commit content'`
    `git push`

* 将修改提交到远端仓库

	* 在github页面，点击New pull request.
		<p align="center">
	   <img src="http://geek.analysys.cn/static/upload/221/2019-04-02/90f3abbf-70ef-4334-b8d6-9014c9cf4c7f.png" width="60%" />
	 </p>
	 
	* 选择修改完的本地分支和要合并过去的分支，Create pull request.
		<p align="center">
	   <img src="http://geek.analysys.cn/static/upload/221/2019-04-02/fe7eecfe-2720-4736-951b-b3387cf1ae41.png" width="60%" />
	 </p>
	
* 接着社区Committer们会做CodeReview，然后他会与您讨论一些细节（包括设计，实现，性能等）。当团队中所有人员对本次修改满意后，会将提交合并到dev分支

* 最后，恭喜您已经成为了dolphinscheduler的官方贡献者！
