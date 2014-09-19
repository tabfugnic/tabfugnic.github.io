---
title: Allowing Logind For All Users
summary: It's important to easily be able to shutdown or suspend your computer. Freedesktop gives that ability, but uses the rather opaque PolicyKit tool to deal with security.
---

I use [i3](http://i3wm.org/), a window manager as essentially a desktop replacement. The issue is that it isn't a desktop replacement, that's also the fun part. My computer does not suspend itself when I close the lid, instead it merely turns of the screen. This isn't great when trying to conserve battery. This had to be approached programmaticly.

In order to suspend a linux machine, there many tools. The one chose was to use systemd and take advantage of freedesktop. Freedesktop, however, uses PolicyKit, an interesting system combining all things Javascript, XML and a lack of documentation.

Mulling over countless websites that suggest either creating

{% highlight bash %}
  [Local Users]
  Identity=unix-user:*
  Action=org.freedesktop.login1.*
  ResultAny=yes
  ResultInactive=yes
  ResultActive=yes
{% endhighlight %}
