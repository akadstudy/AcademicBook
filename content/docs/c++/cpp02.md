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

1. First, the variable we're checking here is **number**, so that's going to be the condition that we're switching on. Add that to a **switch** statement and open our curly brackets ready for the rest of the switch block:

```C++
switch (number)
    {
```

2. Next, we'll convert our first **if** statement into a **case** statement. If we look at the first one, we're checking whether **number** is equal to 1. Add this as our first **case** value and copy the output into the **case** body:

```C++
    case 1:
        std::cout << "Fries: $0.99\n";
    break;
```

3. Now, repeat this for each of the **if** statements, apart from the last one. If you remember, this statement had no condition that it checked; it's simply the last option. This meant that if all other checks failed, execution would fall right through to that final default statement. This is exactly how the default case works, so we will end by moving that **else** statement into a default case. We should end up with the following **switch** statement, which will replace our **if/else** chain:

```C++
switch (number)
    {
        case 1:
            std::cout << "Fries: $0.99\n";
        break;

        case 2:
            std::cout << "Burger: $1.25\n";
        break;

        case 3:
            std::cout << "Shake: $1.50\n";
        break;

        default:
            std::cout << "Invalid choice.";
        break;
    }
```

This statement is functioning the same as the chained **if/else**, so you could use either; however, you generally see switch statements over long **if** chains. Now, let's run this code and check that it's behaving how we'd expect.

4. The complete code looks like this:

```C++
// if/else to switch/case
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
 
    switch (number)
    {
    case 1:
        std::cout << "Fries: $0.99\n";
    break;

    case 2:
        std::cout << "Burger: $1.25\n";
    break;

    case 3:
        std::cout << "Shake: $1.50\n";
    break;

    default:
        std::cout << "Invalid choice.";
    break;
    }
}
```

5. Run the complete code. You will obtain an output that's similar to the following:

The program behaves in the same way but is arguably neater and easier to follow. We can clearly see each possible behavior branch and the case that will let it execute.

---

## Loops

Alongside **if** statements, loops are among the most fundamental of programming concepts. Without loops, our code would execute by running through our logic statements one by one and then ending. That's how our applications have worked so far; however, in reality, this really isn't practical. Systems tend to consist of many moving parts, and code execution will jump all around the code base to where it's needed.

We've seen how this can be achieved by creating branches in our code where statements can be evaluated, and we do different things based on the outcome. Another way we do this is via loops. Loops allow us to rerun sections of code, either a set or indefinite number of times depending on which one we choose. We're going to be looking at three: **while**, **do while**, and **for** loops.

## while

A while loop is one of the most basic loops in your arsenal and is usually the outermost loop in an application. When execution enters a while loop it typically won't leave until the condition is false. We say generally because multithreaded applications can break this rule; however, they're beyond the scope of this introductory course. Here is the basic implementation of a while loop:

```C++
  while (condition)
    {
        // Do stuff.
    }
```

A common thing to see in an application is an outmost **while** loop that will evaluate a **bool** such as **bIsRunning**. With this, you set an indefinite lifespan for your application, which is usually what we want. We want the software to run for as long as the user wants it to. As soon as we want the loop to stop running, we just change the bool to **false**. We need to be careful here, however, as it's easy to make a **while** loop that never ends as the condition never evaluates **false**. In this case, your loop will get stuck indefinitely with no way out.

The following code snippet shows this approach of using a **while** loop as an outermost loop to control the lifetime of the application. While **bIsRunning** is **true**, the application will run indefinitely:

```C++
int main()
{
    bool bIsRunning;

    // Do application setup.

    while (bIsRunning)
    {
        // Run application logic.
    }
    // Do application cleanup.

    return 0;
}
```

We've written a few example apps that accept user input, but generally stop after the first input. Let's take one of our existing applications and modify it so that it runs in a **while** loop; we'll continue with the menu application that we refactored into a switch. We want to put all of the code that we want to rerun inside the **while** loop. This includes the outputting of the menu items, the user selection, and the outputting of their answers.

---

## Implementing a while Loop

In this exercise, we will reuse the code from *Exercise 7, Re-factor an if/else Chain into switch/case*, and implement a **while** loop in our menu program.

Follow these steps to complete the exercise:

1. Copy the code from the previous exercise into the compiler window.
2. Now, implement a **while** loop and pass the value **true** into it shown in the following:

