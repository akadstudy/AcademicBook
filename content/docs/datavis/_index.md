---
# Title, summary, and page position.
linktitle: DataVisualization
summary: Learn how to use Academic's docs layout for publishing online courses, software documentation, and tutorials.
weight: 0
icon: book-reader
icon_pack: fas

# Page metadata.
title: DataVisualization
date: "2018-09-09T00:00:00Z"
type: book  # Do not modify.
---

# Overview

This chapter presents various tools and techniques that are used to control the flow of execution throughout applications. This includes, but is not limited to: if statements, switch statements, and various loops. We will also look at how we control the lifetime of our applications using these techniques, and how they are to be used efficiently. The chapter will end with the creation of a number guessing that that will implement various loops and conditional statements.

# Introduction

In the first chapter, we covered the absolute essentials of C++ and looked at the key components of a C++ application. We looked at how applications run, how they're built, and how we can get information in and out of them with some basic I/O. Up until this point, the applications we've built have mainly run sequentially; that is, the code we've written has been executed line by line, sequentially. While that's great for demonstration purposes, this generally isn't how real-world applications work.

In order to represent logical systems correctly, we need to be flexible in what we do and when. For example, we may only want to perform a certain action if a given statement is true or to return to an earlier piece of code again. Manipulating execution in this manner is known as control flow (or program flow), and is the topic of this chapter.

To begin with, we are going to look at the humble **if** statement, one of the most fundamental logic statements. We'll then branch out into looking at **switch** statements, a nice alternative to long chains of **if/else** statements. Next, we'll look at loops. Specifically, we'll see how we can use them to repeat code execution, and how we can make them more efficient and precise with **break** and **continue** statements.

The chapter will conclude with a fun activity in which we'll create a number-guessing game from the ground up. This will not only require the skills we learned in Chapter 1, Your First C++ Application, but also the program flow skills that we're about to cover. When this chapter is finished, not only will you have a solid understanding of the core logic statements and loops, but you will have also implemented them within practical exercises.
