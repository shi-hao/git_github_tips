# Duplicating a github repo with history    
  
It's so easy to duplicate a github repository including every commits and branches.  
  
1) Create a new repo in github using UI/command as usual. This will be the target repo where duplicate of source repo to be pasted.  
  
2) Open a command prompt and Clone the source/existing repo using the command:  
   git clone --bare https://sourceRepoURL  
  
A new folder will be created containing some files from source repo.  
  
3) Move to that folder:  
cd sourceRepoFolder  
  
4) Push these files into the target repo using command:  
git push --mirror https://targetRepoURL  
  
That's it. Thank you.  
  
# Duplicating a github repo with history to self-established git server  
1) Open a command prompt and Clone the source/existing repo using the command:  
   git clone --bare https://sourceRepoURL  
   then you will get a dir, with name repo-name.git  
  
2) copy the repo-name.git dir to self-established git server   
  
3) git clone username@ip:dir + repo-name.git  
  

**COMPLAINT**
Move all the github repo to self-established git server!  
Github can be reached by nothing, even VPN!  
Github bring users very bad using experience in china, 
Web pages cannot be opened, pull/push very slow, often failed!   
Github has been dead in china.  
