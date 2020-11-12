# git 技巧

## git添加/删除/推送 到多个仓库

```
# 更改新的仓库地址
git remote set-url origin git@github.com:haobird/book.git
# 新增仓库地址, 并且知道标志为 pages
git remote add pages git@github.com:haobird/book.git
# 删除指定标志的仓库地址
git remote remove pages 
# (如上)删除指定标志的仓库地址
git remote rm origin
# 推送到远程库
git push -u origin master
# (如上)推送到指定远程库的指定版本
git push pages master
# 查看本地的远程库
git remote -v

```

## git分支操作

```
# 查看远程分支
git branch -a
# 同步远程服务器上的数据到本地
git fetch origin  （如果看不到远程分支，也可以运行此命令来同步）
# 拉取远程分支
git checkout -b 本地分支名 origin/远程分支名
# (同上)简化版本
git checkout --track origin/guang2.0
# 强制更新推送到远程
git push origin master --force
# 推送到远程不存在的分支（两个步骤）
git push --set-upstream origin mix1.0
git push origin mix1.0

```

## 提取文件操作



## git常见问题

#### 拒绝合并无关历史

>  fatal: refusing to merge unrelated histories

```
git pull origin master --allow-unrelated-histories 
```

#### 第一次添加远程库，拉取分支出现错误提示

> There is no tracking information for the current branch.Please specify which branch you want to merge with.的方法：

```
git branch --set-upstream master origin/master
```

#### 未合并文件冲突

> Pull is not possible because you have unmerged files.

```
1.pull会使用git merge导致冲突，需要将冲突的文件resolve掉 git add -u, git commit之后才能成功pull.

2.如果想放弃本地的文件修改，可以使用git reset --hard FETCH_HEAD，FETCH_HEAD表示上一次成功git pull之后形成的commit点。然后git pull.
```

#### 当前不是分支

> You are not currently on a branch.

```
首先git checkout -b temp
其次git checkout master
```



## git 上线流程

```
1、git checkout -b deploy-jie 创建一个新的开发分支
2、git branch 显示是否创建成功分支
3、git check out deploy-jbl 切换到当前分支，进行开发
4、git commit -m ‘提交开发’ 提交更改
5、git checkout master 切换到master分支
6、git merge deploy-jbl 合并开发分支到master
7、git pull 拉取最新提交
8、git push 推送提交到版本库
9、修改分支到一半的时候，需要切换分支，此时可以不提交修改。直接git stash 储藏起来
10、等修改另外的分支完成，重新切换回来的时候，再使用git stash apply重新获取刚才的变更
11、如果merge 错分支了，或者不想合并了，此时尚未push ，可以先看下日志 git reflog ，则git reset --hard HEAD^
12、如果已经commit 了，此时想回退回来，且保留修改的代码，查看日志 git log ，则git reset --soft HEAD^
13、合并失败，终止合并git merge --abort
14、删除分支 git branch -d hotfix
15、推送到远程库新分支 git push origin deploy-iss-InviteActionSms
16、如果需要合并两个分支的一部分文件，使用这个命令可以强行合并 git checkout [branch] -- [file name]  如：git checkout B message.html message.css message.js other.js
17、删除远程分支git push origin --delete deploy-iss-InviteActionSms
18、推送到远程分支别名git push origin deploy-iss-PasswordShare:deploy-iss-jie
19、更好的查看log日志 git log --pretty=oneline
20、直接还原到某个分支 git reset --hard 1094a
21、强制推送到远程代码 git push origin HEAD --force
22、当PUSH错误后，可以使用 git revert <commit_id>操作实现以退为进，此时就不需要强制push了。
23、从暂存区删除某个文件 git rm --cached one.txt 文件不会删除，只会处于没有版本管理的状态
24、使用 "git checkout -- <文件>..." 丢弃工作区的改动。如： git checkout -- file
25、用命令git reset HEAD file可以把暂存区的修改撤销掉（unstage），重新放回工作区：git reset HEAD readme.txt
26、git reset命令既可以回退版本，也可以把暂存区的修改回退到工作区。当我们用HEAD时，表示最新的版本。(HEAD^表示上一个版本,就是git log的第二次)
27、把当前分支的某个文件替换为其他分支的文件： git checkout <branch name> -- path
```