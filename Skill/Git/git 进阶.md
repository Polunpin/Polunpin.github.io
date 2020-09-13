

# GIT 进阶学习

## Git 速查表

![Git 速查表](git 进阶.assets/11455432-669c33b411d979df.jpg)



## 1.1 常见命令

- `git init` : 初始化 git 仓库，即将一个文件夹初始化为一个 git 仓库。具体的操作是创建一个 `.git` 隐藏文件夹
- `git status` : 查看仓库的状态
- `git add <file>` : 将文件提交到暂存区
- `git commit -m <代码提交信息>` : 将暂存区的文件提交到仓库中，并附带说明信息
- `git log` : 查看所有产生的 commit 记录
- `git config -l` : 查看自己的配置，默认配置都在`.git/config` 文件中

## 1.2 分支相关的命令

- `git branch <branch_name>` : 如果不加上 `<branch_name>`，查看当前分支情况。如果加上，就是创建一个分支。
- `git checkout <branch_name>` : 切换到`<branch_name>`的分支上
- `git checkout -b <branch_name>` : 创建一个分支并切换到这个分支上，效果相当于合并上面 2 个命令。
- `git merge <branch_name>` : 将 `<branch_name>` 分支合并到当前所在的分支上
- `git branch -d <branch_name>` : 将 `<branch_name>` 分支删除
- `git branch -D <branch_name>` : 将 `<branch_name>` 分支强制删除。如果 `<branch_name>` 分支存在未合并的代码时，那么用 `-d` 是删除不了。

## 1.3 标签相关的命令

- `git tag` : 查看历史 tag 记录。
- `git tag <tag_name> <commit_id>` : 在指定提交 id 上创建一个 tag。如果不写 `<commit_id>` ，那就在最新的 commit 上创建一个 tag。
- `git checkout <tag_name>` : 切换到 `<tag_name>` 标签
- `git show <tag_name>` : 查看标签信息
- `git tad -d <tag_name>` : 删除标签
- `git push origin <tag_name>` : 将某个标签推送到远程仓库
- `git push origin :refs/tags/<tag_name>` : 可以删除一个远程标签。

## 1.4 SSH

提前申明， windows 系统并不自带 SSH， 但是安装的 Git 中带有 SSH。所以以下命令请在 Git bash 下执行。

- `ssh-keygen -t rsa` : 指定 rsa 算法生成密钥。
- `ssh -T git@github.com` : 测试 ssh 是否成功添加到 github 中

## 1.5 Github 操作

- `git clone ...` : 将 github 项目复制到本地的当前目录
- `git push origin <本地分支>:<远程分支>` : 把本地分支中本地代码同步到远程分支
- `git pull origin <branch_name>` : 把远程 <branch_name> 分支的最新的代码同步到本地当前分支中
- `get remote add origin git@github.com:xxx/xxxx.git` : 将当前本地仓库与远程进行联接
- `git remote -v` : 查看我们当前项目有哪些远程仓库

## 1.6 补充命令

- **alias** 别名
  - `git config --global alias.<别名> "<原命令>"`。比如 `git config --global alias.c "checkout"`，之后 `git c` == `git checkout`
- **diff**
  - `git diff` : 比较工作区文件和暂存区文件差异。如果加上文件名，就仅比较这个文件在工作区与暂存区的区别
  - `git diff <commit_id1> <commit_id2>` : 比较两次提交之间的差异
- **checkout**
  - 作用 1 ：切换分支、标签以及 commit。本质是「用某个 HEAD 中的最新内容替换掉你的工作区中的文件」。切换时，暂存区的内容不受影响但相当于在切换前执行了 `git stash`
  - 作用 2 ：撤销还没进入暂存区的修改的作用。举个例子，假设我们在一个分支开发一个小功能，刚写完一半，这时候需求变了，而且是大变化，之前写的代码完全用不了了，好在你刚写，甚至都没有 git add 进暂存区，这个时候很简单的一个操作就直接把原文件还原：`git checkout a.md`，本质上是将 HEAD 内容覆盖掉工作区的内容。注意，checkout 命令只能撤销还没有 add 进暂存区的文件。
- **stash**
  - 作用：把当前分支中的工作区的所有修改先暂存到栈上。
  - 运用场景：假设我们正在一个新的分支做新的功能，这个时候突然有一个紧急的bug需要修复，而且修复完之后需要立即发布。当然你说我先把刚写的一点代码进行提交不就行了么？这样理论上当然是ok的，但是这会产品垃圾commit，原则上我们每次的commit都要有实际的意义，你的代码只是刚写了一半，还没有什么实际的意义是不建议就这样commit的，那么就用 `git stash` 保留。
  - `git stash` : 把当前分支所有没有 commit 的代码先暂存起来
  - `git stash list` : 查看所有 stash 记录
  - `git stash apply` : 将暂存的代码还原
  - `git stash drop` : 把最近一条 stash 记录删除。*注意：每次还原代码后，最好删除这条 stash 记录*
  - `git stash pop` == `git stash apply` + `git stash drop`
  - 注意：执行了 `git add` 的数据在切换分支时，会自动暂存一起。本质上是因为切换分支不影响暂存区的数据。但需要手动恢复。