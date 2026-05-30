---
layout: page
title:  "Setup"
date:   2026-05-05 09:56:00 +0200
permalink: /setup/
categories: setup
---
If you've clicked on this article I imagine you're curious how I've set this all up. It's really quite simple and I'll gladly tell you the tech stack I've used.

I made this website using [Ruby][ruby-docs] in combination with [Jekyll][jekyll-docs]. Jekyll serves as a **static web generator** which allows me to write all my blog posts in **markdown** while Jekyll automatically converts my files into a fully functional blog.   
Why did I pick Jekyll? Well it's quite simple, I've never used it before. I'm always trying to learn and I love trying out new tech stacks!

The set-up is quite easy to create a blog of your own. First you start off by installing Ruby, depending on your OS you can use a **package manager** or simply work using an **installer**.   
Afterwards we want to install a certain **gem**. Gems represent libraries containing reusable Ruby code. The gem we want is **Bundler** which we install using `gem install bundler`. Bundler allows us to easily install other gems together with their dependencies.  
With Bundler we can run `gem install jekyll bundler` to easily install all the dependencies needed for Jekyll.   
Lastly it's a simple matter of running `jekyll new <site-name>` and you'll have your very own blog setup that you can run using `bundle exec jekyll serve`.

Adding a blogpost is quite easy working with Jekyll. I simply add a new **markdown** file under my `_posts` folder. The tricky part however is the naming convention. All files are named like this: `<year>-<month>-<day>-<post-name>.md`  
The only thing the mardown file really needs is this:

```md
---
layout: post
title:  "How I created this blog"
date:   2026-05-05 09:56:00 +0200
categories: 'category'
---
```

Underneath that you are free to write to write whatever content you want for your post!

[ruby-docs]: https://www.ruby-lang.org/en/documentation/
[jekyll-docs]: https://jekyllrb.com/docs/home