# setting up git server  
  
需求：在一台服务器或者PC上建立git server服务，供小范围内开发人员使用，  
具备如下基本功能：  
(1)所有人可以从服务器git clone工程。  
(2)所有人可以从服务器git pull更新。  
(3)所有人可以向服务器git push本地更新。  
  
环境：2台ubuntu16 PC，一台服务端，一台客户端  
  
## 1. 安装git  
使用如下指令安装git，以ubuntu16为例进行安装。  
<pre>  
sudo apt update  
sudo apt-get install git  
</pre>  
  
## 2.服务器端创建用并配置SSH  
在服务器端创建一个用户，并为该用户创建.ssh目录。  
<pre>  
sudo adduser git  
su git  
cd  
mkdir .ssh && chmod 700 .ssh  
touch .ssh/authorized_keys && chmod 600 .ssh/authorized_keys  
</pre>  
  
## 3.服务器创建空仓库  
使用如下指令在服务器上创建一个空的仓库。  
<pre>  
cd /home/git  
mkdir  mypic.git  
cd mypic.git  
git init --bare  
Initialized empty Git repository in /home/git/mypic.git/  
</pre>  
  
## 4.客户端创建ssh登录密钥对  
在客户端pc上创建ssh密钥对。  
<pre>  
ssh-keygen  
</pre>  
默认会在当前用户的.ssh目录下生成id_rsa私钥和id_rsa.pub公钥，  
将生成的公钥复制到服务端的.ssh/authorized_keys文件中。  
<pre>  
cat id_rsa.pub >> /home/git/.ssh/authorized_keys  
</pre>  
  
## 5.客户端git clone项目，修改并git push更新  
首先保证客户端可以正常访问到服务器，网络正常。  
然后使用如下指令克隆创建的项目。  
<pre>  
git clone username@<ip>:<dir+pro_name>  
git clone git@192.168.0.129:~/mypic.git  
</pre>  
进行必要的修改，并提交到仓库。  
<pre>  
git add *  
git commit -m "log"  
git push origin master  
</pre>  
