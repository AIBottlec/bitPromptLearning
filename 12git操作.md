#### git基本操作 
1. 协作开发基本流程
    git init
    git clone [url]
    git checkout -b [mybranch] 新建一个分支，并切换到该分支
    echo "some info ..." > <your-file>
    git add <your-file>
    git commit -a
    git push origin <your-branch>
2. 分支合并
    - git checkout master     切换到master主分支
    - git pull [origin master]  从master分支拉取代码
    - git checkout ghm 切换到自己的分支
    - git merge master 将主分支的新内容添加到自己的分支，新内容在自己分支的本地，服务器没有新内容
    - git push origin ghm     将合并后的内容提交到服务器上自己分支
3. 异常处理
    - pull过程中发生冲突，解决冲突后，commit，pull,push
    - 在分支merge过程中[$git merge master]，如果发生冲突：修改冲突->commit->push origin [branch]->merge查看冲突解决完整性。
    - 发生冲突时，可使用命令 $git checkout -f恢复场景，把冲突文件拷贝备份后merge，比较两文件的差异可使用meld工具。

<hr>
#####新建代码库
- 新建一个目录，将其初始化为Git代码库
    git init [project-name]
- 下载一个项目和它的整个代码历史
    git clone [url] 

##### 配置
- 显示当前的Git配置
    git config --list
- 编辑Git配置文件
    git config -e [--global]
- 设置提交代码时的用户信息
    git config [--global] user.name "[name]"
    git config [--global] user.email "[email address]"

##### 增加/删除文件
- 添加指定文件到暂存区
    git add [file1] [file2] ...
- 添加指定目录到暂存区，包括子目录
    git add [dir]
- 添加当前目录的所有文件到暂存区
    git add .
- 添加每个变化前，都会要求确认
    对于同一个文件的多处变化，可以实现分次提交
    git add -p
- 删除工作区文件，并且将这次删除放入暂存区
    git rm [file1] [file2] ...

##### 代码提交
- 提交暂存区到仓库区
    git commit -m [message]
- 提交暂存区的指定文件到仓库区
    git commit [file1] [file2] ... -m [message]
- 提交工作区自上次commit之后的变化，直接到仓库区
    git commit -a
- 提交时显示所有diff信息
    git commit -v
- 使用一次新的commit，替代上一次提交
    如果代码没有任何新变化，则用来改写上一次commit的提交信息
    git commit --amend -m [message]
- 重做上一次commit，并包括指定文件的新变化
    git commit --amend [file1] [file2] ...

##### 分支
- 列出所有本地分支
    git branch
- 列出所有远程分支
    git branch -r
- 列出所有本地分支和远程分支
    git branch -a
- 新建一个分支，但依然停留在当前分支
    git branch [branch-name]
- 新建一个分支，并切换到该分支
    git checkout -b [branch]
- 新建一个分支，指向指定commit
    git branch [branch] [commit]
- 新建一个分支，与指定的远程分支建立追踪关系
    git branch --track [branch] [remote-branch]
- 切换到指定分支，并更新工作区
    git checkout [branch-name]
- 切换到上一个分支
    git checkout -
- 建立追踪关系，在现有分支与指定的远程分支之间
    git branch --set-upstream [branch] [remote-branch]
- 合并指定分支到当前分支
    git merge [branch]
- 选择一个commit，合并进当前分支
    git cherry-pick [commit]
- 删除分支
    git branch -d [branch-name]
- 删除远程分支
    git push origin --delete [branch-name]
    git branch -dr [remote/branch]

> http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html
