---
title: "[Hexo][02] - The creation of this website"
date: 2019-10-10 03:49:51
tags: [tutorial,log,hexo,web]
categories: 
- [porject-log]
- [tutorial]
- [hexo]
---

This is the log of the creation of this website. You may read as a tutorial.
___

After create and run the starting page, we need to add theme and post.

# Adding a themes to your website #

The first thing is to find a theme that you wish to apply to your website.
You can find many themes on here https://hexo.io/themes/index.html .

After you find the theme, you click the theme name to get in the theme github page like this.
![this is the theme of this blog](https://i.imgur.com/y5CQAji.png)
<br>
_All code here will use this theme as example, if you are using a different theme, plz change the code to fit your theme._

## Clone the theme to your local file. ##
Go back to VScode terminal, your web file directory and clone the theme by this code.
~~~
git clone git://github.com/Molunerfinn/hexo-theme-melody.git themes/melody
~~~
## Change your web theme. ##
Then go to file `[yourweb]\_config.yml` fine `theme:` at the last and change it to your theme.
~~~
theme: melody
~~~
And preview in localhost by this 3 command.
~~~
hexo clean
~~~
~~~
hexo g
~~~
~~~
hexo s
~~~
_And also `hexo d` to deploy, and back up 3 step :`git add .`, `git commit -m "typesomething"`, and `git push origin hexo`._

___
<br></br>

# Adding page to your website. #

Here is how to add some defult page of the theme. (If your theme has provided these pages.)

For the tags page:
~~~
hexo new page "tags"
~~~
Then a new directory `tags` should be created and it have a file call `index.md`.
Open the `index.md` file, and add a `type` become like this.
~~~
 ---
title: tags
date: 2019-10-08 05:48:26
type: "tags"
---
~~~

categories page will be same procedure.
~~~
hexo new page "categories"
~~~
Then a new directory `categories` should be created and it have a file call `index.md`.
Open the `index.md` file, and add a `type` become like this.
~~~
 ---
title: categories
date: 2019-10-08 05:48:26
type: "categories"
---
~~~
You can add more pages you want by the same step.

## Add the page to the menu. ##
Go to the `_config.yml` __under your theme directory. NOT your website file.__ <br>
`[youwebfile]\themes\melody\_config.yml` and add your page like this.
~~~
menu:
  Home: /
  Archives: /archives
  Tags: /tags
  Categories: /categories
  #XXX: /xxx
~~~

___

<br></br>

# Adding post to your website. #

Finally add some real content to the website. Here is how to add post.
Type the following code, and fill in the file name of you post.
~~~
hexo new [filename]
~~~
And you can add some tags and categories to your post like this.
~~~
---
title: "[Hexo][01] - The creation of this website"
date: 2019-10-08 18:23:34
tags: [tutorial,log,hexo,SSH,web]
categories: 
- [porject-log]
- [tutorial]
- [hexo]
---
~~~
Another example:
~~~
---
title: "[Hexo][02] - The creation of this website"
date: 2019-10-10 03:49:51
tags: [tutorial,log,hexo,web]
categories: 
- [porject-log]
- [tutorial]
- [hexo]
---
~~~