```C++
#include <iostream>
#include <string>

int main()
{
bool bIsRunning = true;
{
    while (bIsRunning)
    {
        std::string input;
        int number;

        std::cout << "Menu\n";
        std::cout << "1: Fries\n";
        std::cout << "2: Burger\n";
        std::cout << "3: Shake\n";
        std::cout << "Please enter a number 1-3 to view an item price: ";
        getline (std::cin, input);
        number = std::stoi(input);
        
        switch (number)
        {
            case 1:
                std::cout << "Fries: $0.99\n";
            break;

            case 2:
                std::cout << "Burger: $1.25\n";
            break;

            case 3:
                std::cout << "Shake: $1.50\n";
            break;

            default:
                std::cout << "Invalid choice.";
            break;
        }
    }
}
}
```

3. The complete code looks like this:

```C++
#include <iostream>
#include <string>

int main() 
{
bool bIsRunning = true;
{
  while (bIsRunning)
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

      switch (number)
      {
          case 1:
              std::cout << "Fries: $0.99\n";
          break;

	  case 2:
              std::cout << "Burger: $1.25\n";
          break;

	  case 3:
              std::cout << "Shake: $1.50\n";
          break;

	  default:
              std::cout << "Invalid choice.";
          break;
      }
    }
  }
	}	
```

4. Run the program.

For now, we just want this application to run indefinitely, hence we have used **true** as our expression. We can see that it loops, re-asking the user for their selection again, as shown in the following output:

---

## do while

The structure of a do while loop is very similar to that of a **while** loop, with one fundamental difference: the condition check is after the body. This subtle difference means that the body will always be executed at least once. The basic structure of a **do while** loop is as follows:

```C++
    do
    {
        // code
    }
    while (condition);
```

The following flowchart shows the structure and logic flow of a **do while** loop:

Look at the following example:

```C++
 while (false)
    {
        // Do stuff.
    }
```

The code inside this **while** statement will never be executed because we first evaluate the expression, **false**, and thus skip over that code. If we were to use the same condition with a **do while** loop, however, as shown in the following code snippet, we would see different behavior:

```C++
do
    {
        // Do stuff.
    }
    while (false);
```

In this case, since the execution runs from top to bottom, the code is executed first, and then the condition; even though it's **false**, the code has already run once. We will see this with the help of our old friend—the **Hello World** program.

---

## Implementing while and do while Loops with a False Condition

In this exercise, we will edit code "Hello World" program to include a **while** and then a **do while** loop. For both of these loops, we will pass the **false** condition and observe the outputs.

Follow these steps to complete the exercise:

1. Insert the following code, which includes a **while** loop only, in the compiler window, and then execute it:

```C++
// While loop.
#include <iostream>
#include <string>

int main()
{
    while (false)
    {
        std::cout << "Hello World!";
    }

    return 0;
}
```

You will obtain the following output:

As can be seen in the output, we see nothing in the execution window. Since we did the evaluation first, the program never executed the code. This changes, however, if we replace the while loop with a do while loop.

2. Edit the code to include a **do while** loop, as shown in the following snippet:

```C++
// do ... while loop.
#include <iostream>
#include <string>

int main()
{
    do
    {
        std::cout << "Hello World!";
    }
    while (false);

    return 0;
}
```

3. Run the code. You should obtain the following output:

Now, we can see that we do indeed get the words **Hello World** printed to the console; so, while the two loops are similar in nature, they have a big difference. The **while** loop will evaluate the condition first, whereas the **do while** loop evaluates it after.

---

## for

Both **while** and **do while** loops are indefinite loops, meaning they will only stop when their conditions evaluate **false**. Generally, when constructing these loops, we don't know how many iterations we need; we simply set it going and stop it at some later juncture. **for** loops, however, are used when we know how many iterations of something we need, and when we need to know what iteration we're currently on.

For example, let's say we have a collection of contacts and we want to run through them all, printing out their names and numbers. Since we know the size of this collection, we could write a for loop that would iterate the correct number of times, allowing us to visit every element in the collection sequentially. Since we also know which iteration we're currently on, we could use that to determine how we output the data. Perhaps, for the first half of the contact list, we want to output both the name and number, whereas, for the second half, we only require numbers. Or perhaps we want to do something special with the first and last contacts in the list. A **for** loop would allow us to do all of these things.

