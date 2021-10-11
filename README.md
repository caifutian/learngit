把本地仓库的所有内容推送到远程库上:git push -u origin master
推送当前commit内容推送到远程库上： git push origin master 
查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>或者git switch <name>

创建+切换分支：git checkout -b <name>或者git switch -c <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>

查看分支合并情况:git log --graph --pretty=oneline --abbrev-commit

当手头工作没有完成时，先把工作现场git stash一下，然后去修复bug，修复后，再git stash pop，回到工作现场；
在master分支上修复的bug，想要合并到当前dev分支，可以用git cherry-pick <commit>命令，把bug提交的修改“复制”到当前分支，避免重复劳动。
保存当前工作区修改:$ git stash
$ git checkout master 或 $git switch master 切换到master分支
$ git checkout -b issue-101 新建bug 分支修复问题
$ git add readme.txt 
$ git commit -m "fix bug 101" 提交完切换回master合并
$ git switch master 
$ git merge --no-ff -m "merged bug fix 101" issue-101
$ git branch -d issue-101 合并完删掉issue-101分支

同样的bug在dev分支上可以把issue-101的修复合并过来
$ git switch master
$ git log --pretty=oneline 查看issue-101修复id
$ git switch dev
$ git cherry-pick xxxx 合并issue-101到dev
$ git stash pop   恢复之前手头工作没有完成时的修改

如果要丢弃一个没有被合并过的分支，可以通过git branch -D <name>强行删除。

命令git tag <tagname>用于新建一个标签，默认为HEAD，也可以指定一个commit id；

命令git tag -a <tagname> -m "blablabla..."可以指定标签信息；

命令git tag可以查看所有标签。

命令git push origin <tagname>可以推送一个本地标签；

命令git push origin --tags可以推送全部未推送过的本地标签；

命令git tag -d <tagname>可以删除一个本地标签；

命令git push origin :refs/tags/<tagname>可以删除一个远程标签。

在GitHub上，可以任意Fork开源仓库；

自己拥有Fork后的仓库的读写权限；

可以推送pull request给官方仓库来贡献代码。

忽略某些文件时，需要编写.gitignore；

.gitignore文件本身要放到版本库里，并且可以对.gitignore做版本管理！

