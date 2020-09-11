---
title: "[Hexo][03] - 用git實行雙電腦update blog"
date: 2019-10-12 04:16:08
tags: [tutorial,log,hexo,web,git]
categories: 
- [porject-log]
- [hexo]
---

簡單記錄小弟係學校lab同屋企兩部電腦點樣同步更新.
___

例如, 你係學校/公司的A電腦開始起website, 完成咗上兩個tut的步驟, 而家係屋企B電腦想做更新, 第一步係起番相應既develop environment.

# inital on the second computer. #

* [Git](https://git-scm.com/ "Git") 
* [Node.js](https://nodejs.org/en/ "Node.js")
* [Visual-Studio-Code](https://code.visualstudio.com/ "Visual Studio Code")

On any directory.
~~~
npm install hexo
~~~

Clone your website file.
~~~
git clone https://github.com/[youraccount/yourrepository]
~~~

On your repository directory install the Node.js package manager.
~~~
npm install
~~~

Install the deployer.
~~~
npm install hexo-deployer-git
~~~

confirm your environnment.
~~~
hexo g
hexo s
---INFO  Hexo is running at http://localhost:4000 . Press Ctrl+C to stop.
~~~

edit something and deploy it to github. Remember to generate your SSH key to github account.
~~~
hexo d
~~~

B電腦可以更新個website喇~ 之後記得backup d file番github.

# backup to github after edit. #
Backup 3 step!
~~~
git add .
git commit -m "any remark you want"
git push origin [your branch name]
~~~

A, B電腦都有website file同environment. A電腦要更新要點做呢?

Back to the original computer, how to update.
# Replace your local document with github backup. #
~~~
git fetch origin
git reset --hard origin/[your branch name]
~~~

After edit remember to backup your data to github!