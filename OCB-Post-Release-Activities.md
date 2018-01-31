
### Tagging Repository after RELEASE 

- Checkout the branch from which release has been made.
```
c:\Projects\github-sap\OmniChannelBanking\deploytool> git checkout OCB83SP04
Switched to a new branch 'OCB83SP04'
Branch 'OCB83SP04' set up to track remote branch 'OCB83SP04' from 'origin'.

c:\Projects\github-sap\OmniChannelBanking\deploytool> git branch
* OCB83SP04
  master
```


- Check if history is fine and your are applying tag on right revision
```
c:\Projects\github-sap\OmniChannelBanking\deploytool> git log -n1
commit c494c33bc174c7ef57f7c9950960d5a4b9ec5348 (HEAD -> OCB83SP04, origin/OCB83SP04)
Author: sambule <sandeep.ambule@sap.com>
Date:   Tue Jan 30 14:48:05 2018 +0530

    deploy.sh  unix format
```


- Create a tag with with message
```
c:\Projects\github-sap\OmniChannelBanking\deploytool> git tag -a v8.3.4.PL02-RELEASE -m "OCB 8.3 SP04 PL02 Release"

c:\Projects\github-sap\OmniChannelBanking\deploytool> git tag
v8.3.4.PL02-RELEASE
```


- Push the tag to the remote repository
```
c:\Projects\github-sap\OmniChannelBanking\deploytool> git push origin v8.3.4.PL02-RELEASE
Counting objects: 1, done.
Writing objects: 100% (1/1), 188 bytes | 94.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0)
To https://github.wdf.sap.corp/OmniChannelBanking/deploytool.git
 * [new tag]         v8.3.4.PL02-RELEASE -> v8.3.4.PL02-RELEASE
```