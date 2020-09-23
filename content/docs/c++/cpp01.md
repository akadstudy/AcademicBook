---
title: First C++ Application
linktitle: First C++ Application
type: book
date: "2019-05-05T00:00:00+01:00"
# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 1
---

# Overview

This chapter equips you with the fundamental tools and techniques required to get started building basic C++ applications. We'll start by breaking a C++ application into its core components, identifying each by their role(s). We'll then take a look at the core language that defines C++, including pre-processor directives—statements that let us perform actions before our code is compiled. Finally, we'll look at how we get information in and out of our applications (I/O) before putting this all together in a final exercise in which you will write and run your own C++ application in an online compiler.

## Introduction

As the world becomes smarter, so do our devices. Everything from watches to our refrigerators now have the capacity to run code, a large portion of which is C++. Between 1972 and 1973 Dennis Richie authored the C programming language while working at Bell Labs. While great for efficiency, thanks to features such as low-level memory access, C is a procedural language and so does not provide object-orientated features. In response to this, Bjarne Stroustup, also while working at Bell Labs, began working on "C with classes" in 1979. In 1983, the language was renamed C++, and it saw its first commercial release two years later in 1985. Since then, it has gone through many standardizations, the last in December 2017, and continues to be governed by the International Organization for Standardization.

Utilized in everything from operating systems to cutting-edge 3D game engines, C++ is the backbone of countless systems and industries, not least because of its high-performance capabilities, flexibility, and portability. C++ puts you close to the hardware, so it is often the tool of choice for performance-critical applications.

The goal of this course is to demystify the C++ programming language, and to get you writing quality code as quickly as possible through a very pragmatic approach. While theory is certainly required, and will be covered where necessary, we'll mainly be focusing on practical application—learning by tackling real-world exercises and activities.

To start our journey, we looked at a brief history of the language. While this alone won't make you a better programmer, it's always good to have context for what we're doing and why. By learning the origins of the language and how it's used in industry, we will set ourselves up with an informed starting point for the journey ahead.

We're then going to jump right into dissecting a basic C++ application. By breaking an application down into its constituent parts, we can gain an understanding of the main pieces that it comprises. We'll then expand on this basic understanding by looking at each part in more detail throughout the rest of this introductory chapter.

When we've concluded this chapter, we'll not only have an understanding of the origin of the language; we'll also be familiar with the different core parts of an application. We'll be able to look at an example C++ application with a sense of meaning and understanding. We'll then use this basic understanding to springboard into the next chapter, where we'll look deeper into the language at specific features and functionality.

## Advantages of C++

Before we dive into the structure of a C++ program, let's have a look at a few key benefits of the language:

- **Performance**: By putting the programmer close to the hardware, C++ allows us to write very efficient programs. Along with low-level memory access, the abstraction between code and what the machine will do is smaller than in most other languages, meaning you can manipulate the system better.

- **Portability**: C++ can be cross-compiled to a wide array of platforms, and runs on everything from watches to televisions. If you're writing an application or library for more than one platform, C++ shines.

- **General purpose**: C++ is a general-purpose programming language, and is used in everything from video games to enterprise. With a rich feature set spanning everything from direct memory management to classes and other Object-Oriented Programming (OOP) principles, you can make C++ work for you.

- **Large libraries**: Since the language is used in so many applications, there's an abundance of libraries to choose from. With hundreds of open source repositories, the wealth of information (and the support systems that come with it) is vast.

C++ is a double-edged sword, however, and as the famous saying goes, *"With great power comes great responsibility"*. C++ gives you enough room to do great things, but also to get yourself into trouble if used incorrectly. Bjarne himself once said of the language, "C makes it easy to shoot yourself in the foot; C++ makes it harder, but when you do it blows your whole leg off." That's not to say by any means that C++ should be avoided, just that it should be used deliberately and with consideration—something the following chapter will impart.

## Anatomy of a C++ Application

With a brief understanding of the history of the language, we're going to start our journey by delving into a basic C++ program to see what we're working with. There's no more fitting a start than Hello World!. This famous program prints the words Hello World! to the console, and has served as the starting point for scores of programmers before you. While basic, it contains all the key components of a C++ application, so will prove a great example for us to de-construct and learn from.

Let's start by taking a look at the program in its entirety:

```c++
// Hello world example.
#include <iostream>

int main()

{
    std::cout << "Hello World!";
    return 0;
}
```

Consisting of just seven lines of code, this small program contains everything we need to look at the basic anatomy of a C++ program. We're going to cover each aspect of this program in more detail over the coming chapters, so don't worry if not everything makes perfect sense as we break this program down. The aim here is simply to familiarize ourselves with some core concepts before covering them in more detail as we progress.

Starting from the top, we have a **preprocessor directive**:

`#include <iostream>`

Preprocessor directives are statements that allow us to perform certain operations before the program is built. The **include** directive is a very common directive that you'll see in most C++ files, and it means "copy here." So, in this case, we're going to copy the contents of the **iostream** header file into our application, and in doing so, allow ourselves to use input/output functionality it provides.

