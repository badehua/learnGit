# 学习git命令行
mkdir learngit  `创建文件夹`<br>
cd learngit 切换到learngit文件夹<br>
pwd  查看当前目录<br>
cat readme.txt 查看readme.txt文件内容<br>
## 创建版本库
git init 初始化，把当前文件夹变成git可以管理的仓库<br>
## 添加、提交文件
git add readme.txt 添加readme.txt文件到仓库<br>
git commit -m 'xxx' 把文件提交到仓库，-m 'xxx'表示本次提交的说明，引号内可以输入任意内容<br>
git status 查看仓库当前状态<br>
git diff readme.txt 查看修改内容<br>
## 历史、版本回退
git log 查看历史记录<br>
git log --pretty=oneline 简化版历史记录<br>
git reset --hard HEAD^ 回退到上一版本,HEAD^表示上一版本，HEAD^^表示上上版本,HEAD~10表示前10个版本<br>
git reset --head 1094a 回退到commit id 为1094a...的版本，版本号写前几位，但不能只写前一两位<br>
