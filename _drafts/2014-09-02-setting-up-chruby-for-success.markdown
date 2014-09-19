---
title: Setting up chruby for success
layout: post
summary: RVM is great, but overkill. chruby is light weight and easy to use, but things to work around.
---



- wget

__Install__

In a tmp directory, ideally `~/tmp`. Then run the following commands:

{% highlight bash %}
 wget -O chruby-0.3.8.tar.gz https://github.com/postmodern/chruby/archive/v0.3.8.tar.gz
 tar -xzvf chruby-0.3.8.tar.gz
 cd chruby-0.3.8/
 sudo make install
{% endhighlight %}
