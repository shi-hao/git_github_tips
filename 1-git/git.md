#part1  git pratical skills    
  
1.设置git    
设置用户名：   git   config  --global  user.name	bleach    
设置邮箱：     git   config  --global  user.email   xxx@163.com    
设置显示颜色： git   config  --global  color.ui     auto      

提交代码时，git log中显示对应的用户名和邮箱，如下。

commit a6daf20f6c8e111bfb91a2d68ad278a3883de8f7
Author: bleach <shi7631470@163.com>
Date:   Tue Nov 21 09:00:42 2023 +0800

    edit

查看全局变量： git   config  --global  --list  
			   git   config  -l
  
2.三种状态  
版本管理下的文件有三个状态：  
（1）文件被修改了，还未被暂存。  
（2）文件被修改了，已经被添加到暂存(git add)  
（3）文件被修改了，已经提交到版本库(git commit)  
  
原始文件-->暂存-->版本库  
  
3.创建并添加文件到版本库三步走  
初始化工作目录：git   init  
将文件添加到暂存：    git   add  <filename>     
将文件添加到版本库：git commit  -m  "版本说明"  
  
4.添加（add）到暂存  
添加某个文件的修改到暂存：git  add  <filename>  
添加所有文件的修改到暂存：git  add  .   或者 git  add  
  
5.提交（commit）修改到版本库  
提交本次所有的修改到版本库：git  commit  –m  “log 信息”  
  
6.添加暂存和提交版本库合并操作（add+commit）  
添加暂存和提交版本库指令可以合并：git  commit   -a  -m  “log信息”  
不过，注意，此指令表示将所有已经添加到版本管理的所有文件的修改添加暂存并提交修改到版本库，如果某个文件没有添加到版本管理，也就是说从未对其执行过git  add，那么该文件的修改是不会提交的。  
  
7.查看改动  
7.1查看当前改动（git  status）  
版本库中当前文件发生了修改，文件可能处于三种状态之一，可以使用git  status指令来查看改动。  
git  status  
  
7.2查看改动（git  diff）  
显示当前工作目录树中未被暂存的改动：git  diff  
显示暂存区和最新版本库的区别：git  diff   --cached  
显示当前目录下暂存的和未被暂存的跟最新版本库的区别：git  diff  HEAD  
显示两次提交的差别：git  diff  <SHA1前八位>  <SHA1前八位>  
  
8.查看log  
版本库在不断修改，每次提交都会产生提交信息，使用git  log可以查看提交信息。  
8.1查看简单提交信息  
git  log  
不使用任何的参数，查看每次commit的提交信息，包括一行哈希值，一行提交作者，还有一行时间。  
  
8.2查看详细提交信息  
git  log  –p  
使用一个参数-p，可以查看每次提交的详细信息，哈希值，作者，时间，以及所有文件改动的详细信息（增，删，改等详细信息）。  
可以使用管道将信息输出到文本查看工具，便于查看，比如，  
git  log  –p  |  less  
将信息输出到less，方便查看。  
  
8.3查看某个文件详细改动  
git  log  –p  <filename>  
可以使用上述指令查看某个文件在所有提交过程中，每次的改动。  
git  log  -n  –p  <filename>  
-n表示次数，上述指令表示查看最新n次提交过程中，文件每次的改动。  
  
8.4一行查看log信息  
git  log  --oneline  
使用--oneline参数可以简化查看的信息，只会显示哈希值的前八位和提交的log信息。  
   
  
9.版本回滚  
9.1 版本之间切换--git checkout  
git checkout用于在各个版本之间切换，牢记，使用git checkout查看以往版本，不能在历史版本上进行修改，在历史版本  
上修改的内容无法提交到版本库，而且在checkout到其他版本后，修改内容不会被保存。  
  
git checkout <version-hash-tags>  切换到当前分支的某一版本  
git checkout <branch-name>        切换到某一分支或者用于切换到当前分支的最新版本  
  
  
（1）使用git  log查看所有的版本信息的哈希值。  
（2）使用git  checkout  <前八位哈希值>，然后回滚到之前的版本。  
（3）在回滚的版本下进行编辑修改，编译等。  
（4）返回之前最新的版本，首先复原文件的修改，git  checkout  .  
（5）返回最新的版本，git  checkout  master  
  
9.2 删除某个或者某些版本  
  
  
  
#part2 understanding and using branch  
  
git branch    查看所有的分支  
git branch    <name>    <基于的版本hash/tags>  创建新的分支，基于的版本可以省略，省略的话表示基于当前分支的当  
                                               前版本进行新的分支创建。  
git checkout  <branch-name>  切换到某个分支  
  
首先要理解分支，举例子说明，有一款软件不断开发，不断演进，有很多版本，如下。  
program：  
ver1 --> ver2 --> ver3 --> ver4  
  
有一天，有一位程序员A想在该软件的某一个版本上做一定的开发，开发自己的特性功能，这是如何做呢，比如  
就在版本ver2基础上，这时候，branch就是解决这个问题的。  
首先使用git branch来创建分支 git  branch  <new branch name>    <基于的版本hash/tags>  
git   new    ver2  
  
program：  
master barnch:ver1 --> ver2 --> ver3 --> ver4  
new    branch:ver1 --> ver2   
在新的分支new上，程序员A可以进行新的开发，并提交，产生新的版本.  
  
program：  
master barnch:ver1 --> ver2 --> ver3 --> ver4  
new    branch:ver1 --> ver2 --> new-ver1 --> new-ver2   
