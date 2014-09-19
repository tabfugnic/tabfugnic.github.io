---
title: Using auth-source(netrc) for ERC
layout: post
summary: Never put your passwords in your dotfiles, your IRC configs are no different. auth-source is a powerful tool leveraged by many libraries in Emacs, including ERC.
---

Never save passwords in your dotfiles! It, unfortunately, is an all too common practice. Here's a quick guide on how to use auth-source to do proper automatic login for ERC and freenode or IRC servers with server passwords.

Let's say in your ERC config you have:

`(setq erc-prompt-for-nickserv-password nil)`

Then you either automatically or manually start erc with:

`erc :server "irc.freenode.net" :port 6667 :nick "tabfugnic"`

In your authinfo.gpg you can use the format

`machine <server_url> login <irc_nick> port <port number> secret <your_secret>`

It's very important that you fill in all of these field. If anyone is missing then it will not actually be able to find your secret. ERC requires all four.

So if you are on freenode, which allows you to use your nick identifier as a server password to identify you, then you could have.

`machine irc.freenode.net login tabfugnic port 6667 secret my_extremely_secret_password`
