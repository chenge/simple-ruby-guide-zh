## Version 0.8/13.0

## Introduction
### Reader positioning

Position the reader to understand the basic programming concepts. In order to briefly ignore the basic concepts, if you feel that understanding is difficult, consider looking for a more basic book.

### What is Rust?
> [Rust](http://www.rust-lang.org/)<span data-type="color" style="color:rgb(51, 51, 51)"><span data-type="background " style="background-color:rgb(255, 255, 255)"> </span></span> is a modern system programming language that focuses on safety, speed, and concurrency. Rust achieves these goals through memory security, but does not use the Garbage Collection (GC).

If you read the simple introduction and don't know the truth, you can check out the short video introduction of [intorust] (http://intorust.com) before reading. If you are still hesitating to learn Rust, you can browse [ "Love Rust." ](https://www.yuque.com/progfun/rust/yc0dqk)

This book adopts a minimalist style and does not seek encyclopedia. The goal is to have a basic understanding after the completion of the course. Hope is an easy way to finish in two or three days.

Refer to ["Study by Rust"] (https://rustwiki.org/zh-CN//rust-by-example/index.html), [RustPrimer] (https://rustcc.gitbooks.io /rustprimer/content/) Two books, please go to more content.

## Chapter 1: Basics
When you start reading, you have some interest.
Getting started with Rust is very simple and doesn't require any configuration.

You can go to [playground] (https://play.rust-lang.org/) to run the code online. The local installation is omitted, please refer to the reference book in the introduction.

Here is hello world:

```c
// This is the comment content and will be ignored by the compiler.

Fn main() {
    Println!("Hello Rust World!");
}
```
##
`println!` is a [macro] (https://rustwiki.org/zh-CN//rust-by-example/macros.html) (macros) that can output text to the console.

The source program can be used to generate executable files using Rust's compiler `rustc`:

```bash
$ rustc hello.rs
```

`rustc` will get the executable `hello` after compilation.

```bash
$ ./hello
Hello Rust World!
```

There is a [runner] (https://github.com/stevedonovan/runner) that can be run in one step.

In addition, the built-in cargo can provide project management and is introduced in small projects.

## Chapter 2: Structure, Trait

First look at the structure:


```c
// unit structure
Struct Nil;

// tuple structure
Struct Pair(i32, f32);

// structure with two fields
Struct Point {
    x: f32,
    y: f32,
}

// The structure can be used as a field for another structure
#[allow(dead_code)]
Struct Rectangle {
    P1: Point,
    P2: Point,
}

Fn main() {
    // Instantiate the structure `Point`
    Let point: Point = Point { x: 0.3, y: 0.4 };

    // access the field of point
    Println!("point coordinates: ({}, {})", point.x, point.y);

    // instantiate a unit structure
    Let _nil = Nil;

    // instantiate a tuple structure
    Let pair = Pair(1, 0.1);

    // access the fields of the tuple structure
    Println!("pair contains {:?} and {:?}", pair.0, pair.1);

    // Deconstruct a tuple structure
    Let Pair(integer, decimal) = pair;

    Println!("pair contains {:?} and {:?}", integer, decimal);
}
```

Trait

```c
Trait HasArea {
    Fn area(&self) -> f64;
}

Struct Circle {
    Radius: f64,
}

Impl HasArea for Circle {
    Fn area(&self) -> f64 {
        Std::f64::consts::PI * (self.radius * self.radius)
    }
}

Fn main() {
    Let c = Circle {
        Radius: 1.0f64,
    };
    Println!("circle c has an area of ​​{}", c.area());
}


```

This program will output:

```c
Circle c has an area of ​​3.141592653589793
```

## Chapter 3: HashMap, Array

Let's take a look at the simple usage of HashMap.

```c
Use std::collections::HashMap;

Fn main(){
    Let mut come_from = HashMap::new();
    // insert
    Come_from.insert("WaySLOG", "HeBei");
    Come_from.insert("Marisa", "U.S.");
    Come_from.insert("Mike", "HuoGuo");
    
    // find the key
    If !come_from.contains_key("elton") {
        Println!("Oh, we found {} personal, but poor Elton cat is still homeless", come_from.len());
    }
    
    / / Delete elements according to the key
    Come_from.remove("Mike");
    Println!("\nMike猫!\n");
    
    / / Use the return of get to determine whether the element exists
    Let who = ["MoGu", "Marisa"];
    For person in &who {
        Match come_from.get(person) {
            Some(location) => println!("{} from: {}", person, location),
            None => println!("{} is also homeless.", person),
        }
    }
    
    // traversal output
    Println!("\nSo, everyone?");
    For (name, location) in &come_from {
        Println!("{}From: {}", name, location);
    }
}
```

Look at the array again:
```cpp
Fn main() {
    Let mut array: [i32; 3] = [0; 3];

    Array[1] = 1;
    Array[2] = 2;

    Assert_eq!([1, 2], &array[1..]);

    // This loop prints: 0 1 2
    For x in &array {
        Println!("{} ", x);
    }
}
```

Dynamic array Vec

```c
Fn main() {
    / / Create an empty Vec
    Let v: Vec<i32> = Vec::new();
    Println!("{:?}", v);
    
    / / Use the macro to create an empty Vec
    Let v = vec![1, 2, 3, 4, 5];
    Println!("{:?}", v);
    //Create ten zeros
    Let v = vec![0; 10];
    / / Create a variable Vec, and press element 3
    Println!("{:?}", v);
    Let mut v = vec![1, 2];
    V.push(3);
    Println!("{:?}", v);
    / / Create a Vec with two elements, and pop up an element
    Let mut v = vec![1, 2];
    Let two = v.pop();
    Println!("{:?}", two);
    / / Create a variable Vec containing three elements, and index a value and modify a value
    Let mut v = vec![1, 2, 3];
    v[1] = v[1] + 5;
    Println!("{:?}", v);
    
}
```



## "small case

This project refers to the RustPrimer book, [Json Processing] (https://rustcc.gitbooks.io/rustprimer/content/action/json_data/readme.html). Introduced the use of caogo.
A small project can verify that our understanding of Rust is correct.

## ——Special chapter: Ownership, Borrowing and Life Cycle

## Chapter 4: Code Organization

Basic usage of the module

```c
Mod ccc {
    Pub fn print_ccc() {
        Println!("{}", 25);
    }
}

Fn main() {
    Use ccc::print_ccc;

    Print_ccc();
    // or
    Ccc::print_ccc();
}

```

The package crate is a larger unit.

Really we use a lot of external libraries when we are developing. External library is passed

```c
Extern crate xxx;
```

This was introduced.

Note: For the above references to take effect, you must also add `xxx="version num"` to the `dependecies` section of `Cargo.toml`.

After the introduction, it is equivalent to the introduction of a symbol `xxx`, which can be directly referenced to the item in the crate with this `xxx` as the root:

```c
Extern crate xxx;

Use xxx::yyy::zzz;
```

When introduced, it can be renamed with the `as` keyword.

```c
Extern crate xxx as foo;

Use foo::yyy::zzz;
```

## Chapter 5: Rust Highlights

## ——Special chapter: error handling


## Chapter 6: Concurrency

## Chapter 7: Macro

## Chapter 8: Testing

Rust's test features are divided into three levels according to their granularity:

Function level
2. Module level;
3. Engineering level;

In addition, Rust also supports testing of documents.

Here is a simple function level test.

```c
#[test]
Fn it_works() {
    Assert!(2>1); // do test work
}
```

Very simple, in Rust, only needed
