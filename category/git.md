##### REBASE代码
* 原理：

      1、代码回溯到修改之前，将当前分支的代码，保存起来    
      2、利用提交的序列信息，重新构建主干提交记录    
      http://www.fwqtg.net/%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3git-rebase%E6%B5%81%E7%A8%8B.html   
      http://segmentfault.com/a/1190000002422158    
      http://www.cnblogs.com/sinojelly/archive/2011/08/07/2130172.html   
      http://stackoverflow.com/questions/2660977/what-does-it-mean-when-git-says-a-file-needs-update

* 操作方式（前提:待rebase分支:A，被rebase分支:B--如master）：

    方法：
    
      1、基于线上分支A，checkout新的分支C，并以分支C来rebaes分支B，rebase后，将心分支C提交，最终提出merge到分支A  
      线上分支A: origin/A
    
      2、基于本地分支A, 以此分支rebase 分支B，rebase结束后，可以直接提交到分支A   
      本地分支A: A
    
    流程：   
    
      1、到待rebase分支下，git rebase B ，会创建临时分支（后面的conflict修改，都会基于临时分支，conflict修复后，会返回rebase前的分支）   
      2、出现conflict，解决冲突，然后git add. 索引新的rebase修改   
      3、执行性git rebase --continue 或者 git rebase --abort 放弃本次rebase   
      4、如果继续有冲突，重复步骤2    
      5、rebase完之后，可以git push orgin 分支A或者是新建的分支A`然后在merge  
    注意： `如果在修复conflict的时候，如果对原属于A的代码做了修改，需要在push之前，先git pull 修复冲突`


##### git 基本操作（紧挨git命令的是被操作分支，如果省略，则是当前分支）
*  git push origin xxx  新checkout的分支可以push出任意新的分支，但不是push 任意已有分支
*  git reset --hard  修改未提交，删除不需要加head，或者某次提交的哈希码
*  git pull origin xxx  对比git push origin xxx ，git pull 可以指定更新任何分支的代码
*  git branch --set-upstream A B  手动建立追踪关系。