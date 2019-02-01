#part1 账户设置和配置
github主页:https://github.com

使用邮箱注册github帐号。


##access github repo using ssh




#part2 upload code to github

(1)登录github帐号，创建一个空的repo，不要添加readMe，ignore，license等内容，
然后github会提示你如何进行下一步操作，提示内容如下：

…or create a new repository on the command line

echo "# git_github" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:shi-hao/git_github.git
git push -u origin master

…or push an existing repository from the command line

git remote add origin git@github.com:shi-hao/git_github.git
git push -u origin master

…or import code from another repository

You can initialize this repository with code from a Subversion, Mercurial, or TFS project.

提示1：通过命令行创建一个新的仓库
本地没有使用git管理的代码文件，准备在本地创建一个新的版本仓库，并上传到github


提示2：上传已经在本地使用git管理的仓库
本地已经有一个仓库了，将其上传到github


提示3：引入其他仓库的的代码

