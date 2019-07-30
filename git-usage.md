# 配置
## 全局配置
git config --global user.name "Your Name"
git config --global user.email "email@example.com"

//定义全局的用户配置信息，用户名和用户 邮箱

## 局部配置
git config --local user.name "Your Name" 
git config --local user.email "email@example.com"

//--local 在这里可以省略 效果相同

//定义当前仓库所有提交使用的作者姓名和邮箱

# 初始化
git init //将当前目录创建成一个git仓库
git init <dir-name> //指定目录创建成git仓库 例如 git init test-dir



# 添删文件

git add --all //将所有修改添加到暂存区
git add file.txt //将指定文件添加到暂存区

git rm test.txt //删除文件 

git rm --cached test.txt //从版本控制中移除文件 -n可以表示演戏

git checkout -- test.txt //回退到最近提交或添加

git checkout <commit> <file> //将文件回退为指定commit的内容，并添加到暂存区

git checkout <commit> //回退到指定的commit

git commit -m "description"

# 远程仓库

git remote 
git remote -v	//查看推送远程库
git remote add origin https://github.com/xxxxxx/xxxxx //关联一个远程库 origin为远程库名字
git remote rm name
git remote rename name_before name_after

git push -u origin master   //本地分支的更新,推送到远程主机 -u可以设置默认的推送主机 这样下次可以直接使用git push推送至默认的远程主机 master为分支名

git fetch origin <master>   //获取远程更新 fetch之后不会直接修改本地数据 需要合并 即执行git merge origin/master

# 仓库状态

git status 

git diff file.txt

git log  //显示从最近到最远的提交日志

git log -n <number> //显示number个提交日志

git log --oneline //每个提交日志只显示一行

git log --stat //显示详细信息

git ls-files //列出进入版本控制的文件

# 克隆远程仓库
git clone <repo> //将指定的远程仓库克隆到当前目录
git clone <repo> <dir> //将指定的远程仓库克隆到指定目录

# 分支

git branch name //创建名为name的分支

git checkout name //切换到名为name的分支

git merge name //合并指定的名为name的分支到当前分支 git merge origin/master ->远程

git branch -d name //删除分支

git branch -r //查看远程分支

git branch -a //列出所有分支



## git分支模型

git有一个HEAD指针，用于指向当前工作的分支。

例如现在的工作分支为master，那么HEAD就指向master。

git branch 创建分支时实际上是从当前commit状态派生出一个新的状态的节点，但他的分支名改变。



# 回滚

git revert <commit> //恢复成指定的commit分支，注意仍然保留上一次的commit（即生成新的节点）

git reset <commit> //将HEAD指针指向指定的commit，后序的节点将会被删除，工作目录不变

git reset --hard <commit>  //同git reset <commit>，并修改工作目录

git reset  //将暂存区的内容更变为上一次的commit状态，工作目录不变

git reset --hard //同git reset 并修改工作目录

git reset <file> //撤销add的文件

git submodule add https://github.com/xxxxxx/xxxxx //添加一个子模块 之后还需add .gitmodules和子模块的目录 

git submodule init //clone一个有子模块的项目时 第一次需要执行 之后不需要

git submodule update //更新子模块