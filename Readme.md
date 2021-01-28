# Service Virtualization in IBM Rational Test Automation Server

## Create a RIT project in a GIT folder
- Create a normal RIT project
- Add git credentials in RIT preferences
- Shutdown RIT
- Add the project content in GIT
- Restart RIT

The only way I found to push the RIT project to GIT is to use the git bash command line client
```
$ cd <RIT Folder>
$ git init
$ git add .
$ git commit -m "Initial RIT Project"
Your branch is up to date with 'origin/master'.
$ git remote add origin https://github.com/VialeMuriel/RITSimpleGIT.git
AzureAD+MURIELViale@LAPTOP-8FUG2OFG MINGW64 ~/github/RITSimpleGIT (master)
$ git push -u origin master
Enumerating objects: 16, done.
Counting objects: 100% (16/16), done.
Delta compression using up to 8 threads
Compressing objects: 100% (14/14), done.
Writing objects: 100% (16/16), 2.95 KiB | 755.00 KiB/s, done.
Total 16 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), done.
remote:
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/VialeMuriel/RITSimpleGIT/pull/new/master
remote:
To https://github.com/VialeMuriel/RITSimpleGIT.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```
