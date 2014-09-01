---
layout: post
title: "Variables"
date: 2013-11-21 16:58
---
## Agenda

- What they are used for
- What do they look like
- Standard look

## What are they used for?

Variables are a central part of any programming language and Ruby is no different. Variables are a way to store dynamic values for later. The main idea behind this is that you can then store a value in it and any time you call upon that you can retrieve that value. That stored value is free to modified at your discretion.

Let's define some terms first.

- variable - the entity used to store values or in ruby's case objects!
- assignment - the action of saving to the variable
- access - getting the value from a variable

I can talk about how this is valuable but let's try an example.

```ruby
x = 5 #=> 5 # assignment
x = x + 5 #=> 10 # Reassignment
x #=> 10
```

### What do they look like?

Variables come in all shapes and sizes. But there are some rules for them. A variable is anything word starting with character from the alphabet or $ or _ or @. And the rest can be any combination of alphanumeric characters of any case and _ .

- variable
- @variable
- @@variable
- VARIABLE
- Variable = Class.new
- $variable

This is sort of all over the place. But there are standards for this. Most variables are going to be what's called snake_case. Or as it looks all lower case where new words are separated by an underscore. Here are the guidelines typically for variables.

### The regular variable

Most variables with snake it's used only by the methods you they are created in. They are meant to have very limited mobility/scope. Here's an example.

### @instance_variable

This one is just like other last variable is in snake case, but an entire object knows about this variable. Let me give an example.
