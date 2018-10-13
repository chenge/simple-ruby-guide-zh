# Ruby Little Book 3 Days

# Chapter 1 Introduction

##  brief introduction

Target audience:

* First time programmer
* First time learning Ruby programmers

Ruby is suitable for beginners, even those who have never written a program to learn, I believe that the primary part can be completed in one day.

To help you learn more easily, I try to choose simple content.

By browsing the directory, I know what I chose. At the beginning, I chose three groups of four concepts. This book is aimed at beginners, so the middle and high level are just introduced, and I introduced the unit test and DSL. These contents, especially the primary part, are the core content that I think is more important for beginners based on my self-learning experience. It is not that other Arrays, Hash, etc. are not important, just for concise and quick learning.

With this foundation, if you don't understand it, check out the reference book.

I will revise it from time to time and add materials that I think are good.


##  Why write this little book

I want to introduce the main points of Ruby in the most concise way.

I am a programmer myself. I was exposed to Ruby around 2005. I was looking at the introduction of the book. I had a good impression of Ruby, but I still felt that I had no choice but to feel complicated. After a few more years, I read a few reference books and seemed to understand some.

Similar books generally involve a lot of details, but the backbone is not clear, beginners often have no way to go, and the burden of learning is heavy. If I read the introduction of this book at first, I think it is helpful.

Of course, this is just an introductory book. Practice depends on yourself.

##  study plan

It is recommended that you take two steps, one day for primary experience and one to six months for intermediate level.

1. Learn the first elementary part first, perceive and cultivate interest, and refer to the time of day.
2. If you are interested in continuing to learn the intermediate level, you can choose your own books or refer to the electronic version in Chinese and English below. The reference time is 1-6 months.


