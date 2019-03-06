# part1 账户设置和配置  
github主页:https://github.com  
  
使用邮箱注册github帐号。  
  
  
## access github repo using ssh  
  
  
  
  
# part2 upload code to github  
  
登录github帐号，创建一个空的repo，不要添加readMe，ignore，license等内容，  
然后github会提示你如何进行下一步操作，提示内容如下：  
<pre>
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
</pre>
  
提示1：通过命令行创建一个新的仓库  
本地没有使用git管理的代码文件，准备在本地创建一个新的版本仓库，并上传到github  
  
提示2：上传已经在本地使用git管理的仓库  
本地已经有一个仓库了，将其上传到github  
  
提示3：引入其他仓库的的代码  
 
# part3 clone repo from the github
## (1)git clone  
总共有有两种方式，git clone using https or ssh。  
打开要克隆的项目主页，点击项目主页右侧的clone or download按钮，选择clone with https或者clone with ssh。  
复制对应的地址，将项目的master分支克隆到本地，使用ssh，需要先配置了ssh密钥才可以。  
<pre>
	git clone https://github.com/openssl/openssl.git
	git clone git@github.com:openssl/openssl.git
</pre>

## (2)git branch  
将项目克隆到本地后，使用git branch可以查看当前分析。
<pre>
	git branch 
	git branch  -a
</pre>
git branch用于查看本地的所有分支，git branch -a可以查看远程项目的其他所有的分支。

## (3)git checkout 
下载其他的分支到本地。  
<pre>
	git checkout -b local_name  remote_branch_name
</pre>
local_name是创建的本地分子的名字，remote_branch_name是使用git branch -a查看到的远程分支  
的名字，将远程分支remote_branch_name克隆到本地，命名为local_name，并切换到该分支。

