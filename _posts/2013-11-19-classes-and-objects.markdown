---
layout: post
title: Classes and Objects
date: 2013-11-19 10:59
tags: bewd, classes, objects
---

The very root, the very heart of ruby is objects.  Everything is an object and they receive messages and have attributes.

### Creating Objects

Since everything is an object in Ruby the very nature of typing nearly anything at all would create an object. Such as:

``` ruby
"string"    # a String object
30          # a Fixnum object
3.444       # a Float object
[1, 3, 4]   # an Array object
```

All create objects. To define your own object or most other objects you need to use the syntax `Object.new`. This will actually create a blank and generic object with some messages it can already receive.

We can create our own abstract object ideas using `Class.new` or just `class`. like the following.

``` ruby
class World

end
```

We've just created an abstract object `World`. That means from there we can create a `World` object or instance by typing `World.new`

### Messages

One of the big things that objects do is they receive messages, these are defined as __methods__ on the __class__ and look something like.

``` ruby
class World
  def hello
    # Code goes here
  end
end
```

It's sending messages to objects that give them the ability to respond, change state or set attributes. For example, you could have method that just outputs a string.

{% highlight ruby %}
class World
  def hello
    "Hello World!"
  end
end
{% endhighlight %}

Or you could send a message to an object that adds or changes attributes on the model such as:

{% highlight ruby %}
class World
  # Here we initialize a world with 7 billion people
  def initialize
    @people = 7000000000
  end

  def new_born
    @people = @people + 1
  end
end
{% endhighlight %}

You can even make it change what it is completely! Like in the case of to_s on a number, this turns it into a string! Watch.

{% highlight ruby %}
5.class #=> Fixnum
5.to_s #=> "5"
5.to_s.class #=> String
{% endhighlight %}

### Attributes

In class we talked about attributes. And attributes are denoted by the `@` symbol and are more commonly referred to as instance variables. Let's see an example.

{% highlight ruby %}
class House
  def initialize
    @location = "New York, NY" # @location is an attribute/ instance variable
  end
end
{% endhighlight %}

Attributes are automatically created if they weren't there before hand. So when I said `@location = "New York, NY"` That attribute is immediately created when I say `House.new`

attributes aren't immediately accessible to us. We can access these attribute by creating methods.

{% highlight ruby %}
class Phone
  def initialize(brand)
    @brand = brand
  end

  def brand
    @brand # this gives us the ability to access the @brand attribute
  end

  def brand=(new_brand)
    @brand = new_brand # this allows us to change @brand
  end
end
{% endhighlight %}

###attr

- attr_reader
- attr_writer
- attr_accessor

Since these are attributes and they are very common in ruby we have some syntax that is given to us to do these tasks.

welcome `attr_` syntax. These can can be given at the beginning of the class to replicate what we just did with out attributes. For example

Using `attr_reader` gives us the ability to see the value of that attribute. For example.

{% highlight ruby %}
class Chair
  attr_reader :material
  def initialize(material)
    @material = material
  end
end

#### Above is the same as

class Chair
  def initialize(material)
    @material = material
  end

  def material
    @material
  end
end
{% endhighlight %}

Next is `attr_writer` or the ability to explicitly change the attribute. This is done like so.

{% highlight ruby %}
class Clock
  attr_writer :size
  def initialize(size)
    @size = size
  end
end

#### Above is the same as

class Clock
  def initialize(size)
    @size = size
  end

  def size=(new_size)
    @size
  end
end
{% endhighlight %}

Finally, `attr_accessor` just makes it so you have both.


### End

That's a crash course in how we do classes and objects. Use it how you wish.
