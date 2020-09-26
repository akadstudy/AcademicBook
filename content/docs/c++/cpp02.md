---
title: Control Flow
linktitle: Control Flow
type: book
date: "2019-05-05T00:00:00+01:00"
# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 2
---

## Overview

This chapter presents various tools and techniques that are used to control the flow of execution throughout applications. This includes, but is not limited to: if statements, switch statements, and various loops. We will also look at how we control the lifetime of our applications using these techniques, and how they are to be used efficiently. The chapter will end with the creation of a number guessing that that will implement various loops and conditional statements.

## Introduction

In the first chapter, we covered the absolute essentials of C++ and looked at the key components of a C++ application. We looked at how applications run, how they're built, and how we can get information in and out of them with some basic I/O. Up until this point, the applications we've built have mainly run sequentially; that is, the code we've written has been executed line by line, sequentially. While that's great for demonstration purposes, this generally isn't how real-world applications work.

In order to represent logical systems correctly, we need to be flexible in what we do and when. For example, we may only want to perform a certain action if a given statement is true or to return to an earlier piece of code again. Manipulating execution in this manner is known as control flow (or program flow), and is the topic of this chapter.

To begin with, we are going to look at the humble **if** statement, one of the most fundamental logic statements. We'll then branch out into looking at **switch** statements, a nice alternative to long chains of **if/else** statements. Next, we'll look at loops. Specifically, we'll see how we can use them to repeat code execution, and how we can make them more efficient and precise with **break** and **continue** statements.

The chapter will conclude with a fun activity in which we'll create a number-guessing game from the ground up. This will not only require the skills we learned in *Chapter 1, Your First C++ Application*, but also the program flow skills that we're about to cover. When this chapter is finished, not only will you have a solid understanding of the core logic statements and loops, but you will have also implemented them within practical exercises.

---

## if/else

One of the most basic, yet most important, control flow statements is if. This simple keyword is at the heart of all logic, allowing us to perform a given action only if a specified condition is true. By chaining these **if** statements together in creative ways, we can model any logical system.

The syntax for an **if** statement is as follows:

`if (condition) { // do stuff. }`

If the statement we use as our condition resolves to **true**, then the code within the curly braces will be executed. If the statement is **false**, then it will be skipped. Our condition can be anything that can be either true or false. This can be something simple, such as checking the value of a Boolean, or something more complex, such as the result of another operation or function.

We also have the **else** statement. This allows code to be executed **if**, and only if, a preceding if statement's condition evaluates to **false**. If the condition evaluates to true, however, and the **if** statement is thereby executed, the code within the **else** statement will not be executed. Here's an example:

```C++
if (MyBool1)
    {
        // Do something.
    }
    else
    {
        // Do something else.
    }
```

In this example, if **MyBool1** was **true**, then we'd execute the **// Do something** code but not **// Do something else**. If **MyBool1** evaluated to **false**, however, we'd execute the **// Do something else** code but not **// Do something**.

An **else** statement can also be used together with an **if** statement. With an **else/if** block in place, should the first **if** check fail, then the second will be evaluated. Here is an example:

```C++
if (MyBool1)
    {
        // Do something.
    }
    else if (MyBool2)
    {
        // Do something else.
    }
```

In this example, **MyBool1** will be checked first. If that returns **true**, then the **// Do Something** code will be executed but **// Do something else** will not. If **MyBool1** was **false**, however, **MyBool2** would then be checked, and the same rules would apply: if **MyBool2** was true, then **// Do something else** would execute. So, if **MyBool1** and **MyBool2** were both false, then neither code would be executed.

It's also possible to place **if** statements inside one another. This practice is referred to as nesting. Here's an example:

```C++
 if (MyBool1)
    {
        if (MyBool2)
        {
            // Do something
        }
    }
```

In this example, if **MyBool1** returns **true**, then the second **if** statement will be evaluated. If **MyBool2** is also **true**, then **// Do Something** will be executed; otherwise, nothing will get executed. C++ allows us to nest many levels deep. The standard suggests 256 (although this isn't enforced), but the more levels deep you go, generally, the more confusing the code. It's good practice to minimize nesting where possible.

Now, let's get some code written and see these **if / else** statements in action.

---

## Implementing if/else Statements

In this exercise, we will write a simple application that will output a certain string based on an input value. The user will input a number, and the application will use **if/else** statements to determine whether it's either above or below 10.

Follows these steps to complete the exercise:

1. Enter the **main()** function and then define a variable called **number**:

