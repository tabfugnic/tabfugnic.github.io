---
title: Allowing Logind For All Users
summary: It's important to easily be able to shutdown or suspend your computer. Freedesktop gives that ability, but uses the rather opaque PolicyKit tool to deal with security.
---

I use [i3](http://i3wm.org/), it's window manager to replace a desktop environment. It lacks many of the nice things that are in a full desktop environment. For example, it does not explicitly give a way to suspend your machine.

In order to suspend a linux machine, there many tools. The one chose was to use systemd and take advantage of freedesktop. Freedesktop, however, uses PolicyKit, an interesting system combining all things Javascript, XML and a lack of documentation.

The line of code I want to use is:

{% highlight bash %}
  dbus-send --print-reply --system --dest=org.freedesktop.login1 /org/freedesktop/login1 "org.freedesktop.login1.Manager.Suspend" boolean:true
{% endhighlight %}

This command by default is restricted to admins. With good reason. In a multiuser environment, it would be concerning if anyone at any time could just suspend the whole machine.

For a single user environment, I find this to be acceptable enough.

Mulling over countless websites that suggest either any number of solutions, I finally found this.

{% highlight bash %}
  [Local Users]
  Identity=unix-user:
  Action=org.freedesktop.login1.*
  ResultAny=yes
  ResultInactive=yes
  ResultActive=yes
{% endhighlight %}
