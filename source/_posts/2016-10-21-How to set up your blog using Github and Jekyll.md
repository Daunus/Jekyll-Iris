---
layout: post
title:  "How to set up your blog using Github and Jekyll"
permalink:  "How to set up your blog using Github and Jekyll"
date:   2016-10-21
categories: jekyll doco
---


##Step 1: Get a jekyll theme
You can Download or clone repo Jekyll Iris `git clone https://github.com/XunaXu/Jeykll-Iris.git`
or find a theme you like from [Jekyll Theme website](http://jekyllthemes.org/)

<br/>

##Step 2: A quick guide for Jekyll using Jekyll Iris

###_config.yml

This is a file with global variables. There are detailed comments to explain all variables in the actual file. Some variables are for toggle features on and off, some are for defining your disqus account, your google analytics id. etc.  So Take a look at _config.yml file to begin with is a good start, and don't forget to run `Jekyll Serve` on the terminal if there are some change in this file.

All global variable can be referred in your source file, here is an example. `\{\{site.author.name\}\}`


<br/>

###Source folder

Source folder is where you should do modifications and put your posts in. It auto generates _site folder for you when the 'jekyll serve' command is runing. You do need to understand this folder if you want to customise your website. Here are basic explanations.

Source folders has five folders, four private, one public.

* #### _includes
It divides a webpage into separated html sections: a build block for all pages.
	* footer
	* header (nav bar in this case)
	* comments (for disqus),
	* social (as social icons, your linked in, facebook, github accounts)
	* share (as allow other to share your posts via twitter, google, etc)
	* subscribe ( mail chimp in this case)
	* scripts (All javascripts file links)
	* head (as <head> in html section)


* ####_layouts
Here are only two layouts defined, one for all post pages and about page. It requires html sections from _includes folder to build a webpage.
	* default layout: a standard webpage with header and footer. it is used for other pages, such as about, index and post pages.
	* about layout: it is based on the post layout.
	* post layout: post layout which defines your blog post.


* ####_posts
A folder containing markdown files for blog posts. This is the only folder you need to change once you are happy with the website functions and looks. You need to define these variables on the top for each post.
	* layout: post as an example, you refer any layout from _layout folder.
	* title:  "Consectetuer adipiscing elit-1"
	* permalink:  "consectetuer-adipiscing-elit-1" (this needs to be unique, it will become a part of the url)
	* date: the post normally are sorted by the date in decent order
	* categories: (it is not used here, but you can define tags to category your posts.)


* ####_sass
	It has all scss files for the site. Your cool makedown style and unique website looks are beginning from here.


* ####assets
	* js folder - Js libraries and packages you are using, copy and paste here.
	* fonts folder - we are using foundation here.
	* images folder - this is where put your avatar
	* css folder - it refers to _sass folder.
	* 404 page
	* about page
	* index page
	* feed.xml  - not being used here.

<br/>

##Step 3:  Get a custom domain and host on github

Now you have customised a local website running on your local pc. you may want to have your own web domain, such as www.xunaxu.com instead of xunaxu.github.io. Here is a youtube tutorial which helped me to set up my site.

[How to: Free Website Hosting + Custom Domain with Github Pages](https://www.youtube.com/watch?v=CJLb8UUIJPg)

<br/>

## Step 4: Production and Deployment
In the production, you probably don't need a base url as http://[your site]/Jekyll-Iris/. so base url in _config.yml should be empty.

The deploy command lines are below, you just need to change the github repo to yours.

{% highlight bash %}
cd _site
git init
git add --all
git commit -m "Deploy to GitHub Pages"
git push --force --quiet "https://github.com/yourAccountName/your.git" master:gh-pages
{% endhighlight %}

<br/>

---

###Useful Tips

* Debugging: Printing out variables using inspect
```
\{\{ page.url | inspect \}\}
```

* Commenting
```
\{\% comment \%\}
	...adfasdf..
\{\% endcomment \%\}
```

* Links
	* [The official Jekyll documentation](https://jekyllrb.com/docs/quickstart/) is highly recommend to have a look.
	* [Markdown Guide](https://guides.github.com/features/mastering-markdown/) is always handy.

<br/>