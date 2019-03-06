1.查看分支  
git  branch  
  
2.创建分支  
git branch branch_name  
  
3.切换到某个分支  
git  checkout  branch_name  
  
4.以某个tag代码为基础创建一个分支  
git branch branch_name tag_name  
  
  
应用实例1：  
有一个源码工程，想在其某一个中间版本上进行修改，此时如何做呢？  
  
(1)查看工程版本信息  
git log  
或者  
git tag  
  
(2)以目标版本为基础，新建一个分支  
  
git branch my-branch  hash_value  
或者  
git branch my-branch  tag_name  
  
(3)切换到新分支，进行代码修改  
git checkout my-branch  
切换到新分支后，可以查看下log信息，看下是否处在之前的版本上。  
  
git log  
