---
layout: post
title: "NWebSec and Content Security Policies"
categories: blog
tags: [programming,learning]
image:
  feature: security-large.jpg
  teaser: security-small.jpg
  credit: Blue Coat Photos
  creditlink: "https://www.flickr.com/photos/111692634@N04/15855489588"
---

Today I stumbled across an excellent open source library called <a href="https://www.nuget.org/packages/NWebsec" target="_blank">NWebSec</a>

Basically, the main goal of the project is to make setting Security Headers in ASP.NET applications super easy.

And it is. The NuGet package adds a bunch of things to your web.config and then the docs at <a href="http://docs.nwebsec.com" target="_blank">http://docs.nwebsec.com</a> explain everything super clearly.

If you're in need of this, it's so much easier than doing everything by hand.

Thanks to the guys <a href="https://twitter.com/NWebsec" target="_blank">@NWebSec</a> for creating such a great library.

Route to finding this library:
1. Google "<a href="https://www.google.co.uk/search?q=content+security+policy+troy+hunt" target="_blank">Content Security Policy Troy Hunt</a>"
2. Visit <a href="https://www.troyhunt.com/implementing-content-security-policy/" target="_blank">Troy Hunt's blog</a>