> Note: One iteration is just a loop running once. If a loop is said to iterate five times, it just means it ran five times.

The basic structure of a **for** loop is as follows:

```C++
    for (initialization; condition; iteration expression)
    {
        statement(s);
    }
```

The following flowchart shows the structure and logic flow of a **for** loop:

There are three clauses that are used in a for loop:

- **Initialization**: This is a statement that is run once at the very start of the loop. This is used to declare a variable that will be used as a counter.
- **Condition**: This is the condition that is checked each time before the loop runs. If the condition is **true**, the loop will run. If the condition is **false**, that's the end of the **for** loop. This is used to check that the counter variable is below a specified value. This is how we control how many times the loop will run.
- **Iteration Expression**: This is a statement that's run at the end of each loop. It's used to increment the counter variable.

Now, let's implement a basic **for** loop in the next exercise to cement our understanding.

---

## Implementing a for Loop

In this exercise, we will create a **for** loop that will run five times to print out a string of numbers: **01234**.

Perform the following steps to complete the exercise:

1. Begin with the main function:

```C++
#include <iostream>
#include <string>

int main()
{
```

2. Create a **for** loop with the variable **i** initialized to **0**, and **i** set to be less than **5**; increment the counter, and then finally print the output. You can use the following code for this:

```C++
    for (int i = 0; i < 5; ++i)
    {
        std::cout << i;
    }
}
```

3. The complete code looks like this:

```C++
#include <iostream>
#include <string>

int main() 
{
    for (int i = 0; i < 5; ++i)
    {
        std::cout << i;
    }
}
```

Run the code. You will obtain the following output:

We can see that 5 numbers are printed out, 0 through 4, as shown in the preceding screenshot. Notice that the numbers are 0 through 4, as the increment runs after the main loop body, and **i** starts with a value of 0.

We can break the code down into the three statements we identified in the preceding section: **initialization**, **condition**, and **increment**. Our **initialization** statement in this loop is as follows:

```C++
    int i = 0
```

With this statement, we're creating our counter and setting its value to 0. This counter is what will be used to keep track of how many times we want our loop to run. Our **condition** statement in this loop is as follows:

```C++
    i < 5
```

This is the **condition** that we check to ensure that the loop can run, similar to how the **while** loop works. At the start of each iteration, this **condition** is checked. If I (our counter variable) is less than the value specified, then the loop will run. Our **increment** statement in this loop is as follows:

```C++
    ++i
```

This statement is called after each iteration of the loop and increments our counter so we can keep track of how many times the loop has run.

---

## Range-based for loop

The last loop we're going to look at, and more briefly than the previous three, is the range-based loop. Introduced in C++ 11, this loop allows us to quickly iterate over all objects in a collection. We've not yet covered collections, so we will only address the basics here.

When iterating over collections using a **for** loop, we use the iterator. In our use cases, that's been the **i** variable to access the elements as shown in the following snippet:

```C++
    int myVector[] {0, 1, 2, 3, 4};
    for (int i = 0; i < myVector.size(); ++i)
    {
        int currentValue = myVector[i];
        std::cout << "\n" << currentValue;
    }
```

With a range-based **for** loop, however, we don't manually get the element via our incrementing value. Instead, the loop simply gives us each value in the collection:

```C++
    int myVector[] {0, 1, 2, 3, 4};
    for (int currentValue : myVector)
    {
        std::cout << "\n" << currentValue;
    }
```

Both these loops will produce the same output, but we can see that the second loop is more concise, less prone to error because we aren't manually fetching our elements, and is also very likely to be more efficient. Generally, if you don't need an index value, then this kind of loop will allow you to have cleaner, more solid code.

## Exercise 11: Generating Random Numbers Using Loops

In this exercise, we're going to build an app that will generate a set of random numbers for the user. Our application will consist of a main outer loop and another loop within it to control the generation of our numbers.

For the outer loop, we're going to use a **while** loop—a common setup for an application. We know that this loop will run indefinitely, so it is perfect for controlling the outermost scope of an application. For the inner loop, we'll use a **for** loop, because we'll know how many numbers our user wants to generate.

Follow these steps to complete the exercise:

1. We'll start by creating our main function and defining our main variables. This includes the bIsRunning bool, which will control the lifetime of our application:

```C++
#include <iostream>
#include <string>
#include <cstdlib>
#include <ctime>

int main()
{
    bool bIsRunning = true;
    std::string input = "";
    int count = 0;
```

