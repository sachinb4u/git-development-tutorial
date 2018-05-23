### How to see log with limited entries and only changed files
> git log --name-status -n2

Only show 2 entries with list of files and status of change
```git
$ git log --name-status
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