# 学习git命令行
mkdir learngit  创建文件夹<br>
cd learngit 切换到learngit文件夹<br>
pwd  查看当前目录<br>
## 创建版本库
git init 初始化，把当前文件夹变成git可以管理的仓库
git add readme.txt 添加readme.txt文件到仓库
git commit -m 'xxx' 把文件提交到仓库，-m 'xxx'表示本次提交的说明，引号内可以输入任意内容
git status 查看仓库当前状态
git diff readme.txt 查看修改内容
git log 查看历史记录
git log --pretty=oneline 简化版历史记录