Next, we'll output our heading content and create the **main** loop. We're using a **while** loop, and our condition is going to be that **bool** we just defined:

2. Next, we'll output our heading content and create the **main** loop. We're using a **while** loop, and our condition is going to be that **bool** we just defined:

```C++
    std::cout << "***Random number generator***\n";
    while (bIsRunning)
    {
```

3. With our **while** loop in place, we can now add all the code that we want to run during each iteration of the **main** loop. This starts with outputting our instructions and reading the user input:

```C++
  std::cout << "Enter amount of numbers to generate, or 0 to exit: ";
        // Get count from user.
        getline(std::cin, input);
        count = std::stoi(input);
```

We've covered **break** in this chapter, and we can now use it to check whether the user wants to exit the application. If the user entered a **0**, indicating this, we can call **break**, exiting the main **while** loop and ending the application. We'll also set the seed for our random number generation.

> **Note**: To generate our random numbers, we're using **rand** and **srand**. **rand** gives us our random number, and **srand** sets a seed for the random number generation. By using **time(0)**, time in seconds since the epoch, we get a seed and number random enough for our needs.

4. Input the following code to insert a **break** statement to allow the user to exit the application. We'll cover '**break**' in more detail shortly:

```C++
        // Check if user wants to quit application.
        if (count == 0)
        {
            break;
        }
        // Generate and output random numbers.
        srand((unsigned)time(0));
```

Now, we can write the **main** loop that will generate our random numbers and output them to the user. Since we got a **count** variable from our user, we can use that to ensure we iterate the correct number of times. Within the loop, we'll generate a random number and do a bit of formatting. After each number, we want to print a comma to create a well-formatted list, but not after the last one. We can use a **continue** statement for this:

> **Note**: The continue statement will be covered in the next topic. For now, note that it allows us to skip the rest of the current loop, starting the next one immediately.

```C++
        for (int i = 0; i < count; ++i)
        {
            std::cout << rand() % 10;
            if (i == count - 1)
            {
                continue;
            }
            std::cout << ", ";
        }
```

> **Note**: The modulus % operator returns the remainder after division. In the preceding step, we are using it, along with **rand**(), to generate numbers between 0 to 9. We'll cover this, and many other operators, in more detail in Chapter 4, Operators.

6. Finally, we'll output a couple of blank lines for presentation and add our final curly braces:

```C++
        std::cout << "\n\n";
      }
  }
```

7. The complete code looks like this:

```C++
#include <iostream>
#include <string>
#include <cstdlib>
#include <ctime>

int main() 
{
    bool bIsRunning = true;
    std::string input = "";
    int count = 0;
    std::cout << "***Random number generator***\n";
    while (bIsRunning)
    {
        std::cout << "Enter amount of numbers to generate, or 0 to exit: ";
        // Get count from user.
        getline(std::cin, input);
        count = std::stoi(input);
        // Check if user wants to quit application.
        if (count == 0)
        {
            break;
        }

        // Generate and output random numbers.
        srand((unsigned) time(0));
        for (int i = 0; i < count; ++i)
        {
            std::cout << rand() % 10;
            if (i == count - 1)
	    {
                continue;
            }
            std::cout << ", ";
            }

	    std::cout << "\n\n";
        }
    }
```

8. Run the application. When complete, the application should be able to generate the specified number of random integers, as shown here:

By using a **while** loop, we've been able to create an application that can be used for an indefinite amount of time. Imagine if every time you went to do something on your computer, you could only do one thing before it needed to be rebooted. This would not be very practical. Having the ability to loop code and manipulate program flow is essential.

---

## break/continue

Having the ability to loop sections of code is very important, but it has to be used carefully. We've seen that it's possible to create loops that never end, and another concern is ensuring that they're used efficiently. So far, the loops we've looked at have been small, and we've been happy to see them run through in their entirety. But what if we needed more control over our loops, perhaps to end one early? Thankfully, we have two important keywords to help us with that**—break** and **continue**.

### break

**break** is a C++ keyword that will exit the current loop, with execution jumping to the next section of code if there is any. This keyword works with the different types of loop that we've covered so far, and we can demonstrate it nicely using a simple counting application, as shown in the following snippet:

