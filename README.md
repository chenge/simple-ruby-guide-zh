# 第一章 简介

## 内容简介

目标读者：

* 初次编程者
* 初次学习Ruby的程序员

Ruby是适合于初学者的，即使是从未写过程序的人来学，我相信初级部分一天就能学完。

为了帮助你学习更轻松些，我尽量选择了简单的内容。

通过浏览目录，就知道我选择了一些什么内容。初级我选择了三组共四个概念，本书定位初学，所以中高级只是附带介绍一下，选择了介绍单元测试和DSL。这些内容，特别是初级部分，是我根据我的自学经验，认为对初学者比较重要的核心的内容，不是说别的Array、Hash等不重要，只是为了简明和快速学习，做了取舍。

有了这个基础后，遇到不懂的，查阅下参考书就可以了。

我会不定期地修订，增加我认为不错的材料。


## 为什么写这个小书

我希望用最简洁的方式介绍Ruby的要点。

我本身是程序员，05年左右接触Ruby，我是看镐头书入门的，对Ruby的印象不错，但还是觉得不得要领，觉得有些复杂。又过了几年，读了几本参考书才似乎理解了一些。

类似的书一般都涉及很多细节，反而让主干不清晰，初学者往往不得要领，学习负担重。如果一开始读到本书这样的介绍，我认为是有帮助的。

当然这只是入门书，修行要看你自己了。

## 学习计划

建议你分两步，初级体验一天，中级1-6个月。

1. 先学习初初级部分，感性认识和培养兴趣，参考时间一天。
2. 有兴趣继续的话学中级，可自选书籍或者参考下面的中英文电子版，参考时间1-6个月。


* [Ruby in 100 Minutes](http://tutorials.jumpstartlab.com/projects/ruby_in_100_minutes.html)(有目录，简明扼要，介绍了11个常用概念，包括有些另类的Symbol类型，:hello)
* [100分钟的红宝石](http://fanyi.youdao.com/WebpageTranslate?keyfrom=fanyi.web.index&url=http%3A%2F%2Ftutorials.jumpstartlab.com%2Fprojects%2Fruby_in_100_minutes.html&type=AUTO&action=FY_BY_CLICKBUTTON)(有道翻译的中文版，翻译效果不错)
* [20分钟体验 Ruby](https://www.ruby-lang.org/zh_cn/documentation/quickstart/)


## 实验

可以网上实验，或者本机实验。

网上实验

最简单的，[codepad网站直接运行](http://codepad.org/)，代码复制过去，选择ruby.

另一种稍微复杂的方式，去[实验楼网站](http://www.shiyanlou.com/)，linux环境下运行看结果，可以在终端Terminal里运行：irb，就可以与ruby对话了。
<img src='http://simplecloud.qiniudn.com/944bd3db7397a0b714af6a4cb0558a0d' width=800 />

本机实验

linux和苹果上一般都安装好了ruby，运行ruby -v可以看是否安装了。
如果没有的话，请参考[wiki](https://ruby-china.org/wiki)自行安装Ruby。windows上也很容易安装的。

>可以尝试这种现代的交互式自学方式。
>
* [计算客Ruby交互式课程](http://www.jisuanke.com/class/info/14)
* [codeacademy英文Ruby交互式课程](http://www.codecademy.com/en/tracks/ruby)

## 学习社区

http://exercism.io
是很好的英文的互动编程社区。

## 版本变更

变更：

2015-3-26：高级部分改用了DSL的例子，更实用也更容易理解。

2015-1-26：改写单元测试，更容易理解

2015-1-23：增加了“面试准备系列”

## 读者反馈

希望你写下阅读的感受和改进意见。

# 第二章 初级：类和对象

##Ruby的基本设计原则

欢迎开启有趣的Ruby之旅!

Ruby语言的作者Matz在《代码之美》一书中讲述了他的设计思想，就是简洁、保守、简单、灵活性，以及平衡性等五大原则。

```ruby
puts 'hello world'
```

例子中那一行代码，可以说明简洁、保守（puts继承自C语言）和简单。灵活性和平衡性需要在更复杂的代码中可以体会到。

## 类和对象

分类是符合人的思维的。比如人类，每个人就是人类的一个实例，约定都翻译成对象。

```ruby
#注释：定义类
class Person
  def initialize(name)
     @name = name
  end

  #定义方法
  def show_name
    puts @name
  end
end

#创建对象
zhao = Person.new 'zhao yun '
qian = Person.new 'qian wei '

#调用方法
zhao.show_name
qian.show_name
```

简单解释一下:

* class是定义类Person，注意用大写
* def定义了方法
* @name是实例变量的写法
* new是生成对象，两个new就生成了两个对象，会调用initialize这个构造方法，只能用这个名字，name是参数
* 最后两句是调用方法show_name, puts的意思就是显示一段文字

如果你第一次编程，也许你对这些术语还有些陌生，不要紧，多看几次，慢慢就会熟悉起来了。

>参考资料，初次阅读可以跳过，或者选看感兴趣的部分。

>英文视频：Learn to program using Ruby

>共9部分，大约一个小时。[原youtube网址](https://www.youtube.com/channel/UC1dbW9fGofQMbqAIFivmyWw)

>我搬运了三个部分到百度，百度云盘

>[ Part 1- Getting started](http://pan.baidu.com/s/1sjJUfzn)

>[ Part 8- Blocks](http://pan.baidu.com/s/1bnFCSc3)

>[ Part 9- Classes and Objects](http://pan.baidu.com/s/1mgAARs0)

>youtube有字幕，视频听不懂问题也不大，看演示过程就可以了，还可以练习英语，一举两得。

结束语：类和对象是最基本的。

# 第三章 块

块是ruby的特色。

```ruby
3.times do
  puts 'hello world'
end

3.times { puts 'one line hi' }

people = ['zhao', 'qian']

people.each do |x|
  puts x
end
```

以上就是两种块的写法，第一个是无参数，单行的话用括号。后一个带参数x，［］是数组。块可以看成独立的函数，与块前面的方法协同工作，就像二人转。


>参考：

>参考部分来自网上的一些资料，有些是英文的，难度大一些，初学可以跳过，等有需要再看

><img src='http://mixandgo.com/uploads/blog_image/image/20/mastering_ruby_blocks.jpg' width=800 />

>[5分钟block（英文）](http://mixandgo.com/blog/mastering-ruby-blocks-in-less-than-5-minutes)

结束语：块无处不在，两种形式do和｛｝

# 第四章 模块

模块也是Ruby的特色。

```ruby
module Show
  def show_msg
    puts self.class
  end
  Pi = 3.14
end

class Person
  include Show
end

class Desk
  include Show
end

Pi = 2
puts Show::Pi #注释：3.14

Person.new.show_msg #Person
Desk.new.show_msg   #Desk
```

主要有两个作用，一个是作为命名空间，避免名字冲突，比如例子中的Pi。另一个是共享代码，例子中Person和Desk共享Show的代码。

>参考：

>[看懂这个视频(英文版)相当于学会了一半的 Ruby(RubyChina帖子, 帖子里的链接已失效)](https://ruby-china.org/topics/23481)

>[看懂这个视频(英文版)相当于学会了一半的 Ruby(YouTube链接)](https://www.youtube.com/watch?v=y4V9qVTkj3c)

结束语：模块是组织代码的基本方式。

# 第五章 中级：单元测试

开始本章学习。

>补充说明一下：如果你不是很有经验的话，看这个单元测试例子会有困难。可以结合这个例子和简介里提到的基础教程来学习。

关系示意图如下

－－incoming————》测试对象－－－outgoing－－－》依赖对象

主要包括测试对象和依赖对象。

- incoming测试状态。

- outgoing分command和query，command就是有输出，query没有输出。
  * outgoing command测试行为，用mock模拟对象。
  * outgoing query不用测试。

```ruby
 #引用minitest gem，可以自己安装: gem install minitest
require "minitest/autorun"

class Calc
  def initialize(logger)
    @logger = logger
  end

  def add(a, b)
    result = a + b
    r = @logger.log "add #{a}, #{b}"
    result if r
  end
end

 # < 是继承
class TestCalc < MiniTest::Test
  def test_add
    mock_logger = MiniTest::Mock.new
    #mock return true
    mock_logger.expect(:log, true, ['add 2, 5'])
    calc = Calc.new(mock_logger)
    assert calc.add(2, 5) == 7
    mock_logger.verify
  end
end
```

>参考：
>[面试准备系列（英文版）](http://samurails.com/interview/prepare-for-a-ruby-job-interview/)
>可以作为学习的参考。

结束语：单元测试是质量的保证。

# 第六章 高级：元编程和DSL

DSL是特定领域语言，rails里有很多例子，rake, rspec, migration等等。下面这个例子演示了原理，主要用了method_missing。学完后，再看那些rails代码就比较亲切了。

当然本书主要还是入门书，更多的请参考《Ruby元编程》这本书。

```ruby
class FancyMarkup
  attr_accessor :indents, :html

  def initialize
    @indents = 0
    @html = ""
  end

  # Catch-all method to avoid creating methods
  # for each HTML element.
  def method_missing(m, *args, &block)
    tag(m, args, &block)
  end

  # The first method called when creating an
  # HTML document.
  def document(*args, &block)
    tag(:html, args, &block)
  end

  private

  # Create the HTML tag
  # @param (String|Symbol) HTML tag (ul, li, strong, etc...)
  # @param (Array) Can contain a String of text or a Hash of attributes
  # @param (Block) An optional block which will further nest HTML
  def tag(html_tag, args, &block)
    content = find_content(args)
    options = html_options(find_options(args))

    html << "\n#{indent}<#{html_tag}#{options}>#{content}"
    if block_given?
      @indents += 1
      instance_eval(&block)
      @indents -= 1
      html << "\n#{indent}"
    end
    html << "</#{html_tag}>"
  end

  # Searching the tag arguments, find the text/context element.
  def find_content(args)
    args.select{|arg| arg.is_a? String}.first || nil
  end

  # Searching the tag arguments, find the hash/attributes element
  def find_options(args)
    args.select{|arg| arg.is_a? Hash}.first || {}
  end

  # Indent output number of spaces
  def indent
    "  " * indents
  end

  # Build html options string from Hash
  def html_options(options)
    options.collect{|key, value|
      value = value.to_s.gsub('"', '\"')
      " #{key}=\"#{value}\""
    }.join("")
  end
end

output = FancyMarkup.new.document do
  body do
    div id: "container" do
      ul class: "pretty" do
        li "Item 1", class: :active
        li "Item 2"
      end
    end
  end
end

puts output
```

会得到这个结果：

```html
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

>[本实例英文原文](http://www.leighhalliday.com/creating-ruby-dsl)

# 附录 学习Ruby的一些小窍门

## 必备工具

irb是自带的.

pry更好用一些，可以这样：

```ruby
ls Object
```

像目录操作一样。

## 编辑器

sublime和开源的atom都不错。
SublimeCodeIntel插件可以提供Ruby代码提示。

## 查祖先

```ruby
1.9.3-p545 :023 > String.ancestors
=> [String, Comparable, Object, Kernel, BasicObject]
```

String的前面有四个上级

## 过滤方法

Ruby的方法非常多，以至于不得不用grep了。

```ruby
1.9.3-p545 :049 > [].methods.grep /^me/
=> [:member?, :methods, :method]
```

## 查方法来源

```ruby
1.9.3-p545 :018 > {}.method :select
 => #<Method: Hash#select>
1.9.3-p545 :019 > {}.method :reduce
 => #<Method: Hash(Enumerable)#reduce>
```

method方法可以实现。

## 文档

如果找明确的方法，可以用ri，方便快捷。

```ruby
ri String.sub
```

不过这种方式似乎不好用。有一个专门的dash软件，很好用。似乎是只支持mac。

## 对象模型

各种对象语言的原理是类似的，但是内部实现模型是不一样的。Ruby用起来简单，内部很复杂的。

当你感觉Ruby好用的时候，其实应该感谢Matz的工作。

Kernel模块是核心，很多重要的方法都在里面。推荐看《Ruby元编程》，书中有详细介绍。

## 推荐书籍网站

入门

- Ruby中文官网

- 《笨办法学Ruby》

提高

- 《Eloquent Ruby》

- 《Ruby元编程》

- 《面向对象设计实践指南:Ruby语言描述》

路线图

- 本书属于中间区域，入门书籍。
![books](https://ruby-china-files.b0.upaiyun.com/photo/2015/79aa594a748c3f53008cabedf9388d1c.png)

带有链接的图：https://www.learneroo.com/modules/61/nodes/337

原图：http://www.zappable.com/tag/chart/


# 告别：

希望这本小书成为你学习Ruby的起点，再见！

![请我喝一杯，手机支付宝](https://ruby-china-files.b0.upaiyun.com/photo/2014/742b05af2b572630c94f8c6b544f7d38.jpg)

联系方式：见目录部分

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/chenge/simple-ruby-guide-zh/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

