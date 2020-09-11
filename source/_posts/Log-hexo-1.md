---
title: "[Hexo][01] - The creation of this website"
date: 2019-10-08 18:23:34
tags: [tutorial,log,hexo,SSH,web]
categories: 
- [porject-log]
- [tutorial]
- [hexo]
---

This is the log of the creation of this website. You may read as a tutorial.
___

##  - Before start. ##
You need to download the following software environment.

* [Git](https://git-scm.com/ "Git") 
* [Node.js](https://nodejs.org/en/ "Node.js")
* [Visual-Studio-Code](https://code.visualstudio.com/ "Visual Studio Code")

##  - Install the environment ##

Create a directory that will contain your web file. For example `D:\myweb`. <br>
Then open Visual-Studio-Code -> Terminal -> New Terminal and `cd` to your directory.

### Install the hexo environment. ###
~~~
npm install hexo
~~~

### Create a hexo project. ###
~~~
hexo init [your file name]
---for example$ hexo init XXXXX.github.io
~~~

`cd` to your project file. For example `D"\myweb\XXXXX.github.io` to do the following step. <br>
### Install the Node.js package manager. ###
~~~
npm install
~~~
After all, your environment is ready. Type the following code to confirm.
~~~
hexo g
hexo s
---INFO  Hexo is running at http://localhost:4000 . Press Ctrl+C to stop.
~~~
ctrl + left click to open the link, you will see the initial page of your website.


##  - deploy your website to github, publish to the network. ##

Open a repositories on github and name it as `[your-account-name].github.io`.


### Generate and/or adding your SSH key to github account. ###
Open Git Bash, and type the following code with your github email account.
~~~
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
~~~
Then you will get.
~~~
> Generating public/private rsa key pair.
> Enter a file in which to save the key (/c/Users/you/.ssh/id_rsa):[Press enter]
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
~~~
Add you SSH key to your github account as following https://help.github.com/en/articles/adding-a-new-ssh-key-to-your-github-account .

finish the github works, we back to our local project continue the setup.

### Install the deployer in your project file. ###
~~~
npm install hexo-deployer-git --save
~~~

Check the `_config.yml`  under your project file. This file contain all the config of your website including the title, url...etc. <br>
At last of the file, you will see `deploy:` , we need to change it as following.
~~~
deploy:
  type: git
  repo: git@github.com:[githubaccount]/[githubaccount].github.io.git
  branch: master
~~~

### deployer and publish your website. ###

~~~
hexo d

>type the [passphrase] of your SSH keys. 
~~~

you will see the website on `[githubaccount].github.io`.

___
<br></br>
___


## Backup your blog to github ##

still using visual studio code terminal at the project file.

### connect your git to github repository. ### 
~~~
git init
git remote add origin git@github.com:[youraccount]/[youraccount].github.io
~~~

### add a new branch. ###
~~~
git checkout -b [yourbranch name]

------For example: git checkout -b hexo
~~~
Then you are Switched to a new branch "hexo".

### Backup 3 step! ###
~~~
git add .
git commit -m "any remark you want"
git push origin [your branch name]
~~~

___
<br></br>
___

Basically you are done all the jobs. The next step is to add some content and maintain the themes.