Next, we have our entry point, **main()**:

`int main()`

The main() function is where your C++ application will kick-off. All applications will have this function defined and it marks the start of our application—the first code that will be run. This is typically your outer-most loop because as soon as the code in this function is complete, your application will close.

Next, we have an IO statement that will output some text to the console:

`std::cout << "Hello World!";`

Because we have included the **iostream** header at the start of our application, we have access to various input and output functionality. In this case, **std::cout. cout** allows us to send text to the console, so when we run our application, we see that the text **"Hello World!"** is printed. We'll cover data types in more detail in the coming chapters.

Finally, we have a **return** statement:

`return 0;`

This signals that we're done in the current function. The value that you return will depend on the function, but in this case, we return **0** to denote that the application ran without error. Since this is the only function in our application, it will end as soon as we return.

And that's our first C++ application; there's not too much to it. From here, the sky is the limit, and we can build applications that are as big and complex as we like, but the fundamentals covered here will stay the same throughout.

Seeing this application typed out is one thing, but let's get it running in our first exercise.

## Compiling Our First Application

In this exercise, we are going to compile and run our first C++ application. We're going to be using an online compiler throughout the course (and the reasons for doing so will be explained after this exercise) but for now, let's get that compiler up and running. Perform the following steps to complete the exercise:

