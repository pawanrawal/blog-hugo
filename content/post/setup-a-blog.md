+++
date = "2016-04-16T00:17:01+05:30"
description = ""
title = "How to setup a blog"

+++

For a long time I have wanted to setup my blog and share my learnings. This week I got down to getting it done. Through this post I want to help you setup your blog on your website.

There are multitude of ways of setting up your blog, you could set it up on Wordpress or just write posts on Medium. The method that I am going to outline below would mostly suit developers.

Sometime ago I came across this [post](https://medium.freecodecamp.com/domain-registrars-dns-and-hosting-353e4163a19#.b3jca1giu) on Medium. Its an excellent post which outlines the various steps needed to setup your website. 

1. I bought my domain from namecheap.com

+ Added my site to Cloudflare

3. Used custom DNS on Namecheap to point mysite to Cloudflare nameservers

    For the above steps you can follow the instructions to the post I linked to above.

4. Setup Github pages - I didn't want to host the site myself, Github Pages looked simple and seemed to fit my use case.

5. Setup Hugo - For my blog, I am using [Hugo](https://gohugo.io/), a static Web Engine written in Golang. It has some pretty cool themes. I am using [hugo-cactus-theme](https://github.com/digitalcraftsman/hugo-cactus-theme) for my blog. Hugo has a bunch of cool features. It has a built in hot reload, where you can preview the changes locally as soon as you make any changes. 

To integrate Hugo with Github Pages, I followed this [tutorial](https://gohugo.io/tutorials/github-pages-blog/#hosting-personal-organization-pages) on the Hugo website. Github Pages has options for a Project or Organization/Users site. I am using the Users site, so I followed the simpler instructions for hosting personal pages. It involves setting up two repos, one for hosting Hugo content(which is a normal repo) and the other(your public folder) as a git submodule which is a github pages repo. There is also a cool `deploy.sh` script there which can be used to deploy to the Github pages repo.

6. [Add CNAME](https://help.github.com/articles/setting-up-your-pages-site-repository/#adding-your-custom-domain-to-a-cname-file) file to Github Pages repo.

7. We are almost done. Now we just need to add CNAME records to Cloudflare to point our domain name to github servers. I added two CNAME records. One with name @ and domain name pawanrawal.github.io and the other with name www and domain name pawanrawal.github.io

This made sure that both pawanrawal.com and www.pawanrawal.com are served by my Github pages repo.

I still have to figure out a bunch of things about the blog, but its in a good enough state now and I can start posting regularly to it.

Feel free to leave comments or ask any doubts you might have.