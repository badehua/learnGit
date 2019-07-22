# 学习git命令行
`mkdir learngit`    创建文件夹<br>
`cd learngit`    切换到learngit文件夹<br>
`pwd`    查看当前目录<br>
`cat readme.txt`    查看readme.txt文件内容<br>
`rm readme.txt`    删除文件<br>
`ls` 查看文件目录<br>
## 创建版本库
`git init`    初始化，把当前文件夹变成git可以管理的仓库<br>
## 添加、提交文件
`git add readme.txt`    添加readme.txt文件到仓库<br>
`git commit -m 'xxx'`    把文件提交到仓库，-m 'xxx'表示本次提交的说明，引号内可以输入任意内容<br>
`git status`    查看仓库当前状态<br>
`git diff readme.txt`    查看修改内容<br>
## 历史、版本回退
`git log`    查看历史记录<br>
`git log --pretty=oneline`    简化版历史记录<br>
`git reset --hard HEAD^`    回退到上一版本,HEAD^表示上一版本，HEAD^^表示上上版本,HEAD~10表示前10个版本<br>
`git reset --head 1094a`    回退到commit id 为1094a...的版本，版本号写前几位，但不能只写前一两位<br>
`git reflog`   查看所有的命令历史<br>
## 管理、撤销修改及删除文件
`git diff HEAD -- readme.txt`   查看工作区与版本库最新版本区别<br>
`git checkout -- readme.txt`    丢弃工作区更改，回到最近一次git commit或git add时的状态<br>
`git reset HEAD readme.txt`    把暂存区的修改撤销，重新放回工作区<br>
`git rm readme.txt`  ,  `git commit -m 'remove readme.txt'`   删除readme.txt文件，并提交修改<br>
## 添加远程仓库
`git remote add origin git@github.com:badehua/learngit.git `    链接到远程仓库<br>
`git push -u origin master`    把当前master分支推送到远程。由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令<br>
## 删除关联的远程仓库
`git remote rm origin`
## 从远程库克隆
`git clone git@github.com:badehua/learngit.git ` 克隆远程仓库<br>
`git branch -r` 查看远程分支<br>
`git branch -a` 查看所有分支<br>
## 分支管理
`git checkout -b dev` 创建dev分支，然后切换到dev分支<br>
`git branch dev`,`git checkout dev` 这两行命令等价于第一行的命令<br>
`git branch` 查看本地所有分支，*号代表当前分支<br>
`git merge dev` 把dev分支到当前分支，Fast-forward模式，这种模式下，删除分支后，会丢掉分支信息<br>
`git branch -d dev` 删除dev分支<br>
当存在冲突时，Git用<<<<<<<，=======，>>>>>>>标记出不同分支的内容
`git log --graph --pretty=oneline --abbrev-commit` 查看分支的合并情况<br>
`git merge --no-ff -m 'merge with no-ff' dev` 普通模式合并，合并后的历史有分支，能看出来曾经做过合并，引号中写入说明<br>
`git stash` 贮藏，临时把工作现场储藏起来，之后可以恢复继续工作<br>
`git stash list` 查看贮藏列表<br>
`git stash apply` 恢复工作内容，但stash内容并不删除<br>
`git stash drop` 通过此命令删除<br>
`git stash pop` 恢复同时删除stash内容<br>
`git stash apply stash@{0} ` 多次stash，恢复指定stash<br>
`git branch -D feature-vulcan` 强行删除feature-vulcan分支。如果要丢弃一个没有被合并过的分支，可以通过git branch -D <name>强行删除<br>
`git remote -v` 查看远程库信息<br>
`git checkout -b dev origin/dev` 检出远程dev分支，并在本地起名dev分支,切换到本地dev分支<br>
`git branch --set-upstream branch-name origin/branch-name` 建立本地分支与远程分支的关联<br>
`git pull` 抓取远程新提交<br>
`git rebase` 变基。把分叉的提交历史“整理”成一条直线，看上去更直观<br>
## 标签管理
`git tag v1.0` 打标签<br>
`git tag` 查看所有标签<br>
`git tag v0.9 f53c633` 给commit id为f52c633的提交打标签<br>
`git show v0.9` 查看标签信息<br>
`git tag -a v0.1 -m 'xxx' 1094adb` 创建带有说明的标签，-a指定标签名，-m指定说明文字<br>
`git tag -d v0.1` 删除标签<br>
`git push origin v0.1` 推送标签到远程<br>
`git push origin --tags` 一次性推送全部尚未推送到远程的本地标签<br>
`git tag -d v0.9`,`git push origin :refs/tags/v0.9` 删除远程标签，先删除本地，然后删除远程<br>