---
title: 1 - A beginner's guide to get started with C++;
date: 2021-03-22 03:00:00 +05:30
modified: 2021-03-22 03:00:00 +05:30
tag: cpp
description: I am new to C++, i learned it in my college 3 years back, and now i am going to learn it again as a beginner. I am also not good at C++, i understand the fundamentals, but do not worry, we will learn it as if i am a noob.
image: ""
---

[30DaysOfCpp](https://www.linkedin.com/feed/hashtag/?keywords=30daysofcpp)

<article><kbd>C++</kbd> is one of the popular languages, I have learned it in my college 3 years back, and now i am going to learn it again like a beginner. I am a Python guy, it is going to be an exciting journey.</article>

#### The Introduction

C++ is a general purpose, compiled programming language, It was designed by `Bjarne Stroustrup` in 1990s.

I know you are already aware about it, but we will get into more interesting stuff like `linker`, `pointer`, `templates` and much more in `C++`, as we move futher in this series of articles.

I am not going to bore you with repetitive stuff like `variables`, `loops` etc, of course we will study about them but not much, as every language has almost same kind of fundamentals.

#### Why C++ in 2021?

This question has already came into your mind that why should we learn this old language today in 2021, specially when we have `Python`, `Javascript`, `Ruby`, `Go` etc ?

The Answer is simple, `C++` is freaking fast, and gives you a super power as a programmer, on top of that, `C++` is still widely used in creating _Games_, _Desktop Softwares_, _Browsers_, _Operating Systems_, _Compilers_ and _Embeded Systems_.

So the answer is simple, `C++` makes you think like a real programmer, it gives you the freedom to handle almost everything in your program.

#### Is C++ the fastest language ?

The answer is yes and no.


`Yes`, because `C++` is a compiled languages and after compilation, `C++` program gets converted into the low level machine program, which makes it the fastest language.

`No`, because it depends on the programmer. In the case of other languages like `Java`, `C#` or `Python`, so much optimization has been done automatically by the compiler/interpreter on the fly, though in `C++`, if you write a bad program, it could even be slower than the equivalent of other language.


### Enough talk now, lets jump into our first C++ program.

We will setup out programming environment in the next article, for now let's have a look at the simplest `hello word` `C++` program.

```cpp
#include <iostream>

int main() {
    std::cout << "Hello World";
}
```

If you are seeing this syntax for the first time, you might be already scratching you head and thinking what the heck is this ?


No worries, I am here, let's break this program down into pieces -


```cpp
// 1st Line
#include <iostream>
```

Unlike other languages, `C++` does not come with input output services in the standard library like printing text in the console or taking user input.

For that, we have to include (import) the input output methods in our `C++` program.

First line is also called as `header` or `preprocessor`, because the moment your `C++` program compilation starts, first thing your compiler does, is, include necessary header files, and to do that, it needed the name of header files like `iostream`.

Let's jump into the next line -

```cpp
// 2nd Line
int main() {...}
```

This is our `main` function, also knows as entry point for the compiler of `C` or `C++`.

We can call it an entry point, because no matter how long your program is, `C++` always going to start the execution from `main` function, `main` is the official start of the "user specified" part of the `C++` program.

What is the meaning of `int` on the left of `main` ?

We know that in programming, every function returns something, in this case, `int` denotes that the `main` function will always return an `integer`, although here it does not matter, because we are not returning anything, `main` is a special case in `C++`.

Let's have a look at inside the `main` function -

```cpp
int main() {
    std::cout << "Hello World";
}
```

If you take a look at the first line inside `main`, it seems like pretty confusing, but it is not.

This `std::cout` shows that we are using `standard console output` to print the text on console.

This `<<` is an operator, also knows as `stream out` or `overloaded` operator. Operators are nothing, just a function. It simply `passes` the string (text) into `cout`.

You can consider this whole line as given below -
```cpp
std::cout << "Hello World";

// can be understood as

std::cout.print("Hello World");
```

Let's have a look at the whole program again -

```cpp
// Header or Preprocessor
#include <iostream>

// Entry point or main function
int main() {

    // Standard console output and next line
    std::cout << "Hello World";
}
```


So this is how we have understood our first `C++` program.

#### Conclusion -

I can totally understand your curiosity, we will setup our system environment to write and execute the program locally in next article.


##### There is so much to learn in the upcoming articles, stick with me, you can follow me on [LinkedIn](https://www.linkedin.com/in/hamhaingaurav/) from [here](https://www.linkedin.com/in/hamhaingaurav/) for more updates.

##### Until then you can watch some intersting C++ videos and read a great article from the links given below, enjoy C++.


##### Resources

- [The Cherno - Youtube](https://www.youtube.com/playlist?list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb)
- [The C++ Programming Language - Freecodecamp](https://www.freecodecamp.org/news/the-c-plus-plus-programming-language/)