```C++
// if/else example 1.
#include <iostream>
#include <string>

int main()
{
    std::string input;
    int number;
```

2. Write code that prints the **Please enter a number**: string, gets the user input, and then assigns it to the **number** variable:

```C++
std::cout << "Please enter a number: ";
    getline (std::cin, input);
    number = std::stoi(input);
```

> **Note**: We've used the **std::stoi** function here, which we first saw in *Chapter 1, Your First C++ Application*. This function converts a string value into its integer equivalent. For example, the string **1** would be returned as **int 1**. Combining it with **getline**, as we did previously, is a good way to parse integer inputs.

3. Use **if/else** statements to evaluate the condition based on the user input and then print either **The number you've entered was less than 10!** or **The number you've entered was greater than 10!**:

```C++
if (number < 10)
    {
        std::cout << "The number you entered was less than 10!\n";
    }
    else if (number > 10)
    {
        std::cout << "The number you entered was greater than 10!\n";
    }
    return 0;
}
```

4. The complete code looks like this:

```C++
// if/else example 1.
#include <iostream>
#include <string>

int main()
{
    std::string input;
    int number;
    std::cout << "Please enter a number: ";
    getline(std::cin, input);
    number = std::stoi(input);
    if (number < 10)
    {
        std::cout << "The number you entered was less than 10!\n";
    }
    else if (number > 10)
    {
        std::cout << "The number you entered was greater than 10!\n";
    }
    
    return 0;
}
```

5. Run the complete code in your editor. You will see that it evaluates the statements and outputs the correct string, as shown in the following screenshot

In this preceding exercise, we used two **if** statements that both evaluate a condition, but what if we want a default action if neither condition is true? We can achieve this by using an else statement on its own:

```C++
if (condition1)
    {
        // Do stuff.
    }
    else if (condition2)
    {
        // Do different stuff.
    }
    else
    {
        // Do default stuff.
    }
```

In this case, if neither **condition1** nor **condition2** proves to be true, then the code in the **else** block will be executed as a default. This is because there's no **if** statement, so nothing has to be **true** to enter it.

Applying this to our simple number example, we currently check whether the number is less than or greater than 10, but not if it's exactly 10. We could handle this with an **else** statement, as follows:

```C++
if (number < 10)
    {
        std::cout << "The number you entered was less than 10!\n";
    }
    else if (number > 10)
    {
        std::cout << "The number you entered was greater than 10!\n";
    }
    else
    {
        std::cout << "The number you entered was exactly 10!\n";
    }
```

---

## Ternary Operator

The ternary operator is a neat feature that allows us to quickly assign a value based on the outcome of an **if** statement. This is best shown with an example. Perhaps we have a float variable, the value of which depends on a Boolean. Without using the ternary operator, we could write this as follows:

```C++
if (MyBool == true)
    {
        MyFloat = 10.f;
    }
   else
    {
        MyFloat = 5.f;
    }
```

> **Note**: Here, we've used **==** instead of just **=.** The **=** operator assigns a value to a variable, whereas the == operator checks whether two values are equal, returning true if they are, and false otherwise. This will be covered in more detail in a later chapter on operators.

Using the ternary operator, we could also write this same code as follows:

`MyFloat = MyBool ? 10.f : 5.f;`

That's much more concise. Let's break down the syntax here and see what's happening. A ternary statement is written as follows:

`variable = condition ? value_if_true : value_if_false;`

> **Note**: While ternary statements can be nested as we saw earlier with **if** statements, it's probably best to avoid it. They can be a real pain to read and understand at a glance.

We start by specifying the condition that we want to evaluate and follow it with the **?** character. This sets our ternary statement in motion. We then define the different values we want to use if the value is **true** or **false**. We always start with the **true** value, followed by the **false** value, with them separated by the **:** character. This is a great way to concisely handle an **if/else** scenario.

## Exercise 6: Creating a Simple Menu Program Using an if/else Statement

In this exercise, we're going to write a simple program that provides menu options for a food outlet. Users will be able to select multiple options from a menu, and we will present the price information based on that choice.

Here are the steps to complete the exercise:

1. Create the template application, and output our three menu options to the user:

```C++
// if/else exercise – Menu Program
#include <iostream>
#include <string>

int main()
{
    std::string input;
    int number;
    std::cout << "Menu\n";
    std::cout << "1: Fries\n";
    std::cout << "2: Burger\n";
    std::cout << "3: Shake\n";
```

2. Next, we'll ask them to input their choice and store it:

```C++
 std::cout << "Please enter a number 1-3 to view an item price: ";
    getline (std::cin, input);
    number = std::stoi(input);
```

