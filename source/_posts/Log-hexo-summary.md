---
title: "[Hexo][04] Summary of hexo blog operation"
date: 2020-02-16 19:03:05
tags: [log,hexo,web]
categories: 
- [porject-log]
- [hexo]
---

# hexo daily command  #

<b>create a new page or article.</b>

~~~
hexo new [layout] <title>
~~~
most useful command `hexo new post [title]`.

|<b>Layout</b> |<b> Path </b>    | <b>content</b> |
|--------------|-----------------|----------------|
|    `post`    | `source/_posts` | blog article   |
|    `page`    |    `source`     | new page at top|
|   `draft`    | `source/_drafts`| article draft  |

The default filename of the `.md` markdown file will be the title.
You can change the default filename by editing the `new_post_name` setting under the `_config.yml` of the blog.
You can add the following element to prefix your filename. For example, `:year-:month-:day-:title.md`.

<b> delete all the cache and static file. </b>
~~~
hexo clean
~~~
use after install a new plugins or having new setting.

<b> generate static file. </b>
~~~
hexo g
~~~

<b> deploy the static file. </b>
~~~
hexo d
~~~

<b> deploy instantly after generate statoc file.</b>
~~~
hexo g -d
~~~

<b> localhost to preview the blog. </b>
~~~
hexo s
~~~

<b> backup the blog to git. </b>
~~~
git add .
git commit -m "remark"
git push origin [branch name]
    -- git push origin hexo
~~~


# used plugins #

## <b> hexo-generator-search </b>

A search function for the blog. You can check the original on [GitHub](https://github.com/wzpan/hexo-generator-search).

install like this. Go to the root of your blog.
```
npm install hexo-generator-search --save
```
enable like this. Edit you blog `_config.yml`.
```yaml
search:
  path: search.xml
  field: all
  content: true
```


## <b> hexo-blog-encrypt </b>

A plugins to encrypt your post. Only password holder can read you article.
check the original on [GitHub](https://github.com/MikeCoder/hexo-blog-encrypt).

install like this. Go to the root of your blog.
```
npm install hexo-blog-encrypt
```
enable like this. Edit you blog article.
```yaml
---
title: Hello World
date: 2016-03-30 21:18:02
password: yourpassword123
---
```
