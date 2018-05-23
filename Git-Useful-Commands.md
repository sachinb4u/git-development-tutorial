### How to see log with limited entries and only changed files
> git log --name-status -n2

Only show 2 entries with list of files and status of change
```git
$ git log --name-status -n2

commit 335025631155bdc6daf2f85106ec2a2bf3bd9729 (HEAD -> gm_new)
Author: Aniket Sagar <aniket.sagar@sap.com>
Date:   Fri May 11 14:10:57 2018 +0530

    Updated EDM

M       com.sap.banking.messagesconfig/src/main/resources/com/sap/banking/messagesconfig/config/edm/MessagesEdm.xml

commit a7f9ffe78a3512dc3b6a4a60634f075a3f56b9ec
Author: Aniket Sagar <aniket.sagar@sap.com>
Date:   Wed May 9 12:21:46 2018 +0530

    Updated the value for Interstitial Msg type to properly map with GlobalMessageConsts

M       com.sap.banking.common-api/src/main/java/com/ffusion/beans/messages/GlobalMessageConsts.java
M       com.sap.banking.messages-api/src/main/java/com/sap/banking/messages/endpoint/constants/BankMessagesType.java


```

### How to see only commits you made and not in master or the branch you want to create pull request
> git log (branch1) --not (branch2)
>
> git log gm_new --not upstream/OCBDEV
>
Here we see log for `gm_new` to list all commits which are in `gm_new` branch but not present `upstream/OCBDEV`
```
$ git log gm_new --not upstream/OCBDEV

commit 335025631155bdc6daf2f85106ec2a2bf3bd9729 (HEAD -> gm_new)
Author: Aniket Sagar <aniket.sagar@sap.com>
Date:   Fri May 11 14:10:57 2018 +0530

    Updated EDM

commit a7f9ffe78a3512dc3b6a4a60634f075a3f56b9ec
Author: Aniket Sagar <aniket.sagar@sap.com>
Date:   Wed May 9 12:21:46 2018 +0530

    Updated the value for Interstitial Msg type to properly map with GlobalMessageConsts

commit 3a7b9350b5627607e79558814399e9214389a47c
Author: Aniket Sagar <aniket.sagar@sap.com>
Date:   Wed May 9 12:04:49 2018 +0530

    New messageadmin service created

commit 614a0e78988193f08ab959fcb87801fe6b400b21
Author: Aniket Sagar <aniket.sagar@sap.com>
Date:   Fri May 4 15:14:21 2018 +0530

    Updated EDM for FilterDesc

commit 77cc7615f7dca2f61b348acb31e6e83e4339d3af
Author: Aniket Sagar <aniket.sagar@sap.com>
Date:   Mon Apr 30 21:41:03 2018 +0530

    Global Message Recipients Added

commit 7de7423ab65f09a5e2e2d40d60d43e21941ec405
Author: Aniket Sagar <aniket.sagar@sap.com>
Date:   Mon Apr 30 15:14:50 2018 +0530

    Updated MessagesAdminMapper to remove unwanted comments

commit 5f742d495c2b691e82cac853fc5bfa0f95dbac49
Author: Aniket Sagar <aniket.sagar@sap.com>
Date:   Mon Apr 30 13:48:33 2018 +0530

    ODATA Implementation For Global Messages

```

### How to see changes done in commit with list of changed files
> git show --name-status a7f9ffe78a
>
> git show --name-status (commit-id)

This will show the commit with message and changed file with A (Added), M (Modified) or D (Deleted) status
```
$ git show --name-status a7f9ffe78a

commit a7f9ffe78a3512dc3b6a4a60634f075a3f56b9ec
Author: Aniket Sagar <aniket.sagar@sap.com>
Date:   Wed May 9 12:21:46 2018 +0530

    Updated the value for Interstitial Msg type to properly map with GlobalMessageConsts

M       com.sap.banking.common-api/src/main/java/com/ffusion/beans/messages/GlobalMessageConsts.java
M       com.sap.banking.messages-api/src/main/java/com/sap/banking/messages/endpoint/constants/BankMessagesType.java
```

### How to see the changes done in the commit using WinMerge to verify difference in modified files
> git difftool a7f9ffe78a~1 a7f9ffe78a
>
> git difftool (commit-id)~1 (commit-id)

This will open WinMerge or any difftool as per your configuration. It will open each modified file.



### How to know which is the base for the branch created. i.e. from which commit this branch has been created
> git show --name-status $(git merge-base test1 upstream/OCBDEV)
>
> git show --name-status $(git merge-base branch base-branch)
>
This is combined command. `git merge-base branch base-branch` give you the commit it which gets passed to `git show --name-status <id>` to show the details
```
$ git show --name-status $(git merge-base test1 upstream/OCBDEV)

commit 046b2a056e3644a2f4f833bf26e905207bfb3f93
Author: Sandeep Ambule <sandeep.ambule@sap.com>
Date:   Fri Feb 9 12:20:10 2018 +0530

    build_war.bat fix (#72)

    * Moved com.sap.banking.frontend-web project to mavenservices

    * GitHub Migration of mavenservices-build script fix

    * build_war.bat fix

M       build_war.bat

```
