# git help for git-nodeapp1  project

## 1. Create a new repository on the command line Create and push it into github

```
echo "# git-nodeapp1" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/pavlo-shcherbukha/git-nodeapp1.git
git push -u origin master
```
## 2. push an existing repository from the command line

```
git remote add origin https://github.com/pavlo-shcherbukha/git-nodeapp1.git
git push -u origin master
```
## 3. Project links
### 3.1 Local directory
```  
   C:/PSHDEV/IBMCLOUD/NODE/LAPP1/git-nodeapp1
```

### 3.2 github urls
    *https:*  https://github.com/pavlo-shcherbukha/git-nodeapp1.git
    *ssh:*    git@github.com:pavlo-shcherbukha/git-nodeapp1.git
    *web:*    https://github.com/pavlo-shcherbukha/git-nodeapp1

### 3.4. Exception if you work with a private repository and you do not  an owner of the repo.

#### 3.4.1. Generate  SSH key and add  public key into github in your profile

#### 3.4.2. Use special URL for git clone or git push

The pattern of the url
https://github_login:github_psw@github.com/TSM-08/SEND_EMAIL.git 

#### 3.4.3. If the repository cloned set up your username and email in repository


```bush

   [core]
	repositoryformatversion = 0
	filemode = false
	bare = false
	logallrefupdates = true
	symlinks = false
	ignorecase = true
[remote "origin"]
	url = https://psh:password@github.com/TSM-08/SEND_EMAIL.git
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
	remote = origin
	merge = refs/heads/master
[user]
	name = psh-username
	email = psh@gmail.com

``` 
