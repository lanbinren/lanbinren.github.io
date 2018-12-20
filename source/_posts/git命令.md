---
title: git命令
---

**git init** 初始化 Git 库
ssh验证指令生成   SSH 也是唯一一个同时便于读和写操作的网络协议。  生成所在路径/root/.ssh/。
           ssh-keygen \-t rsa \-C "your_email@youremail.com"   
           git clone  git@github.com:lanbinren/test.git    拉取分支
           git clone  git@github.com:lanbinren/test.git   xxx   指定生成路径到xxx


>**git status** 检查当前文件状态 ，会看到 README 文件已被跟踪，并处于暂存状态。

**git diff** 显示还没有暂存起来的改动，而不是这次工作和上次提交之间的差异。
<!-- more -->
**git diff \-\-cached** 查看暂存起来的文件和上次提交时的快照之间的差异。

**git commit  \-v** 选项将修改差异的每一行都包含到注释中来。
   （常用）**-m** 参数后跟提交说明  。
	              **\-a** 选项，Git 就会自动把所有已经跟踪过的文件暂存起来一并提交，从而跳过 git add 步骤。

**git commit \-\-amend**  修改最后一次提交。

**git reset HEAD <file>**取消暂存。 

**git remote**  查看当前配置有哪些远程仓库   
**git remote -v ** 	可以加上 \-v 选项（译注：此为—verbose 的简写，取首字母），显示对应的克隆地址。

**git fetch** 只是将远端的数据拉到本地仓库，并不自动合并到当前工作分支，只有当你确实准备好了，才能手工合并。

**git pull** 是从原始克隆的远端仓库中抓取数据后，合并到工作目录中当前分支。

**git\-push** 可将本地版本更新推送到远端仓库中。

**git commit \-\-amend**  修改最后一次提交   

####查看提交历史

**git log \-\-stat**  列出了修改过的文件，以及其中添加和移除的行数，并在最后列出所有增减行数小计。

**git log \-\-since=2.weeks** 显示两周以前的记录。

>选项 说明
\-(n) 仅显示最近的 n 条提交
\-\-since, \-\-after 仅显示指定时间之后的提交。
\-\-until, \-\-before 仅显示指定时间之前的提交。
\-\-author 仅显示指定作者相关的提交。
\-\-committer 仅显示指定提交者相关的提交。

**git log \-\-pretty=format:"%h \- %an, %ar : %s"**  可以定制要显示的记录格式 。

>$ git log \-\-pretty=format:"%h \- %an, %ar : %s"
ca82a6d \- Scott Chacon, 11 months ago : changed the verison number
085bb3b \- Scott Chacon, 11 months ago : removed unnecessary test code
a11bef0 \- Scott Chacon, 11 months ago : first commit

表 2.1 列出了常用的格式占位符写法及其代表的意义。
|选项 |说明|
| :\-\-: | :\-\-: |
|%H | 提交对象（commit）的完整哈希字串|
|%h  | 提交对象的简短哈希字串|
|%T  | 树对象（tree）的完整哈希字串|
|%t | 树对象的简短哈希字串|
|%P | 父对象（parent）的完整哈希字串|
|%p | 父对象的简短哈希字串|
|%an |作者（author）的名字|
|%ae | 作者的电子邮件地址|
|%ad |作者修订日期（可以用 -date= 选项定制格式）|
|%ar |作者修订日期，按多久以前的方式显示|
|%cn |提交者(committer)的名字|
|%ce |提交者的电子邮件地址|
|%cd |提交日期|
|%cr |提交日期，按多久以前的方式显示|
|%s |提交说明|



####标签

**git tag**   列出当前标签

**git tag \-a v0.0 \-m 'my version 0.0'**  创建一个含附注类型的标签

后期加注标签 
**git log \-\-pretty=oneline**   用一行展示的提交历史
**git tag \-a v1.2 9fceb02**   只要在打标签的时候跟上对应提交对象的校验和（或前几位字符）即可。

默认情况下， git push 并不会把标签传送到远端服务器上   git push origin [tagname].

如果要一次推送所有（本地新增的）标签上去，可以使用 \-\-tags 选项 git push origin \-\-tags。

####Git 命令别名
>$ git config \-\-global alias.unstage 'reset HEAD \-\-'

这样一来，下面的两条命令完全等同：

>$ git unstage fileA
>$ git reset HEAD fileA
**git checkout \-\- benchmarks.rb**  从服务器端重新下载。

使用 git config \-\-global core.editor 命令 设定 编辑器。


仓库创建后
…or create a new repository on the command line

echo "# My-HEXO" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:lanbinren/My-HEXO.git
git push -u origin master



…or push an existing repository from the command line

git remote add origin git@github.com:lanbinren/My-HEXO.git


git pull origin master --allow-unrelated-histories

后面加上 --allow-unrelated-histories ， 把两段不相干的 分支进行强行合并



