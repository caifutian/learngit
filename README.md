把本地仓库的所有内容推送到远程库上:git push -u origin master
推送当前commit内容推送到远程库上： git push origin master 
查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>或者git switch <name>

创建+切换分支：git checkout -b <name>或者git switch -c <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>

查看分支合并情况:git log --graph --pretty=oneline --abbrev-commit
