---
layout: post
title: "NHibernate, IsInitialized and Lazy Loading"
categories: blog
tags: [programming,learning]
image:
  path: "https://www.miscampbell.com/images/lazy-load-large.png"
  feature: lazy-load-large.png
  teaser: lazy-load-small.png
  credit: Smashing Magazine
  creditlink: "https://www.smashingmagazine.com/2015/02/redefining-lazy-loading-with-lazy-load-xt/"
---

This week I had a situation where I had a child object which could have been loaded from my database using NHibernate or which could have already been loaded. My default configuration is to lazy load the child object, however, it was actually quite a complex object so I had a more complex DB query to fetch it from the database. However, if I already had the object, I had no real desire to execute the DB query.

I thought this would actually be quite a complex problem to solve and include plumbing the depths of the NHibernate source code. However, it turns out NHibernate have provided a handy utility to tell if an object has already been initialized from the database or not (without loading it).

```NHibernateUtil.IsInitialized(object);```

I ended up wrapping it in an extension method like 

<pre>
public static bool IsInitialized(this object source) {
    return NHibernateUtil.IsInitialized(source);
}
</pre>

which means I can mask the underlying database technology from everything else which is going on.

Route to finding this answer:
1. Google "[tell if child has been lazy loaded nhibernate](https://www.google.com/search?q=tell+if+child+has+been+lazy+loaded+nhibernate)"
2. Find [this](http://stackoverflow.com/questions/1317691/checking-existence-of-lazy-loaded-child-without-getting-loading-in-fluent-nhiber) Stack Overflow
3. End up on [this blog post](http://djeeg.blogspot.co.uk/2006/08/nhibernateutilisinitialized.html) which has the answer to my question

Proof that the depths of the Internet have yet to be mined!