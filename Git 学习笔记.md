# Git 学习笔记

![图片描述](https://img.mukewang.com/59c31e4400013bc911720340.png)

Workspace：工作区
Index / Stage：暂存区
Repository：仓库区（或本地仓库）
Remote：远程仓库

## Git Bash:

##### 配置用户名邮箱：

git config --global user.name "yourname"

git config -- global user.email "youremail"

#### 本地仓库：

##### 创建版本库：

**cd** 进入； **mkdir** 新建；**pwd** 显示当前目录；  **git init** 把该目录变成可以管理的仓库

##### 添加修改文件：

**git add** readme.txt 把文件添加到暂存区

**git commit -m "提交文件"** 把文件提交到仓库，并且显示注释

**git status** 查看文件状态（是否提交，工作区状态）

**git diff** readme.txt 查看文件的修改内容

修改后的文件重复add 和 commit步骤

##### 版本退回：

**git log**  查看历史记录 最上面为最新修改记录 （**git log --pretty=oneline** 每条记录为一行显示）

**git reset --hard HEAD^** 回退到上一版本

**git reset --hard HEAD^^** 回退到上上一版本

**git reset --hard HEAD~100**  回退到前100个版本

**cat readme.txt** 查看文件内容

回退到最新版本：**git reset --hard 版本号**  版本号获取方式：**git reflog**

##### 撤销修改&删除文件：

**撤销修改：** 

1. 手动更改文件—add—commit
2. git reset -- hard HEAD^ 恢复到上一版本
3. git status 查看当前状态 ——**git checkout -- readme.txt** 丢弃工作区的修改

**删除文件**： 

**rm** readme.txt 删除 ——没有commit之前 git checkout -- readme.txt 恢复文件

#### 远程仓库：

**添加SSH Key**: id_rsa.pub公钥

**添加新仓库：**

git remote add origin https: //github.com/name/repo.git 连接远程仓库

git push -u origin master 推上本地文件

（如果地址输入错误，并且显示fatal: remote origin already exists.，则输入 **git remote rm origin**,然后重新输入）

**远程库克隆至本地： **

**git clone** https://……地址

##### 创建与合并分支：

**git checkout -b** dev 创建并切换分支 （注意：checkout如果后面是 **--** ,则是撤销，加上**-b**参数表示创建并切换==  git branch dev  + git checkout dev）

**git branch** 查看分支

**git branch**  dev 创建分支

**git checkout** master 切换分支

**git merge** dev 在（上一部转换）master 合并dev

**git branch -d** dev 删除dev分支

最后同步至远程库：

**git remote** 查看远程库信息

**git remote -v** 详细信息

**git push origin** master 同步