3. Now, we can use our **if/else** statements to check the user input and output the correct information:

```C++
if (number == 1)
    {
        std::cout << "Fries: $0.99\n";
    }
    else if (number == 2)
    {
        std::cout << "Burger: $1.25\n";
    }
    else if (number == 3)
    {
        std::cout << "Shake: $1.50\n";
    }
    else
    {  
        std::cout << "Invalid choice.";
    }

    return 0;
}
```

4. The complete code looks like this:

```C++
// if/else exercise – Menu Program
#include <iostream>
#include <string>

int main()
{
    std::string input;
    int number;
    
    std::cout << "Menu\n";
    std::cout << "1: Fries\n";
    std::cout << "2: Burger\n";
    std::cout << "3: Shake\n";
    std::cout << "Please enter a number 1-3 to view an item price: ";
    getline(std::cin, input);
    number = std::stoi(input);
    if (number == 1)
    {
        std::cout << "Fries: $0.99\n";
    }
    else if (number == 2)
    {
        std::cout << "Burger: $1.25\n";
    }
    else if (number == 3)
    {
        std::cout << "Shake: $1.50\n";
    }
    else
    {
        std::cout << "Invalid choice.";
    }

    return 0;
}
```

5. Run the application. When we input our menu option, we're presented with the correct information for that item, as shown in the following screenshot:

This ability to perform an action if a given condition is true really is at the heart of all programming. If you break down any system far enough, it will comprise "if x is true, do y." With this covered, the possibilities are endless.

---

## switch/case

As we've seen, we can use **if/else** to perform certain actions based on which conditions are true. This is great when you're evaluating multiple conditional statements to determine flow, such as the following:

```C++
 if (checkThisCondition)
    {
        // Do something ...
    }
    else if (checkAnotherCondition)
    {
        // Do something else ...
    }
```

When we're evaluating the different possibilities of a single variable, however, we have a different statement available to us: the **switch** statement. This allows us to branch in a similar way to an **if/else** statement, but each branch is based on a different possible value of a single variable that we're switching on.

A good example of where this would be suitable is the menu application we created in the previous exercise. Currently, we chain **if/else** statements to handle the different possible values, but since we're switching on a single variable (the menu index), it would be more suitable as a switch statement.

A basic implementation of a **switch** statement block is as follows:

```C++
switch (condition)
    {
        case value1:
            // Do stuff.
        break;
	case value2:
            // Do stuff.
        break;
        default:
            // Do stuff.
        break;
    }
```

Applying this to the previous menu example, the condition would be the selected menu index that we read from our user, and the different values would be our supported possibilities (1-3). The default statement would then catch the cases where the user inputs an option that we're not handling. We could print an error message in those cases and have them select a different option.

A switch statement comprises a number of keywords:

- **switch**: This denotes the condition that we're evaluating. We're going to switch our behavior based on its value.
- **case**: Each case statement is followed by the value that we want to handle. We can then define our behavior for that scenario.
- **break**: This statement signals the end of our code for that given case. More on these in the next topic.
- **default**: This is the default case and is what will get called should none of the other cases match.

> **Note**: A default case is not required but is recommended. It allows us to handle all other values, perhaps throwing an exception.

An important limitation of **switch** statements is that they can only be used with certain types. These are whole numbers and **enum** values. This means that, for example, we couldn't use either string or float types within a switch statement.

> **Note**: Enumerated type, or **enum**, is a user-generated data type in C++. A detailed discussion on this is beyond the scope of this course. However, you can refer to the documentation for further details.

It's also worth noting that not every case needs a **break** statement. They are optional, though will likely be required in the vast majority of cases. If the **break** statement is omitted, however, then the flow of execution will continue to the next **case** statement until a break is hit. Be careful here because missing **break** statements is a common cause of hard-to-find bugs; ensuring each case has a **break** statement where needed could save you lots of potential debugging time down the line.

Perhaps the best way to see the use of a **switch** statement is to convert some **if/else** chains to switch statements. This will be the objective of the following exercise.

---

## Refactor an if/else Chain into switch/case

In this exercise, we will reuse the code from the previous exercise and refactor it into a **switch** statement. This will clearly show how we can represent the same functionality using either method. Since we're only checking the different possible values of a single variable, however, a **switch** statement is preferred.

We will break this down into a number of simple steps:

First, the variable we're checking here is **number**, so that's going to be the condition that we're switching on. Add that to a **switch** statement and open our curly brackets ready for the rest of the switch block:

```C++
switch (number)
    {
```