* [Ruby in 100 Minutes](http://tutorials.jumpstartlab.com/projects/ruby_in_100_minutes.html) (There are directories, concise, and introduces 11 common concepts, including some alternative Symbol types, :hello)
[100 minutes of ruby](http://fanyi.youdao.com/WebpageTranslate?keyfrom=fanyi.web.index&url=http%3A%2F%2Ftutorials.jumpstartlab.com%2Fprojects%2Fruby_in_100_minutes.html&type=AUTO&action=FY_BY_CLICKBUTTON)( Chinese version of the translation, the translation is good)
* [20 minutes experience Ruby](https://www.ruby-lang.org/en_us/documentation/quickstart/)


##  experiment

You can experiment online or natively.

Online experiment

The easiest, [codepad website runs directly](http://codepad.org/), the code is copied in the past, choose ruby.

Another slightly more complicated way, go to [Experimental Building Website](http://www.shiyanlou.com/), run the linux environment to see the results, you can run in the terminal Terminal: irb, you can talk to ruby.
<img src='http://simplecloud.qiniudn.com/944bd3db7397a0b714af6a4cb0558a0d' width=800 />


Native experiment

Ruby is usually installed on Linux and Apple. Run ruby ​​-v to see if it is installed.
If not, please install Ruby yourself by referring to [wiki](https://ruby-china.org/wiki). Windows is also very easy to install.

> Try this modern interactive self-learning method.
>
* [Compute Ruby Interactive Course](http://www.jisuanke.com/class/info/14)
* [codeacademy English Ruby Interactive Course](http://www.codecademy.com/en/tracks/ruby)

##   Community
Http://exercism.io
It is a good English interactive programming community.

##   version change

change:

2015-3-26: The advanced part uses the DSL example, which is more practical and easier to understand.

2015-1-26: Rewriting unit tests is easier to understand

2015-1-23: Added "Interview Preparation Series"

##   reader feedback
I hope you can write down the feelings of reading and improve your opinions.



![Division line](http://img-storage.qiniudn.com/15-6-13/61875638.jpg)

# Chapter 2 Elementary: Classes and Objects

##  Ruby's basic design principles

Welcome to the fun Ruby tour!

Matz, the author of the Ruby language, describes his design ideas in the book Beauty of Code, which is the five principles of simplicity, conservatism, simplicity, flexibility, and balance.

Puts 'hello world'

The line of code in the example can be concise, conservative (puts inherited from C) and simple. Flexibility and balance need to be understood in more complex code.

##   Class and Object
Classification is in line with human thinking. For example, human beings, each person is an instance of human beings, and the conventions are translated into objects.

```
#Defining classes
Class Person
  Def initialize(name)
     @name = name
  End

  #definition method
  Def show_name
    Puts @name
  End
End

#Create object
Zhao = Person.new 'zhao yun '
Qian = Person.new 'qian wei '

#call method
Zhao.show_name
Qian.show_name
```        


Briefly explain:

* class is to define the class Person, pay attention to capitalize
* def defines the method
* @name is the way the instance variable is written
* new is the generated object, two new will generate two objects, will call the initialize constructor, can only use this name, name is the parameter
* The last two sentences are called method show_name, puts means to display a paragraph of text

If you are programming for the first time, maybe you are a little stranger to these terms. It doesn't matter. If you look at it a few times, you will become familiar with it.

> References, the first reading can be skipped, or select the part of interest.

> ##   English video: Learn to program using Ruby

> A total of 9 parts, about an hour. [original youtube URL](https://www.youtube.com/channel/UC1dbW9fGofQMbqAIFivmyWw)

> I carried three parts to Baidu, Baidu cloud disk
>[ Part 1- Getting started](http://pan.baidu.com/s/1sjJUfzn)

>[ Part 8- Blocks](http://pan.baidu.com/s/1bnFCSc3)

>[ Part 9- Classes and Objects](http://pan.baidu.com/s/1mgAARs0)

>youtube has subtitles, the video does not understand the problem is not big, you can see the demonstration process, you can practice English, kill two birds with one stone.

Conclusion: Classes and objects are the most basic.

![Division line](http://img-storage.qiniudn.com/15-6-13/61875638.jpg)



# Chapter 3 Block

The block is a feature of ruby.

```
3.times do
  Puts 'hello world'
End

3.times { puts 'one line hi' }

People = ['zhao', 'qian']

People.each do |x|
  Puts x
End
```


The above is the way to write two blocks, the first one is no parameter, the single line is bracketed. The latter with the parameter x, [] is an array. A block can be thought of as an independent function, working in tandem with the methods in front of the block, just like a two-person turn.


>Reference:

>The reference part comes from some information on the Internet. Some of them are in English. It is more difficult. Beginners can skip it. If you need to see it again.



><img src='http://mixandgo.com/uploads/blog_image/image/20/mastering_ruby_blocks.jpg' width=800 />

>[5 minute block (English)](http://mixandgo.com/blog/mastering-ruby-blocks-in-less-than-5-minutes)

Conclusion: Blocks are everywhere, two forms do and {}

![Division line](http://img-storage.qiniudn.com/15-6-13/61875638.jpg)

# Chapter 4 Module

Modules are also featured in Ruby.
```ruby
Module Show
  Def show_msg
    Puts self.class
  End
  Pi = 3.14
End

Class Person
  Include show
End

Class desk
  Include show
End

Pi = 2
Puts Show::Pi #Note: 3.14

Person.new.show_msg #Person
Desk.new.show_msg #Desk
```

There are two main functions, one is to use as a namespace to avoid name conflicts, such as Pi in the example. The other is shared code, in which the Person and Desk share the code for Show.

>Reference:

>[Reading this video (English version) is equivalent to learning half of Ruby](https://ruby-china.org/topics/23481)

Conclusion: Modules are the basic way to organize code.

![Division line](http://img-storage.qiniudn.com/15-6-13/61875638.jpg)

# Chapter 5 Intermediate: Unit Test


Start this chapter.

>Additional note: If you are not very experienced, it will be difficult to see this unit test example. You can combine this example and the basic tutorials mentioned in the introduction to learn.

The relationship diagram is as follows

--incoming————"Test object---outgoing---"Dependent object

It mainly includes test objects and dependent objects.

- incoming test status.

- The outgoing sub-command and the query, the command is output, and the query has no output.
  * outgoing command test behavior, mock the object with mock.
  * outgoing query is not tested.

```
 #minitest gem, you can install it yourself: gem install minitest
Require "minitest/autorun"

Class Calc
  Def initialize(logger)
    @logger = logger
  End

  Def add(a, b)
    Result = a + b
    r = @logger.log "add #{a}, #{b}"
    Result if r
  End
End

# < is inheritance
Class TestCalc < MiniTest::Test
  Def test_add
    Mock_logger = MiniTest::Mock.new
    #mock return true
    Mock_logger.expect(:log, true, ['add 2, 5'])
    Calc = Calc.new(mock_logger)
    Assert calc.add(2, 5) == 7
    Mock_logger.verify
  End
End

```
>Reference:
>[Interview Preparation Series (English)](http://samurails.com/interview/prepare-for-a-ruby-job-interview/)
> can be used as a reference for learning.

Conclusion: Unit testing is a guarantee of quality.

![Division line](http://img-storage.qiniudn.com/15-6-13/61875638.jpg)

# Chapter 6 Advanced: Meta Programming and DSL

DSL is a domain-specific language, there are many examples in rails, rake, rspec, migration and so on. The following example demonstrates the principle, mainly using method_missing. After learning, look at the rails code is more intimate.

Of course, this book is mainly an introductory book. For more details, please refer to the book "Ruby Metaprogramming".

```ruby

Class FancyMarkup

  Attr_accessor :indents, :html

  Def initialize
    @indents = 0
    @html = ""
  End

  # Catch-all method to avoid creating methods
  # for each HTML element.
  Def method_missing(m, *args, &block)
    Tag(m, args, &block)
  End

  # The first method called when creating an
  # HTML document.
  Def document(*args, &block)
    Tag(:html, args, &block)
  End

  Private

  # Create the HTML tag
  # @param (String|Symbol) HTML tag (ul, li, strong, etc...)
  # @param (Array) Can contain a String of text or a Hash of attributes
  # @param (Block) An optional block which will further nest HTML
  Def tag(html_tag, args, &block)
    Content = find_content(args)
    Options = html_options(find_options(args))

    Html << "\n#{indent}<#{html_tag}#{options}>#{content}"
    If block_given?
      @indents += 1
      Instance_eval(&block)
      @indents -= 1
      Html << "\n#{indent}"
    End
    Html << "</#{html_tag}>"
  End

  # Searching the tag arguments, find the text/context element.
  Def find_content(args)
    Args.select{|arg| arg.is_a? String}.first || nil
  End

  # Searching the tag arguments, find the hash/attributes element
  Def find_options(args)
    Args.select{|arg| arg.is_a? Hash}.first || {}
  End

  # Indent output number of spaces
  Def indent
    " " * indents
  End

  # Build html options string from Hash
  Def html_options(options)
    Options.collect{|key, value|
      Value = value.to_s.gsub('"', '\"')
      " #{key}=\"#{value}\""
    }.join("")
  End
End

Output = FancyMarkup.new.document do
  Body do
    Div id: "container" do
      Ul class: "pretty" do
        Li "Item 1", class: :active
        Li "Item 2"
      End
    End
  End
End

Puts output

```
Will get this result:

```
<html>
  <body>
    <div id="container">
      <ul class="pretty">
        <li class="active">Item 1</li>
        <li>Item 2</li>
      </ul>
    </div>
  </body>
</html>
```


>[This example is in English](http://www.leighhalliday.com/creating-ruby-dsl)

![Division line](http://img-storage.qiniudn.com/15-6-13/61875638.jpg)


# Appendix Learn some tips for Ruby

##   tools

Irb comes with it.

Pry is better to use, so you can do this:

Ls Object

Like a directory operation.

##  editor

Sublime and open source atoms are good.
The SublimeCodeIntel plugin can provide Ruby code hints.

##   ancestor

1.9.3-p545 :023 > String.ancestors
 => [String, Comparable, Object, Kernel, BasicObject]

There are four superiors in front of the String

##  Filter method

Ruby has so many methods that I have to use grep.

1.9.3-p545 :049 > [].methods.grep /^me/
 => [:member?, :methods, :method]

##  method

1.9.3-p545 :018 > {}.method :select
=> #<Method: Hash#select>
1.9.3-p545 :019 > {}.method :reduce
=> #<Method: Hash(Enumerable)#reduce>

The method method can be implemented.

## Document

If you are looking for a clear method, you can use ri, which is convenient and quick.

Ri String.sub

However, this approach does not seem to work well. There is a dedicated dash software that works great. It seems to only support mac.

## object model

The principles of various object languages ​​are similar, but the internal implementation model is different. Ruby is simple to use and complex internally.

When you feel that Ruby is easy to use, you should actually thank Matz for his work.

The Kernel module is the core and many important methods are in it. It is recommended to read "Ruby Metaprogramming", which is described in detail in the book.

##  Books

getting Started

- Ruby Chinese official website

- "Stupid way to learn Ruby"

improve

- Eloquent Ruby

- Ruby Meta Programming

- Object-Oriented Design Practice Guide: Ruby Language Description

route map

- This book belongs to the middle area, the entry book.
![books](https://ruby-china-files.b0.upaiyun.com/photo/2015/79aa594a748c3f53008cabedf9388d1c.png)

Diagram with links: https://www.learneroo.com/modules/61/nodes/337

Original image: http://www.zappable.com/tag/chart/




# farewell:

I hope this little book is the starting point for you to learn Ruby, goodbye!


