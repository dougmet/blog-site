---
title: Moving a Blog
author: ''
date: '2021-03-30'
slug: moving-a-blog
categories: []
tags: ["communication"]
---

Toward the end of my PhD, in 2008, I started a blog called "Kinetically Constrained" to talk about science and, as I was into it at the time, bad science. The name came from my thesis topic about kinetically constrained models of glass formers. It also played to that bigger feeling that, despite being such complex unique creatures, our choices are relatively constrained sometimes, and as a group we're much more predictable than we might think.

I used a Google service, called [Blogger](https://www.blogger.com), which did everything I needed. Eventually I got a nice domain name and off I went. I stopped blogging in 2014 but recently want somewhere to put longer thoughts. These days I want to use markdown.

I'm quite proud of some of the posts that were in that blog. Less others. I wanted to keep hold of them, but give up the domain name. When you start to collect a few the renewal cost just doesn't feel worth it anymore. So I wanted to consolidate the domain into dougashton.net and keep a selection of posts.

So I've got a few things to do:

1. Migrate from blogger to a static site generator (I've gone [Hugo](https://gohugo.io) and [Blogdown](https://bookdown.org/yihui/blogdown/)).
2. Publish the new site in [Netlify](https://www.netlify.com/) and point the DNS there.
3. Make a clone of the site in Netlify and point  [blog.dougashton.net](blog.dougashton.net) there.
3. Redirect from the old kineticallyconstrained site to [blog.dougashton.net](https://blog.dougashton.net).
4. Tell Google about the change of address.

None of these were super easy, so here's what I did:

## 1. Migrating from Blogger to Hugo

First step is to backup your Blogger posts. I followed [instructions from Google on backing up the blog](https://support.google.com/blogger/answer/41387?hl=en) to get an xml file with all the posts.

I then used a python utility [blogger-to-hugo](https://pypi.org/project/blogger-to-hugo/) which did the conversion with minimal fuss. This created a minimal Hugo site with a directory full of posts. My original blog posts but now in markdown format with a Hugo header on each.

I made a new Hugo site using the [blogdown tool](https://bookdown.org/yihui/blogdown/) and copied in the converted posts to the `content/post/` directory. I put the images into `static/images/`

Next I tweaked the `config.yaml` in the root of the site to make the permalinks for posts more how I had them before, and how I prefer them:

```yaml
permalinks:
  post: /:year/:month/:title/
```

So this will be `/2021/03/moving-a-blog`. I chose not to change the default [slugs](https://en.wikipedia.org/wiki/Clean_URL#Slug) and decided I'd sort that out with redirects later.

Finally, after a lot of fiddling and fixing bad links, images etc, I had a working version of the site.

## 2. Publishing in Netlify and setting the DNS there

Setting up a site in Netlify is covered widely. Not least in the [Blogdown book itself](https://bookdown.org/yihui/blogdown/netlify.html) so I won't cover that.

### DNS

I decided to let Netlify handle all of the DNS for my old domain (I did something different for the new one). I'm happy with my domain provider so I followed the [instructions to delegate](https://docs.netlify.com/domains-https/netlify-dns/delegate-to-netlify/) from here. That would mean Netlify would point anything `.kineticallyconstrained.com` somewhere but they're not my domain provider.

At this point I've broken my old blog. Instead of going to Blogger it now goes to Netlify. But the URLs are different.

### Redirects

Initially I tried using [Hugo aliases](https://gohugo.io/content-management/urls/#aliases) to get my old blogger URLs, which were `year/month/slug.html` to `year/month/slug/`. But I found I was getting these weird infinite redirect loops where my browser was bouncing back and forth.

In the end I decided to redirect at the Netlify level. The webserver itself is going to do a redirect. [Netlify had good docs on redirects](https://docs.netlify.com/routing/redirects/).

To get this to work I created a text file, with no file extension, called `_redirects` and put it in the `content/` directory. The file looked like this:

```
/2008/07/glass-in-new-york-times.html /2008/07/glass-in-the-new-york-times/
...
```

and one line per redirect. I'll be honest I did it manually, you'll maybe make a script for it. Once this file is deployed, any traffic on the old links get automatically redirected. It worked first time which I wasn't expecting.

So now we have a working port of the site, at the same domain, but now built in Hugo and hosted by Netlify. This might be the end of the guide if you're keeping the same domain name. I wanted to also change the address.

## 3. Clone the site and point the new domain there

Before worrying about redirects I wanted to get a copy of the site (without the redirects) working on the new domain, [blog.dougashton.net](https://blog.dougashton.net). Note that this is a subdomain of `dougashton.net` and this time I didn't want to give Netlify full control of the DNS.

Instead I made the site on Netlify without a domain. You get a weird looking address like `donkey-vegetable-iahaj` (you can get a prettier one if you want, but we don't). Then I went back to my domain name provider and setup an NS record:

![NS record pointing blog subdomain to Netlify name servers](dns-ns.jpg)

From here when I went back to Netlify it was happy and went off and did the LetsEncrypt certificates (to allow https) and all sorts of other things it does automatically for you.

At this point we have identical sites at kineticallyconstrained.com and [blog.dougashton.net](https://blog.dougashton.net). I just want to redirect the old one to the new one.

## 4. Redirect old domain to new domain

Again, you only need to do this if you're changing domain name.

Back over at the old site. The first one we made. The `_redirects` file we used before can also redirect across sites. So I changed this to do:


```
/2008/07/glass-in-new-york-times.html https://blog.dougashton.net/2008/07/glass-in-the-new-york-times/
...
```

I also want everything else to redirect too. For this I added the following to the `netlify.toml` file in the root of the site:

```toml
[[redirects]]
  from = "/*"
  to = "https://blog.dougashton.net/:splat"
  status = 301
  force = true
```

The splat thing just says, whatever URL you put in after the root part, put that after `blog.dougashton.net`. So `kineticallyconstrainedcom/hello-world.txt` would go to `blog.dougashton.net/hello-world.txt`. The 301 tells the browser, and search engines, that this is a permanent redirect.

Once deployed to the old site this sends all its traffic over to [blog.dougashton.net](https://blog.dougashton.net) as desired.

So in summary: we have two sites at this point. Both hosted by Netlify.

old site: All traffic redirects to new site. And some specific URLs are redirected to some specific new URLs.

new site: Has no idea old site exists.

I not long ago renewed the old domain name so I'll just keep the redirect going for the rest of the year and try to remember to update links where I have them still.

## 5. Tell Google Search about the Change of Address

This last bit is kind of optional. But if your posts appear in Google searches you may wish to try to retain that traffic, or at least guide people away from the old domain that you'll cut loose.

I used the [Google Change of Address Tool](https://support.google.com/webmasters/answer/9370220?hl=en) to tell them about the switch. Any tech guide I give here will be a little unfair as Google managed both domains it was very easy. If they're managed by another provider you'll need some extra steps to prove ownership.

It's not totally clear this has done anything. But if I leave the redirect up long enough Google says that within 6 months the search results will update.

## Summary

That was quite a lot of steps. The take home message is really "Choose your domain name wisely". But doing this migration was quite fun and helped my understanding of how the bowels of the internet actually function.

I do like my new Hugo/Netlify setup but if, in the future when fashion inevitably moves me to something-new.com, it should be relatively easy to convert the posts, point the DNSes, and flutter away on the fickle wind of change.

[Code for old site](https://github.com/dougmet/kincon)

[Code for new site](https://github.com/dougmet/blog-site)