> **Note:** The code file for this exercise can be found [here]([Link](https://github.com/PacktWorkshops/The-Cpp-Workshop/blob/master/Chapter01/Exercise01/Exercise01.cpp)).

1. Head [cpp.sh](http://cpp.sh/) and take a look around. This is the compiler that we'll be using. Once you go to the address, you should observe the following window:

**Options**: This allows us to change various compilation settings. We won't be touching this.
**Compilation**: This shows us the status of our program. If there are any compilation issues, they'll be shown here so we can address them.
**Execution**: This window is our console, allowing us to interact with the application. We'll input our values here and view the output of the application.
For our first program, we'll run the "**Hello World!**" application we deconstructed in the preceding section.

2. Type the following code into the code window, replacing all the content that's already there, and then hit **Run**:

```c++
//Hello world example.
#include <iostream>

int main()
{
    std::cout <<"Hello World!";
    return 0;
}
```

As you can see, the console now contains the text **Hello World!**, meaning our program ran without issue:

Try changing the text to something unique and run the program again.

> Note: Here is a partial list of online C++ compilers you can use while working on the exercises. If the one you are using becomes sluggish, or you can't find it at all, try another. Online compilers are useful because they reduce the amount of stuff you have to learn to almost nothing beyond the programming language.

- **Tutorialspoint C++ compiler**: This website allows you to compile a C++ program contained in a single file. It prints error messages from the operating system. You can find it [here](https://www.tutorialspoint.com/compile_cpp_online.php).
- **cpp.sh**: This website allows you to pick a C++ language version and warning level, and compile a single file. However, it does not print error messages from the operating system. You can find it [here](http://cpp.sh/).
- **godbolt compiler explorer**: This website allows you to compile a single file on many different compilers and shows the output assembly language; its UI is a little subtle for some tastes. It prints error messages from the operating system. You can find it [here](https://godbolt.org/).
- **coliru**: This website allows you to compile a single file. It prints error messages from the operating system. You can find it [here](http://coliru.stacked-crooked.com/).
- **repl.it**: This website allows you to compile multiple files. You can find it [here](https://repl.it/languages/cpp).
- **Rextester**: This website lets you compile a single file using Microsoft Visual C++. You can find it [here](https://rextester.com/).

## C++ Build Pipeline

Before we go any further, let's take a moment to discuss the build pipeline. This is the process that turns the code that we write into an executable that our machines are capable of running. When we write our C++ code, we're writing a highly abstracted set of instructions. Our machines don't natively read C++ as we do, and likewise, they're unable to run our C++ files as we write them. They first have to be compiled into an executable. This process consists of a number of discrete steps and transforms our code into a more machine-friendly format along the way:

- **Preprocessor**: As the name implies, it runs through our code before it's compiled, resolving any preprocessor directives that we may have used. These include things such as **include** statements, which we saw previously, and others such as macros and defines that we'll look at later in this lesson. Our files are still human-readable at this point. Think of the preprocessor as a useful editor that will run through your code, doing all the little jobs you've marked, preparing our code for the next step—the compiler.
- **Compilation**: The compiler takes our human-readable files and converts them into a format that the computer can work with—that is, binary. These are stored in object files that end with **.o** or **.obj**, depending on the platform. Consider the small **Hello World !** application we dissected earlier. All that code lives in a single file, **main.cpp**. If we were to pass that to a compiler, we would get back **main.o**; an object file containing the binary version of our source code that the machine can run. This isn't quite ready to run yet, and you can't directly execute an object file. Before we can execute our application, we need to look at the final step of the pipeline—the linker.
- **Linker**: The linker is the last step in producing our executable. Once the compiler has turned our source code into binary objects, the linker comes through and links them all together, putting together our final executable.
- The aforementioned steps have been visualized in the following process flow diagram:



These three steps are what every C++ application goes through, be it a single-file program such as the **"Hello World!"** program we've already discussed, or a multi-thousand-file application that you might see in real-world applications; these fundamental steps remain the same.

Different operating systems have different toolsets that perform these actions, and covering them all would not only take focus away from writing C++ itself, but potentially create different experiences, depending on the setup, especially because they're always changing. That's why in this course we'll be using an online compiler. Not only can we jump straight into writing code, but we can be sure that everyone will have the same results.

This overview of these processes has hopefully provided a solid overview of the fundamentals, so that when you do look to compile your applications in the future, the process will be familiar and you'll understand what's going on behind the scenes.

# C++ Keywords

**Keywords** are words that are reserved by C++. Thus, we cannot use them in our applications for anything other than their intended purposes. For example, a common keyword is **if**, so you would not be able to define a variable or function of that name. It's these keywords that structure the C++ language, and it's through their use that we instruct our program on what it should be doing.

There are many keywords defined in the language, and covering them all at this early stage is not necessary. Instead, let's take a look at the keywords that we'll encounter over the coming chapters.

Some of these words define basic types, (**bool, char, int**, and so on), some of them are statements to define program flow (**if, else, switch**, and so on), and others define objects and scope (**class, struct, namespace**, and so on).

We'll be using these throughout the course, but for now we just need to know that these words are reserved by C++. You'll be able to tell because most modern text editors will highlight these words thereby making them stand out. Let's take a look at how keywords are distinguished in our code editor. Observe the following program:

```C++
// Keywords example.
#include <iostream>
#include <string>

int main()
{
    // Data type keywords.
    int myInt = 1;
    double myDouble = 1.5;
    char myChar = 'c';
    bool myBool = true;

    // Program flow keywords.
    if (myBool)
    {
        std::cout << "true";
    }
    else
    {
        std::cout << "false";
    }

    struct myStruct
    {
        int myInt = 1;
    };
}
```

On the compiler window, the preceding code would appear as follows:


We can see that the keywords in this program are given special presentation in the editor, usually a different color, to denote their status. This will differ between IDEs.

> **Note**: IDE stands for Integrated Development Environment and is the software that we use to develop our applications. Example IDEs include Visual Studio and CLion.

## Keyword Example

Running through each keyword individually isn't necessary. We'll cover them as we go, but we can quickly take a look at some common keyword groups and what they do.

Type keywords denote the basic variable types provided by C++. These include **int**, **bool, char, double**, and **float**:

```C++
int myInt = 1;
char myChar = 'a';
bool myBool = true;
double myDouble = 1.5;
float myFloat = 1.5f;
```

Program flow keywords allow us to structure the logic of the application. These include **if, else, then**, and **switch**, as shown in the following snippet:

```C++
if (expression)
{
  // do this
}
else
{
  // do this instead.
}
```

Access modifiers determine what other classes and components can and can't see our C++ variables and functions. When building classes (something we'll look at shortly) we have three to choose from: **public, protected**, and **private**. The correct use of these modifiers plays a big part in building robust systems, ensuring our data and functionality isn't open to abuse or dangerous misuse. Here is an example:

```C++
class MyClass()
{
    public:
        int var1; // Accessible to the class, everything that can see MyClass.
    protected:
        int var2; // Accessible to the class, and any child classes.
    private:
        int var3; // Accessible to the class only.
}
```

Modifier types change the properties of our variables. These include **const, static, signed**, and **unsigned**. By putting these in front of our variables and functions, we can change the way they behave in our application, as shown in the following example:

```C++
unsigned int var1 = 1; // Unsigned means it can only be positive.
signed int var2 = -1; // Signed can be both positive or negative.
const std::string var3 = "Hello World"; // Const means the value cannot be modified 
static char var4 = 'c'; // Static means the value is shared between all instances of a given class.
```

# Preprocessor Directives

We've come across this term a few times now, so let's look at what it means. A preprocessor directive is a statement that runs before our code is compiled. This is incredibly useful for a range of different things, from header files to selective code compilation.

## Include

One of the most common directives, **#include**, we've already looked at; it means "*copy here.*" When the preprocess runs, it will literally copy and paste the contents of the included file in its place. This means that any functions, variables, classes, and so on defined in that header are now also accessible by the class containing the **include** directive.

There are two variations you'll see with this directive:

```C++
// Include example.
// Version 1 - Generally for system files.
#include <headerfile>

// Version 2 - Generally for programmer files.
#include "headerfile"
```

In **Version 1**, you're directing the preprocessor to look for the file using pre-defined search paths. This is typically used for system headers, and these paths might be set by your IDE, for example; they're implementation-defined.

In **Version 2**, you're directing the preprocessor to start its search locally where the file itself sits. This is generally used to include your own project headers. If this search fails, it will then resort to using the same paths as **Version 1**.

## Macros

The **#define/#undef** directives allow us to define macros in our programs. A macro works similar to the **#include** statement in that it replaces content. You define a name, follow it with either some data or functionality, and then whenever you want to use that code you can refer to it by its defined name instead. When the pre-compiler runs, it will simply replace the instances of the macro name with this defined content.

A macro is defined as follows:

`#define name content`

With this in place, any instance of **name** in the preceding code will be directly replaced with **content**. Let's take this simple example of defining a word:

```C++
// Macro example 1 - Defining a value.
#include <iostream>
#include <string>

#define HELLO_WORLD "Hello World!"
int main()
{
    std::cout << HELLO_WORLD;
}
```

With our macro in place, our output line is the direct equivalent of the following:

`std::cout << "Hello World!";`

We can see this if we run this code in the online compiler. As you can see, we get the output **Hello World!** Anywhere we want to use that string, we can use the macro instead.

As well as defining single values, we can also define functionality as shown in the following snippet:

```C++
// Macro example 2 - Defining functionality
#include <iostream>
#define MULTIPLY(a,b) (a * b)

int main()
{
    std::cout << MULTIPLY(3, 4);
}
```

> **Note**: A significant benefit of defining functionality through macros is speed, as it reduces the overhead of function calls. There's a better way to achieve this, however, through the use of inline functions.

Once defined, a macro can be undefined using the **#undef** directive. This will remove the value/functionality assigned to the macro. If this macro is then called anywhere, an error will occur as it no longer holds a valid value.

We can see this using our first example. Let's say we make two calls to **std::cout** using the macro, but in between them we undefine the macro:

```C++
// Macro example 3 – Undefined macro.
#include <iostream>
#include <string>
#define HELLO_WORLD "Hello World!"

int main()
{
    std::cout << HELLO_WORLD;
    #undef HELLO_WORLD
    std::cout << HELLO_WORLD;
}
```

As we can see, the first call remains fine. At the point the compiler hits that line, **HELLO_WORLD** is still defined. When we hit the second call, however, **HELLO_WORLD** has been undefined, so the compiler throws an error. An example of where macros such as this might be used is with debug behavior. You could define a macro, **DEBUG**, equal to **1**, and use this to produce debug code in your application where needed, and **#undef** it where not.

It's critical that macros are defined when we go to use them, so let's look at how we can ensure that's the case.

## Conditional Compilation

We've just seen that if we try to use a macro that isn't defined, the compiler will throw an error. Thankfully, we have the **#ifdef/#endif** directives to help us guard against this by letting us check whether a given value is currently defined.

If we take the last example where we were getting a compiler error but safeguard against this by using these new statements, we can satisfy the compiler, as shown in the following code:

```C++
// Macro example 4 – Ifdef macro.
#include <iostream>
#include <string>
#define HELLO_WORLD "Hello World!"

int main()
{
    #ifdef HELLO_WORLD
          std::cout << HELLO_WORLD;
    #endif
    #undef HELLO_WORLD
    #ifdef HELLO_WORLD
          std::cout << HELLO_WORLD;
    #endif
}
```

If we modify our program and run the preceding code, we can see that the compiler is now satisfied and will run the program correctly, skipping the second output altogether:

What happens here is the code inside the **#ifdef/else** directives isn't compiled into our final program if the macro specified isn't defined at that time. We also have the **#ifndef** directive available, which checks that the value is not defined. This is used in the same way as **#ifdef**, but obviously returns the opposite value; **true** when the value is not defined, **false** if it is.

As you can imagine, we can use these for lots of things, and there are other directives that allow us to do this with any **constant** expression, not just checking whether something is defined. These are **#if, #else**, and **#elif**.

> **Note**: A constant expression is just an expression where its value can be determined at compile time (before the program is run).

The following program shows an example of how these preprocessor directives can be used to manipulate what code gets compiled into our program:

```C++
// Conditional compilation example.
#include <iostream>
#define LEVEL 3

int main()
{
    #if LEVEL == 0
        #define SCORE 0
    #else
    #if LEVEL == 1
        #define SCORE 15
    #endif
    #endif

    #if LEVEL == 2
        #define SCORE 30
    #elif LEVEL == 3
        #define SCORE 45
    #endif
 
    #ifdef SCORE
        std::cout << SCORE;
    #endif
}
```

Here, we use the value of our **LEVEL** macro to determine what value we give our **SCORE** macro. Let's copy this code into the compiler and see how it behaves. Change the value of **LEVEL** and see how that affects the output.

> **Note**: If we use **#if** and **#else**, each need their own matching call to **#endif**. This is not the case with **#elif**.

As we can see, by changing the value of **LEVEL**, we can change what code actually ends up being compiled into our application. One common use of this in practice is to compile platform-specific versions of things.

Let's say you've got a function that needs to do slightly different things between OSX and Windows. One way to solve this is by wrapping each function definition inside a platform define so the correct function gets compiled for each platform. Here is an example of this functionality:

> **Note**: There is no equivalent of **#elif** when using **#ifdef**. Instead, we have to just chain **#ifdef/#endif** statements.

Now that we have a basic understanding of preprocessor directives, we will apply some of the concepts we've learned by writing a program that defines values through them.

# Defining Values with Preprocessor Directives

In this exercise, we're going to build a small application that will give a test score a letter grade. We'll define score thresholds in macros and use them to assign grades:

1. We'll start by including our iostream and string headers, and defining our grade macros:

```C++
// Preprocessor directives activity.
#include <iostream>
#include <string>

#define GRADE_C_THRESHOLD 25
#define GRADE_B_THRESHOLD 50
#define GRADE_A_THRESHOLD 75
```

Define these thresholds as you see fit.

2. Allow the user of the program to input their test score by typing in the following code:

```C++
int main()
{
    int value = 0;
    
    std::cout << "Please enter test score (0 - 100): ";
    std:: cin >> value;
```

Don't worry that we've not yet covered the IO statements that we're about to use. We'll be covering them next.

3. Output the grade the user got based on their test score.

This is where we use the values we defined earlier. By defining these in macros, we can easily update them at a later date. This is nice as it allows us to modify the thresholds in a single location. Everywhere those macros are used will be updated as a result. Use the following code to do this:

```C++
if (value < GRADE_C_THRESHOLD)
    {
        std::cout << "Fail";
    }
else if (value < GRADE_B_THRESHOLD)
    {
        std::cout << "Pass: Grade C";
    }
else if (value < GRADE_A_THRESHOLD)
    {
        std::cout << "Pass: Grade B";
    }
else
    {
        std::cout << "Pass: Grade A";
    }
}
```

4. The complete code looks like this:

```C++
// Preprocessor directives activity.
#include <iostream>
#include <string>
#define GRADE_C_THRESHOLD 25
#define GRADE_B_THRESHOLD 50
#define GRADE_A_THRESHOLD 75

int main()
{
    int value = 0;
    std::cout << "Please enter test score (0 - 100): ";
    std::cin >> value;
    if (value < GRADE_C_THRESHOLD)
    {
        std::cout << "Fail";
    }
    else if (value < GRADE_B_THRESHOLD)
    {
        std::cout << "Pass: Grade C";
    }
    else if (value < GRADE_A_THRESHOLD)
    {
        std::cout << "Pass: Grade B";
    }
    else
    {
        std::cout << "Pass: Grade A";
    }
}
```

5. Now let's run our program. If a user inputs a score between 1-100, we can provide them with a letter grade. For an input of 50, you will obtain the following output: 

# Basic I/O Statements

I/O stands for **input/output** and is how we get information in and out of our programs. This can take many forms, from inputting text via a keyboard, to clicking buttons with our mouse, to loading a file, and so on. In this chapter, and in general moving forward, we're going to be sticking with text input/output. For this, we'll use the **iostream** header.

Throughout this section, we'll be reading directly from input with little to no data validation. In a working application, however, input would be strictly validated to ensure it's of the correct format, among other things. Our lack of this is strictly for example purposes only.

The **iostream** header contains everything we need to interface with our applications via the keyboard, allowing us to get data in and out of our application. This is accomplished through the **std::cin** and **std::cout** objects.

> **Note**: The **std::** prefix here denotes a namespace. This will be looked at in more depth later in the course, but for now we can just know they're used to group code.

There's a couple of ways we can read data from our keyboard. First, we can use **std::cin** with the extraction operator:

`std::cin >> myVar`

This will put your input into the **myVar** variable and works for both string and integer types.

Observe the following code that has an **std::cin** object included:

```C++
// Input example.
#include <iostream>
#include <string>

int main()
{
    std::string name;
    int age;

    std::cout << "Please enter your name: ";
    std::cin >> name;
    std::cout << "Please enter you age: ";
    std::cin >> age;

    std::cout << name << std::endl;
    std::cout << age;
}
```

If we run this code in our compiler, we can see that we can enter our details and have them printed back to us:

If you tried to enter a name with a space in, you'll have run into an issue where only the first name was captured. This gives us more insight into how **std::cin** is working; namely that it will stop capturing input when it encounters a terminating character (space, tab, or new line). We can see now why only our first name was captured properly.

It's also useful to know that extractions, the **>>** operator, can be chained. This means that the following two examples of code are equivalent:

**Example 1:**

```C++
std::cin >> myVar1;
std::cin >> myVar2;
```

**Example 2:**

```C++
std::cin >> myVar1 >> myVar2;
```

To avoid our strings being cut off when a terminating character, such as space, is encountered, we can pull the entirety of the users input into a single variable by using the **getline** function. Let's update our code using this function to get the user's name:

```C++
std::cout << "Please enter your name: ";
getline(std::cin, name);
```

If we run the code again, we can now see that we're able to use spaces in our name and **getline()** will capture the whole input. Using **getline()** is nicer because it means we don't have to worry about the line issues that can come with using **cin** extraction directly.

When we use **getline()**, we read our user's input into a string, but that doesn't mean we can't use it to read integer values. To convert a string value into its integer equivalent, we have the **std::stoi** function. For example, the string **"1"** would be returned as **int** **1**. Combining it with **getline()** is a good way to parse integer inputs:

```C++
std::string inputString = "";
int inputInt = 0;

getline(std::cin, inputString);
inputInt = std::stoi(inputString);
```

Regardless of which method we use, we need to ensure that we handle strings and numerical values correctly. For example, perhaps we have some code that expects the user to input a number:

```C++
int number;

std::cout << "Please enter a number between 1-10: ";
std::cin >> number;
```

If the user inputs a string here, maybe they type **five** instead of inputting the number, the program won't crash, but our **number** variable won't be assigned a value. This is something we need to be aware of when getting input from our users. We need to ensure it's of the correct format before we try to use it in our programs.

Outputting text is as simple as making a call to **std::cout**, using the insertion operator, **<<**, to pass our data. This will accept both string and numerical values, so both the following code snippets will work as intended:

```C++
std::cout << "Hello World";
std::cout << 1;
```

As with the extraction operation, the insertion operator can be chained to build more complex outputs:

`std::cout << "Your age is " << age;`

Finally, when outputting text there are times where we want to either start a new line or insert a blank one. For this, we have two options, **\n** and **std::endl**. Both of these will end the current line and move to the next. Given this, the following code snippets give the same output:

```C++
std::cout << "Hello\nWorld\n!";
std::cout << "Hello" << std::endl << "World" << std::endl << "!"<< std::endl;
```

As mentioned earlier, there are other types of input and output associated with applications; however, most of the time, IO will be facilitated through some form of UI. For our purposes, these two basic objects, **std::cin/std::cout**, will suffice.

We will apply our knowledge of the **getline()** method and the **std::cin**, **std:cout**, and **std::endl** objects in the next exercise.

# Reading User Details

In this exercise, we're going to write an application that will allow you to input your full name and age. We'll then print this information out, formatting it into complete sentences. Perform the following steps to complete the exercise:

1. Define the **firstName**, **lastName**, and **age** variables, which will hold our user's inputs, as shown in the following snippet:

```C++
// IO Exercise.
#include <iostream>
#include <string>

int main()
{  
  std::string firstName;
  std::string lastName;
  int age;
```

> **Note**: We're going to be covering data types in their own chapter later, so don't worry if the exact nature of these variable types isn't clear at this point.

2. Type in the following code, which will request the user to input their first name:

```C++
std::cout << "Please enter your first name(s): ";
getline(std::cin, firstName);
```

3. We'll do the same for surnames, again using **getline()** using the following snippet:

```C++
std::cout << "Please enter your surname: ";
getline(std::cin, lastName);
```

For our final input, we'll allow the users to input their age. For this, we can use **cin** directly because it's our last input, so we need not worry about terminating lines characters, and we're expecting a single numerical value.

4. Type the following code to have the user input their age:

```C++
std::cout << "Please enter your age: ";
std::cin >> age;
```

> **Note**: Again, it's only because we're writing simple example programs that we're trusting our users to input the correct data and not doing any validation. In a production environment, all user input data would be strictly validated before use.

5. Finally, we'll present this information back to the user, making use of chained insertions to format complete strings and sentences using the following code:

```C++
std::cout << std::endl;
std::cout << "Welcome " << firstName << " " << lastName << std::endl;
std::cout << "You are " << age << " years old." << std::endl;
```

6. The complete code looks like this:

```C++
// IO Exercise. 
#include <iostream> 
#include <string> 

int main() 
{ 
    std::string firstName; 
    std::string lastName; 
    int age; 
    std::cout << "Please enter your first name(s): "; 
    getline(std::cin, firstName); 
    std::cout << "Please enter your surname: "; 
    getline(std::cin, lastName); 
    std::cout << "Please enter your age: "; 
    std::cin >> age; 
    std::cout << std::endl; 
    std::cout << "Welcome " << firstName << " " << lastName << std::endl; 
    std::cout << "You are " << age << " years old." << std::endl; 
} 
```

7. Run our application now and test it with some data.

Thus, with the completion of this exercise, we have put together, through basic IO, a little program that allows users to register their details against something. We will now move on the next topic—functions.

# Functions

**Functions** in C++ encapsulate our code into logical units of functionality. We can then call these functions instead of having duplicate code throughout our project. For example, consider a small application that asks users for their name, greets them, and then stores that name in a list, as shown in the following snippet:

```C++
// Get name.
std::cout << "Please enter your name: " << "\n";
getline(std::cin, name);
std::cout << "Welcome " << name << ".\n";
names.push_back(name);
```

This is code that we will probably want to call multiple times during our application's lifetime, so it is a good candidate to be put into a function. The benefit in doing so is that it reduces duplicate code through our applications, giving us a single place where we can maintain the code and fix any bugs. If it was duplicated throughout the code base, anytime you want to upgrade it or fix something, you'd have to find all instances and do it to each.

A function is split into two parts: a **declaration** and a **definition**. In a function declaration, you're declaring the most basic information about how that function will work–namely–the type of value the function will return, the name of the function, and any parameters. The actual logic of the function's behavior is then dictated by the definition. Let's break a function declaration down.

A function is declared as follows:

`return_type function_name(parameters);`

- **return_type**: This is the type of value that you will return from the function. You can also return **void**, a C++ keyword, if you don't want to return anything. For example, if you had a function that added two numbers together, the return type might be **integer**.
- **function_name**: This is the name of the function and is how you'll reference it in code.
- **parameters**: These are an optional set of values that you pass into a function. Again, taking the example of adding two numbers, you would have two **integer** parameters: your first and second numbers.

This declaration usually lives in a header file (**.h**) along with other functions declarations, and they're then defined in a **.cpp** file. *This is why we see the #include directive so often*. We declare our objects' functionality in header files, then actually define how they work in **.cpp** files. We usually separate these into individual files because it allows us to hide implementation details. It's often the case that header files are made public, so we can see an object's functionality and use it, but the exact implementation of that function is kept private.

> **Note**: We're not going to worry about this for now. Since we're working in a single file, we're just going to define and declare functions at the same time, not separately.

Taking this back to our previous example, we can take the snippet of code that allows a user to input their name, and define it in a function as shown in the following snippet:

```C++
void GetNextName()
{
    std::string name;
    std::cout << "Please enter your name: " << "\n";
    getline(std::cin, name);
    std::cout << "Welcome " << name << ".\n";
    names.push_back(name);
}
```

Now, each time we need this functionality, we can just call this function instead. The function provides its own variable, **name**, for us to use, but note that the **names** variable is being used from the main program. This is possible as it's within scope of the function. Scope is something that will be covered in detail in a later chapter, but for now we can just observe that the **name** variable is defined inside the function, while **names** is defined outside of it.

It's easy to imagine how much tidier this is now that we don't have duplicate code, just multiple calls to the same function. This makes our code more readable, maintainable, and easier to debug. This process of restructuring our code is called refactoring. We should always aim to write code that's easy to maintain, debug, and extend, and having good structure plays a big part in this.

## Passing by Value, Passing by Reference

Function arguments are values that we pass into our function. If we think of our function as a discrete bit of functionality, then our parameters allow us to give it what it needs to run. There are two ways of passing parameters into functions, by value and by reference, and it's important to understand the difference.

When we pass an argument into a function by value, this means we're making a copy, and will be working with that. The easiest way to visualize this is by writing a small test application. Observe the following code:

```C++
// Pass by value-by-reference example.
#include <iostream>
#include <string>

void Modify(int a)
{
    a = a - 1;
}

int main()
{
    int a = 10;
    Modify(a);
    std::cout << a;
}
```

In this simple program, we define a number to be 10, pass it to a function that will subtract 1 from it, and then print that value. Since we started with 10 and are subtracting 1, it would be reasonable to expect the output to be 9. However, when we run the preceding snippet, we obtain the following output:

### Why Are We Outputting 10?

Because when we passed our **a** variable into our function, it was passed by value. The function made a local copy of **a**, in this case 10, and then anything it does to that value is completely separate from the original **a** value we passed in.

Passing by reference is the opposite of this and means, "Actually work on this variable; don't make a copy." Again, it's easiest to see this in action. Let's make the following amendment to our code:

`void Modify(int& a)`

A very subtle change, but what we've done here is added **&** after our **int** type in the function. This symbol means "the address of." We have chapters later in the course that will cover memory in much more detail, so we'll keep it light here, but in practical terms it means, "Don't make a copy; actually use that value."

Let's re-run the code with this change in place.

Passing by value or by reference is an important concept to understand. If you're working with big objects, passing by value can be expensive because temporary objects have to be constructed/deconstructed. This is another topic that will be covered in later chapters. For now, taking away the fact that values can be passed either by value or by reference (as we've seen here) is sufficient. We'll build on this later.

## Function Overloading

Writing functions to encapsulate our behaviors is a great step towards creating versatile and maintainable code. We can do more however; we can overload them. Overloading, in this context, means providing more than one version of the function. Let's say we define a simple function to multiply two numbers:

```C++
int Multiply(int a, int b)
{
    return a * b;
}
```

This function's arguments are of type **int**, so what happens if we wanted to multiply **float** types or **double**? In this case, they'd be converted to integers and we'd lose precision, not something we generally want. In order to solve this, we can provide another declaration of the function, with the same name, that can use those types. Our function declarations would look like this:

```C++
int Multiply(int a, int b);
float Multiply(float a, float b);
double Multiply(double a, double b);
```

What's great is we don't need to worry about calling the correct version of this function. Given we provide the correct types, the compiler will automatically call the appropriate function for us. We can see this in action with a simple test. We can create function definitions for each of these and add a unique output to each so we can tell which one's been hit.

Here is an example of how to do this:

```C++
// Function overloading example.
#include <iostream>
#include <string>

int Multiply(int a, int b)
{
    std::cout << "Called the int overload." << std::endl;
    return a * b;
}

float Multiply(float a, float b)
{
    std::cout << "Called the float overload." << std::endl;
    return a * b;
}

double Multiply(double a, double b)
{
    std::cout << "Called the double overload." << std::endl;
    return a * b;
}

int main()
{
    Multiply(3, 4);
    Multiply(4.f, 6.f);
    Multiply(5.0, 3.0);
    return 0;
}
```

In the preceding code, we have our overloaded function and three calls to it, each with a different type. When you run this application, the following output is obtained:

As we can see, the compiler knew which version of the function to call since we matched the specified parameter types in each case. A **multiply** function is a bit redundant, and certainly a simple use case of this, but demonstrates nicely how we can make our functions more useful and flexible.

Another way to achieve this flexibility is through templates. Instead of overloading a function for each individual type, with a template you create a single, highly generic version of the function that can accept any type. Templates will be covered in a later chapter.

## Default Parameters

Another way we can make our functions more flexible is with default parameters. This allows us to make some of our parameters optional, and we do so by giving them a default value in the declaration as follows:

```C++
return_type function_name(type parameter1, type parameter2 = default value);
```

This function could now be called in two ways:

`function_name(value1, value2);`

In this case, both parameter values are passed into the function as normal:

`function_name(value1);`

In this case, since the second parameter has been omitted, the default value will be used instead. Having the ability to provide default parameters allows us to make our functions more flexible in what they can do, but there's a limit to this. The point of a function is to neatly encapsulate a certain behavior, so we don't want to make it so flexible that it starts being responsible for multiple behaviors. In this case, it would be better to create a new discrete function.

Let's have a quick look at an example of this with another exercise.

# Functions

In this exercise, we're going to define and use a function that will output the larger of two numbers. This function will require a return type and two parameters. Perform the following steps to complete the exercise:

1. Declare the function, assigning its return type, name, and parameters:

```C++
#include<iostream>
int Max(int a, int b)
```

As we saw earlier, if we were purely declaring this function in a header file, we would add a semicolon to the end of that and define it elsewhere. Since that's not the case, however, we open our curly braces straight away and define our functionality.

2. Define the behavior of the function. We want to return the number that has the highest value, so the logic for this is easy, as shown in the following example:

```C++
int Max(int a, int b)
{
    if (a > b)
    {
        return a;
    }
    else
    {
        return b;
    }
}
```

3. Now all we need to do is get two numbers from our users. We've covered IO earlier in this chapter, so we should be comfortable with that:

```C++
int main()
{
    int value1 = 0;
    int value2 = 0;

    std::cout << "Please input number 1: ";
    std::cin >> value1;

    std::cout << "Please input number 2: ";
    std::cin >> value2;
```

4. Finally, we need to output the answer to the user. We've covered this before as well, but this time, instead of using a variable in our **cout** statement, we'll make a call to our new function, passing in the user's numbers:

```C++
std::cout << "The highest number is " << Max(value1, value2);
}
```

5. The complete code looks like this:

```C++
// IO Exercise.
#include <iostream>
#include <string>

int Max(int a, int b)
{
    if (a > b)
    {
        return a;
    }
    else
    {
        return b;
    }
}

int main()
{
    int value1 = 0;
    int value2 = 0;
    
    std::cout << "Please input number 1: ";
    std::cin >> value1;
    std::cout << "Please input number 2: ";
    std::cin >> value2;
    std::cout << "The highest number is " << Max(value1, value2);
}
```

6. Run this in the compiler and test it with some numbers.

# Writing Your Own C++ Application

The aim of the activity is to write a system that will ask users for their first name and age. Users will be placed into groups based on their age, and we'll use macros to define these age brackets. We'll print the user's information back to them, along with their assigned group (the name of which is also at your discretion), using functions to encapsulate any repeated functionality. Our desired outcome will be a small program that will be able to sort users into groups, as shown in the following screenshot:

Before you begin, ensure that all previous exercises have been completed because this activity will test a number of the topics that we've covered in this introductory chapter. Here are the steps to complete the activity:

1. Define your age bracket thresholds using **#defines**.
2. Define a name for each group using **#defines**.
3. Output text asking the user for their name and capture the response in a variable.
4. Output text asking the user for their age and capture the response in a variable.
5. Write a function that will accept age as a parameter and return the appropriate group name.
6. Output the user's name and the group that they have been assigned to.

