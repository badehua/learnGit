# 学习git命令行
mkdir learngit    `创建文件夹`<br>
cd learngit    `切换到learngit文件夹`<br>
pwd    `查看当前目录`<br>
cat readme.txt    `查看readme.txt文件内容`<br>
rm readme.txt    `删除文件`<br>
## 创建版本库
git init    `初始化，把当前文件夹变成git可以管理的仓库`<br>
## 添加、提交文件
git add readme.txt    `添加readme.txt文件到仓库`<br>
git commit -m 'xxx'    `把文件提交到仓库，-m 'xxx'表示本次提交的说明，引号内可以输入任意内容`<br>
git status    `查看仓库当前状态`<br>
git diff readme.txt    `查看修改内容`<br>
## 历史、版本回退
git log    `查看历史记录`<br>
git log --pretty=oneline    `简化版历史记录`<br>
git reset --hard HEAD^    `回退到上一版本,HEAD^表示上一版本，HEAD^^表示上上版本,HEAD~10表示前10个版本`<br>
git reset --head 1094a    `回退到commit id 为1094a...的版本，版本号写前几位，但不能只写前一两位`<br>
git reflog   `查看所有的命令历史`<br>
## 管理、撤销修改及删除文件
git diff HEAD -- readme.txt   `查看工作区与版本库最新版本区别`<br>
git checkout -- readme.txt    `丢弃工作区更改，回到最近一次git commit或git add时的状态`<br>
git reset HEAD readme.txt    `把暂存区的修改撤销，重新放回工作区`<br>
git rm readme.txt    git commit -m 'remove readme.txt'   `删除readme.txt文件，并提交修改`<br>