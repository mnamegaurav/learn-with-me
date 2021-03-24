---
title: 2 - How does C++ compilation works ?
date: 2021-03-24 03:00:00 +05:30
modified: 2021-03-24 03:00:00 +05:30
tag: cpp
description: In this article, we are going to setup our programming environment for C++, and we will also take a look at, how C++ compiler works.
image: ""
---

[#30DaysOfCpp](https://www.linkedin.com/feed/hashtag/?keywords=30daysofcpp)


### The Introduction -
`C++` is a beauty, and its compilation process is what makes it more powerful than other languages. Before we jump into the core programming fundamentals of `C++`, like **_variables_**, **_loops_** etc, we will first try to understand, how the compilation happens in `C++` at an **_abstract_** level.


### Setting up the environment for C++ in VSCode -
We are simply going to use **VSCode** with `g++`(for Unix/Linux) or `MinGW`(on Windows) to setup the environment.

Follow these steps and you will be ready to run your `C++` program in your local system.

1. Download [VSCode](https://code.visualstudio.com/download) from [here](https://code.visualstudio.com/download).
2. If you are on **Unix/Linux**, Your system already came with `g++` compiler. You can check it by opening your terminal and running this command.
    ```bash
    $ g++ --version
    ```
3. If you are on **Windows**, You can follow this guide to setup the `C++` environment, from official **VSCode** documentation.
    [https://code.visualstudio.com/docs/languages/cpp](https://code.visualstudio.com/docs/languages/cpp)

Now you are ready to go ahead into the **_compilation_** process of `C++`.


### C++ Compilation -

When we say **_compilation_**, we generally refers to the whole process of generating an executable file from a `.cpp` file.

But in `C++` compilation process consists of three major steps:
- **Preprocessing**
- **Compilation(Translation)**
- **Linking**

<figure>
<img src="http://www.cplusplus.com/articles/2v07M4Gy/Selection_101.png" alt="C++ Compilation Overview">
<figcaption>C++ Compilation Overview.</figcaption>
</figure>

We will take a look at all of them, but before that, let's relook at the program we saw in the first [article]({{site.url}}/getting-started-with-cpp/). 

```cpp
// Preprocessor
#include <iostream>

// User defined part
int main() {
    std::cout << "Hello World";
}
```

Open your `VSCode` editor and create a new file with this name `main.cpp`, and paste the above program.

Now, tight your seat belts, because we are going on a ride of `C++` compilation.

##### The Preprocessor:

**_Pre-processor_**, is the first thing that happens in the **_compilation_** process.

If you take a look at above **program**, first line of that program `#include ...` is called a **preprocessor directive**.

In this program, we are using this **_preprocessor_** to include the `std` (standard) input output functions from a well known `C++` library named `iostream`.

```cpp
#include <iostream>
```

**_Preprocessor_** job is very simple, it just _copies_ whatever is inside the file `iostream`, and _paste_ it into our `.cpp` file.

After doing the easy job of **_preprocessing_**, `C++` compiler generates a **temporary** file, which consists of all the code from _included_ libraries, and this **temporary** file will be passed to a translator for further _compilation_.

Sounds easy, `#include ...` is just one directive, there is also `#define ...`, `#if ...` etc for different _usecases_.

##### The Compiler (Translator):

After the `C++` **compiler** has included all the `header` files and expanded out all the `#include` statements, Now this **_translator_** comes into the play.

It will take all the generated temporary files(in this case only one) one at a time, and create an `object` file for each `temporary` file.

You can generate an *object* file by yourself, using this command in your `VSCode` terminal.

```bash
$ g++ -c main.cpp
```

`Object` files are just the binary version of your program with the extension `.o` or `.obj`, though you can not directly execute it, there is one process left which will create an `executable` file out of your object files.

##### The Linker:

As its name is suggesting you, The job of the **_linker_** is to link together a bunch of object files (`.o` files) into a binary **executable**.

The **_linker_** takes the _object_ files created by the **_compiler_** (or **translator**) and links them together, along with library code and a runtime files, to form a complete, executable program that is stored in a **single** file.

To run the **linker**, or generate one single executable file out of the object files, you have to run this command.

```bash
$ g++ main.o -o main
```

Now the _compilation_ process is done, If you are on _windows_, you can run this file by directly opening it.

On _Linux/MacOS_ you can run this file from command line, using this command.

```bash
$ ./main
```

Now we are done with the whole `C++` compilation process.

**Note: Generally when you use an IDE for your C++ project, you don't have to run translator, or linker by yourself, everything will be done for you by the IDE.**

To wrap it up the whole process, take a look at this image.

<figure>
<img src="https://icarus.cs.weber.edu/~dab/cs1410/textbook/1.Basics/images/compiler_system.png" alt="C++ Compilation Process">
<figcaption>C++ Compilation Process.</figcaption>
</figure>

### Conclusion -

This article could be a bit overwhelming, but trust me, this is all worth it. When we will get more deep into `C++`, you are going to be thanking me. Hope you have got to learn something from me in this article, do not forget to share your `C++` journey using this hastag [#30DaysOfCpp](https://www.linkedin.com/feed/hashtag/?keywords=30daysofcpp) on linkedin.


##### There is so much to learn in the upcoming articles, stick with me, you can follow me on [LinkedIn](https://www.linkedin.com/in/hamhaingaurav/) from [here](https://www.linkedin.com/in/hamhaingaurav/) for more updates.

##### Until then you can watch some intersting C++ videos and read a great article from the links given below, enjoy C++.


### Resources

- [http://courses.cms.caltech.edu/cs11/material/cpp/mike/misc/compiling_c++.html](http://courses.cms.caltech.edu/cs11/material/cpp/mike/misc/compiling_c++.html)
- [https://icarus.cs.weber.edu/~dab/cs1410/textbook/1.Basics/compiler_op.html](https://icarus.cs.weber.edu/~dab/cs1410/textbook/1.Basics/compiler_op.html)
- [StackOverflow](https://stackoverflow.com/a/6264256)
- [The Cherno - Youtube](https://www.youtube.com/playlist?list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb)
