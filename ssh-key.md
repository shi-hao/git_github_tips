# github ssh key

## setting the ssh key
1)creating the ssh key
2)add the ssh key to github

## clone the repo with ssh instead of https

Q: local repo clone with https, then add rsa ssh key to 
   github, but when push/pull repo, the user name and password 
   are still needed?

A: enter the local repo root dir, and open the ./git/config file,
   then edit the url, the older one is like: 
   url = https://github.com/shi-hao/python_study.git
   then edit to like this:
   url = git@github.com:shi-hao/python_study.git