```C++
// Break example.
#include <iostream>
#include <string>

int main()
{
    std::cout << "Loop Starting ...\n";
    int count = 0;
    while (count < 5)
    {
        ++count;
        std::cout << "\n" << count;
    }

    std::cout << "\n\nLoop finished.";
}
```

In this example, we're going to print out 5 numbers, 0-4. If we run this code as is, we can see that the loop runs in its entirety and gives us our expected outcome. We've also got statements at the start and end of the loop so we can see the flow execution more clearly:

Now, what if there was a condition that meant we wanted this loop to stop executing when the count was equal to 2? Well, we can put a **break** statement inside that check using an **if** statement:

```C++
#include <iostream>

using namespace std;

int main()
{
    std::cout << "Loop Starting ...\n";
    int count = 1; // init
    while (count <= 5) // condition
    {
        std::cout << "\n" << count;
        if (count == 2)
        break;
        ++count; // increment
    }
    std::cout << "\n\nLoop fnished.";
    
    return 0;
}
```

With that **break** condition in place, as soon as the count is equal to **2** (meaning we'll have had 2 iterations of the loop) then the break will be hit and we'll exit the loop. Now, let's run the application and see what we get:

We can now see, as soon as that condition is met and the **break** statement is hit, that the loop stops iterating, and code execution picks up immediately after the loop. The outcome of this will be exactly the same if we write it as a **do…while**:

```C++
#include <iostream>

using namespace std;

int main()
{
    std::cout << "Loop Starting ...\n";
    int count = 1; // init
    do
    {
        std::cout << "\n" << count;
        if (count == 2)
        break;
        ++count; // increment
    }
    while (count <= 5); // condition

    std::cout << "\n\nLoop fnished.";
    return 0;
}
```

And it will be the same if we write it as a **for** loop:

```C++
#include <iostream>

using namespace std;

int main()
{
    std::cout << "Loop Starting ...\n";
    // init condition increment
    for (int count = 1; count <= 5; ++count)
    {
        std::cout << "\n" << count;
        if (count == 2)
        break;
    }
    std::cout << "\n\nLoop fnished.";
    
    return 0;
}
```

Both these loops give the exact same behavior; two iterations before hitting the **break** statement and exiting the loop:

This shows that these loops are sometimes interchangeable, though some are more suited to certain use cases than others. For instance, with the counting example we're using here, a for loop is probably most suitable since it comes with an integer value that increments each loop—something we have to do manually with **while** and **do while** loops. When an incrementing integer is not required, however, a range-based **for** loop is recommended.

### continue

The other keyword we have at our disposal is **continue**. This keyword allows us to skip over the current loop iteration but remain in the loop, in contrast with **break**. Again, the counting example will allow us to demonstrate this. In our example, we're printing the numbers 0-4; let's use the **continue** keyword to skip the printing of the number 3.

As we did with **break**, we can write a condition to check whether the count is equal to 3, and call **count** if so:

```C++
    if (count == 3)
    {
        continue;
    }
```

We also need to change the location of this within our function. The **continue** keyword will skip the rest of the loop's body. Currently, this code is at the end of that body, so we won't actually be skipping anything. In order for **continue** to work as expected, it needs to come before any code that we want to skip but after any code we want to execute. For this example, we will place the **continue** keyword with the **if** statement:

```C++
// continue example.
#include <iostream>
#include <string>

int main()
{
    std::cout << "Loop Starting ...\n";
    int count = 0;
    while (count < 5)
    {
        ++count;
        if (count == 3)
        {
            continue;
        }
    std::cout << "\n" << count;
    }
    std::cout << "\n\nLoop finished.";
}
```
Here, we're always going to increment our **counter** variable and then check whether we want to skip the current iteration. If we do skip it, we'll just go back to the start of the next loop, and if we don't, we'll execute the remainder of the loop as usual. Once you run this code, you will obtain the following output:

We've skipped the printing of number 3 as we wanted, but the loop continued to execute the rest of the way. This can be extremely useful when searching for something. Imagine we have a list of names, and we only want to do things with those that start with the letter D. We could iterate over all our names, first checking whether or not the first letter is D; if not, we continue. In this way, we efficiently skip the use cases that don't interest us.

## Making a Loop More Efficient Using break and continue

In this exercise, we're going to make use of **break** and **continue** to make a loop more efficient. We'll create a loop that will run over the numbers 1-100, printing out only specific multiples of a given value.

Follow these steps to complete the exercise:

