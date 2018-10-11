## 引言
### 读者定位

定位读者为懂得基本编程概念。为了简短忽略了基本概念，如果你觉得理解困难的话，考虑找更基础的书来看。

### Rust是什么
> [Rust](http://www.rust-lang.org/)<span data-type="color" style="color:rgb(51, 51, 51)"><span data-type="background" style="background-color:rgb(255, 255, 255)"> </span></span>是一门注重安全（safety）、速度（speed）和并发（concurrency）的现代系统编程语言。Rust 通过内存安全来实现上述目标，但不用垃圾回收机制（Garbage collection, GC)。

如果你看了那个简单的介绍还不明真相的话，在阅读前可以看看[intorust](http://intorust.com)的英文短视频介绍，如果还在犹豫是否学习Rust的话，可以浏览下[《爱上Rust》。](https://www.yuque.com/progfun/rust/yc0dqk)

本书采用极简风格，不求大全，目标是学完后有基本的了解。希望是轻松的方式，两三天就学完。

参考了[《通过例子学Rust》](https://rustwiki.org/zh-CN//rust-by-example/index.html)，[《RustPrimer》](https://rustcc.gitbooks.io/rustprimer/content/)两本书，更多内容请移步前往。

## 第1章：基础知识
当你开始阅读的时候，说明你已经有一些兴趣了。
Rust入门非常简单，不需要任何配置。

可以去[playground](https://play.rust-lang.org/)在线运行代码。本地安装就省略了，请参考引言中的参考书。

下面是hello world:

```c
// 这是注释内容，将会被编译器忽略掉

fn main() {
    println!("Hello Rust World!");
}
```
## 
`println!` 是一个 [宏](https://rustwiki.org/zh-CN//rust-by-example/macros.html)（macros），可以将文本输出到控制台（console）。

使用 Rust 的编译器 `rustc` 可以将源程序生成可执行文件：

```bash
$ rustc hello.rs
```

`rustc` 编译后将得到可执行文件 `hello`。

```bash
$ ./hello
Hello Rust World!
```

有一个[runner](https://github.com/stevedonovan/runner)可以一步运行。

另外自带的cargo可以提供项目管理，在小项目里有介绍。

## 第2章：结构体、Trait

先看看结构体：


```c
// 单元结构体
struct Nil;

// 元组结构体
struct Pair(i32, f32);

// 带有两个字段的结构体
struct Point {
    x: f32,
    y: f32,
}

// 结构体可以作为另一个结构体的字段
#[allow(dead_code)]
struct Rectangle {
    p1: Point,
    p2: Point,
}

fn main() {
    // 实例化结构体 `Point`
    let point: Point = Point { x: 0.3, y: 0.4 };

    // 访问 point 的字段
    println!("point coordinates: ({}, {})", point.x, point.y);

    // 实例化一个单元结构体
    let _nil = Nil;

    // 实例化一个元组结构体
    let pair = Pair(1, 0.1);

    // 访问元组结构体的字段
    println!("pair contains {:?} and {:?}", pair.0, pair.1);

    // 解构一个元组结构体
    let Pair(integer, decimal) = pair;

    println!("pair contains {:?} and {:?}", integer, decimal);
}
```

Trait

```c
trait HasArea {
    fn area(&self) -> f64;
}

struct Circle {
    radius: f64,
}

impl HasArea for Circle {
    fn area(&self) -> f64 {
        std::f64::consts::PI * (self.radius * self.radius)
    }
}

fn main() {
    let c = Circle {
        radius: 1.0f64,
    };
    println!("circle c has an area of {}", c.area());
}


```

这个程序会输出：

```c
circle c has an area of 3.141592653589793
```

## 第3章：HashMap、数组

先看看HashMap的简单用法。

```c
use std::collections::HashMap;

fn main(){
    let mut come_from = HashMap::new();
    // 插入
    come_from.insert("WaySLOG", "HeBei");
    come_from.insert("Marisa", "U.S.");
    come_from.insert("Mike", "HuoGuo");
    
    // 查找key
    if !come_from.contains_key("elton") {
        println!("Oh, 我们查到了{}个人，但是可怜的Elton猫还是无家可归", come_from.len());
    }
    
    // 根据key删除元素
    come_from.remove("Mike");
    println!("\nMike猫！\n");
    
    // 利用get的返回判断元素是否存在
    let who = ["MoGu", "Marisa"];
    for person in &who {
        match come_from.get(person) {
            Some(location) => println!("{} 来自: {}", person, location),
            None => println!("{} 也无家可归啊.", person),
        }
    }
    
    // 遍历输出
    println!("\n那么，所有人呢？");
    for (name, location) in &come_from {
        println!("{}来自: {}", name, location);
    }
}
```

再看看数组：
```cpp
fn main() {
    let mut array: [i32; 3] = [0; 3];

    array[1] = 1;
    array[2] = 2;

    assert_eq!([1, 2], &array[1..]);

    // This loop prints: 0 1 2
    for x in &array {
        println!("{} ", x);
    }
}
```

动态数组Vec

```c
fn main() {
    //创建空Vec
    let v: Vec<i32> = Vec::new();
    println!("{:?}", v);
    
    //使用宏创建空Vec
    let v = vec![1, 2, 3, 4, 5];
    println!("{:?}", v);
    //创建十个零
    let v = vec![0; 10];
    //创建可变的Vec，并压入元素3
    println!("{:?}", v);
    let mut v = vec![1, 2];
    v.push(3);
    println!("{:?}", v);
    //创建拥有两个元素的Vec，并弹出一个元素
    let mut v = vec![1, 2];
    let two = v.pop();
    println!("{:?}", two);
    //创建包含三个元素的可变Vec，并索引一个值和修改一个值
    let mut v = vec![1, 2, 3];
    v[1] = v[1] + 5;
    println!("{:?}", v);
    
}
```



## 》小项目

这个项目参考RustPrimer书，[《Json处理》](https://rustcc.gitbooks.io/rustprimer/content/action/json_data/readme.html)。介绍了caogo的用法。
通过小项目可以验证一下我们对Rust的理解是否正确。

## ——特别章：所有权、借用和生命周期

## 第4章：代码组织

模块的基本用法

```c
mod ccc {
    pub fn print_ccc() {
        println!("{}", 25);
    }
}

fn main() {
    use ccc::print_ccc;

    print_ccc();
    // 或者
    ccc::print_ccc();
}

```

包crate是更大的单位。

真正我们在开发时，会大量用到外部库。外部库是通过

```c
extern crate xxx;
```

这样来引入的。

注：要使上述引用生效，还必须在 `Cargo.toml` 的 `dependecies` 段，加上 `xxx="version num"` 这种依赖说明。

引入后，就相当于引入了一个符号 `xxx`，后面可以直接以这个 `xxx` 为根引用这个 crate 中的 item：

```c
extern crate xxx;

use xxx::yyy::zzz;
```

引入的时候，可以通过 `as` 关键字重命名。

```c
extern crate xxx as foo;

use foo::yyy::zzz;
```

## 第5章：Rust花絮

## ——特别章：错误处理


## 第6章：并发

## 第7章：宏

## 第八章：测试

Rust 的测试特性按精细度划分，分为 3 个层次：

1. 函数级；
2. 模块级；
3. 工程级；

另外，Rust 还支持对文档进行测试。

这里介绍简单的函数级测试。

```c
#[test]
fn it_works() {
    assert!(2>1); // do test work
}
```

非常简单，Rust 中，只需要在一个函数的上面，加上 `#[test]` 就标明这是一个测试用的函数。

有了这个属性之后，在使用 `cargo build` 编译时，就会忽略这些函数。使用 `cargo test` 可以运行这些函数。

Rust 提供了两个宏来执行测试断言：

```c
assert!(expr)               测试表达式是否为 true 或 false
assert_eq!(expr, expr)      测试两个表达式的结果是否相等
```

## 结论 
终于学习完了，看看你花了多少时间，入门了么？
希望学习愉快，等待下一个语言，下次再见！

