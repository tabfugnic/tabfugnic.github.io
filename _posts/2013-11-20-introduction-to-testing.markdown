---
layout: post
title: "Introduction to Testing"
date: 2013-11-20 08:55
tags: testing, bewd
---

## What this will help with

- Why do we test?
- What is this text I am looking at?
- How do I perform these tests?


## Why do we test?

Code is by it's very definition logical and takes input that will return the same output. Features in software can be reproduced. Testing is our guarantee that those things will return the same output and feel safe knowing how they will work anytime we use that code.

Testing in any sized software project is a nessecity and helps make you feel safe about what you're developing.

It gives the confidence to refactor as well. Which just means to tweak your code so it's the fastest and cleanest it can possibly be. This will be incredibly reassuring as you move forward.

## What are we using to test?

Ruby comes standard with a testing framework called MiniTest. We're going to use this because it has a really clean and very readable syntax. A general term for this syntax is called a Domain Specific Language(DSL). This is not reserved to MiniTest by the way, Rails has it's own Domain Specific Language.

## That's great, what does this all mean?

Since testing guarantees output, we are going to use tests to guarantee that our homework well... works. You'll receive a list of tests and you're job will be to make them pass. You can easily use this as your guide.

## MiniTest

MiniTest is great because it doesn't require as to add anything special to our software to make it work it just adds a couple of lines to our code to let our code know that we're going to use it.

{% highlight ruby %}
require "minitest/autorun"
{% endhighlight %}

This line of code just informs our application that we're using minitest to test our code. This line is only needed if we have tests in the file.

### Tests

- What are tests?
- What does it mean to make them pass?
- What does it mean to have them fail?
- What?

Tests are just bits of code that validate what are program does.

To make a test pass means that there is the code necessary in your application to make the validations work. These can be called.

Tests are failing until they are validated.

It's just guarantees on our code. That's all. It means confidence.

## What to know for your homework

- What does `describe` mean?
- What does `it` mean?
- What does it mean when is `must_equal`?

### Describe

`describe` is just a separator. It holds other `describe` blocks or your tests. It's used a lot of times to block off a class or method. like the following.

{% highlight ruby %}
# person class
class Person

end

# blocking off your tests for the person class
describe Person do

end
{% endhighlight %}

Here you see that we are now creating a section of tests specifically for our Person class. We could in theory test other things in here, but this is really meant to be the place where we only talk about Person.

### It

`it` again is another separator, but this one has a bit more importance. This is your test. You will use to actually write out what you want to test and then inside that you will go deeper. Let's take a look.

{% highlight ruby %}
class Car
  def initialize

  end
end

describe Car do
  it "initializes the car properly" do
    # Code for test
  end
end
{% endhighlight %}

Wait, I can just write a test as a string and it should work? Not exactly. This is us naming the test. We still actually have to write exactly what it is that we're testing on this inside of this. This is just what we want to prove and we have to make up how we plan to prove that.

Still confused. Stick with me. The next part should help.

### Assertions - must_equal

So we now have this `describe` with an `it` inside. But that's not actually proving anything yet. So what we need to do is add the code that determines how these things work. Inside our `it` we're going to make __assertions__. That's when you see `must_equal` come in. That simply says here let's guarantee that a method will do what we want it to do. Let's take a look.

{% highlight ruby %}
class Table
  def initialize
  end

  def info
    "It's a table"
  end
end

describe Table do
  it "tells us some info about the table" do
    kitchen_table = Table.new # Create a table object/create an instance of Table
    kitchen_table.info.must_equal "It's a table" # Make sure it does what it says it does.
  end
end
{% endhighlight %}

As you see must_equal just makes sure that it does exactly what it says it does. And it has to be inside of `it`

### Skip

A side note. You will see `skip` throughout these tests. When your program is run, these tests will be ignored.


## How do I actually run these tests!?!

So for your tests all you will have to do is run that file in ruby and you can do that by doing:

{% highlight sh %}
ruby objects_homework.rb
{% endhighlight %}

Run this immediately! You'll notice when you run this that it will complain. Use what it gives back to move forward. These tests are actually going to tell you what you need to do to complete you're homework.
