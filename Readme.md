# Service Virtualization in IBM Rational Test Automation Server

## Create a RIT project in a GIT folder
- Create a normal RIT project
- Add git credentials in RIT preferences
- Shutdown RIT
- Go to GitHub and create a repository for the RIT project
- Add the RIT project to GIT
- Restart RIT, and verify that the RIT project is now connected to the GIT repository

The only way I found to push the RIT project to GIT is to use the git bash command line client
```
$ cd <RIT Folder>
$ git init
$ git add .
$ git config --global user.name VialeMuriel
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
- Create the stub in RIT.
- Test it and push the project in Git.

## Configure HTTP proxy to run stub in RTAS

- Modify the server base url in the http roxy registration.xml
```
<server base-url="<Rational® Test Automation Server_URL>" security-token="<Offline_User_Token>" />
```
- Point to the IBM RTAS instance where we generate the offline user TOKEN
```
<server base-url="https://rtas-cb2fa44b08d68f0ed76d7db379272825-0000.tor01.containers.appdomain.cloud" security-token="eyJhbGciOiJIUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJlMjI5ZDE1YS1mOWZhLTQxZWEtOTQzNS0yZTAwMTQ5ZDJmODYifQ.eyJpYXQiOjE2MTE4NDQ2OTksImp0aSI6ImU3OTRlZWZkLWMwM2ItNDM3OS1iMDY1LTIyNmM4MmQ0N2NkNiIsImlzcyI6Imh0dHBzOi8vcnRhcy1jYjJmYTQ0YjA4ZDY4ZjBlZDc2ZDdkYjM3OTI3MjgyNS0wMDAwLnRvcjAxLmNvbnRhaW5lcnMuYXBwZG9tYWluLmNsb3VkL2F1dGgvcmVhbG1zL3Rlc3RzZXJ2ZXIiLCJhdWQiOiJodHRwczovL3J0YXMtY2IyZmE0NGIwOGQ2OGYwZWQ3NmQ3ZGIzNzkyNzI4MjUtMDAwMC50b3IwMS5jb250YWluZXJzLmFwcGRvbWFpbi5jbG91ZC9hdXRoL3JlYWxtcy90ZXN0c2VydmVyIiwic3ViIjoiZDZlNTdhMGItMTc3Yi00ZWQ1LWE3MDItM2M5MDdlZjIxZjA1IiwidHlwIjoiT2ZmbGluZSIsImF6cCI6InRlc3RzZXJ2ZXIiLCJzZXNzaW9uX3N0YXRlIjoiMzY4Y2MxMWQtZGRlMS00NmJjLWIzMmItMDVjZDQ3Y2U2MjA5Iiwic2NvcGUiOiJ0ZXN0c2VydmVyIGVtYWlsIG9mZmxpbmVfYWNjZXNzIHByb2ZpbGUifQ.BUPTDE8zAsk3Yi13PQyGq91gZ-PEobGJbeYG-FF_lbU" >
```
- Log on the RTAS server and look at the proxy to verify his insertion
- Create a RTAS Project and add the GIT repository
- Virtual service is there ready to run.
