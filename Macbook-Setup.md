## Macbook Development Environment Setup

### GitHub Setup
- Create SSH keys on macbook and add keys to GitHub profile. Just type `return` on prompts and keys get saved to `~/.ssh`.
    ```shell
    $ ssh-keygen
    ```
    `id_rsa` is private key and `id_rsa.pub` is public key

- Add SSH public key `~/.ssh/id_rsa.pub` to Github and verify that connection is working
    - Copy public key
     ```shell
     $ cat ~/.ssh/id_rsa.pub | pbcopy
    ```
    - Go to github.com settings and add a ssh key.

    - Test connection from your laptop to GitHub

    ```shell
    $ ssh -T git@github.wdf.sap.corp
    Hi i313873! You've successfully authenticated, but GitHub does not provide shell access.
    ```
- Installing Git
    - Open terminal on your MacBook
    - Just type `git` and enter, it will open window to ask you to install git. Follow the instructions and complete setup
    - Verify if git got installed
    ```shell
    $ git version
    git version 2.17.2 (Apple Git-113)
    ```

### Software Setup

#### JDK 8

- Download jdk 8 from Oracle [JDK Download location](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

- You should have `jdk-8u202-macosx-x64.dmg` file in `Downloads` folder. 

- Double click on file and install it and then drag and drop to `Applications`

- Set `JAVA_HOME` in `~/.bash_profile` as shown below. You can close the terminal and see if it gets applied
   ```shell
   export JAVA_HOME=$(/usr/libexec/java_home)
   ```
   ```
   $ echo $JAVA_HOME
   /Library/Java/JavaVirtualMachines/jdk1.8.0_202.jdk/Contents/Home

   $ javac -version
   javac 1.8.0_202
   ```

#### Install `brew` package manager

- Install xcode-select, it might be available already.
```
$ xcode-select --install
xcode-select: error: command line tools are already installed, use "Software Update" to install updates
```

- Request Admin PRivileges before running the script
```shell
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
Check if gets installed properly
```
$ brew doctor
```

### Install softwares using `brew`

1. Install `maven`

    ```shell
    $ brew install maven

    $ mvn -version
    Apache Maven 3.6.0 (97c98ec64a1fdfee7767ce5ffb20918da4f719f3; 2018-10-25T00:11:47+05:30)
    Maven home: /usr/local/Cellar/maven/3.6.0/libexec
    Java version: 1.8.0_202, vendor: Oracle Corporation, runtime: /Library/Java/JavaVirtualMachines/jdk1.8.0_202.jdk/Contents/Home/jre
    Default locale: en_US, platform encoding: UTF-8
    OS name: "mac os x", version: "10.14.2", arch: "x86_64", family: "mac"
    ```

2. Install `ant`

    ```shell
    $ brew install ant
    
    $ brew install ant-contrib
    ```
    - Note the install directory, it should be like `/usr/local/Cellar/ant/1.10.5/libexec/lib/`

    - set environment variable in `~/.bash_profile` as shown

    ```
    export ANT_HOME=/usr/local/Cellar/ant/1.10.5/libexec
    ```
    - Copy the `ant-contrib-1.0b3.jar` to ANT lib.
    ```
    $ cp /usr/local/Cellar/ant-contrib/1.0b3/share/ant/ant-contrib-1.0b3.jar $ANT_HOME/lib
    ```
    - Verify ant installation
    ```
    $ ant -version
    Apache Ant(TM) version 1.10.5 compiled on July 10 2018
    ```