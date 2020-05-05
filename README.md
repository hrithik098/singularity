# Singularity
A exploration towards writing code for microcontrollers in any language. Not just in C/C++.

## Objective
The objective of the project is analyze whether it is possible to build a program that allows us to write programs for embedded microcontrollers in any lanugage? Such that the code is also portable, so that we are able to run it from one platform to the other.

What do we require:
 - Supports **multiple programming languages**
 - Supports **multiple microcontroller architecture**
 - Support for code compatibility across different microcontrollers i.e. **code portability**
 - Optimized **production ready code**.

We have to make sure this project is **SMART**.
 - **Specific** - Able to generate final binary file from Python code.
 - **Measurable** - 
 - **Attainable** - This is something that I just wanted to do. We'll have to evaluate whether this is possible or not.
 - **Relevant** - Super relevant. If implemented, people would be able to program embedded devices in all sorts of different languages, don't have to worry about code interoperability on different micrcocontrollers (ideally speaking).
 - **Time Bound** - This looks like a really long project, but let's see how much can be done by **31st May, 2020**.

## Things that we've to explore
Here are the list of things that are required to be explored to gauge the feasibility of the project:

 - **GNU Compiler Collection** - I feel most of the work has already been done by GCC. We just need the right tools to stich everything together. It has the following parts:
	 - Front End
	 - Middle End
	 - Back End
 - **AVR GCC** - This thing (I don't really know what it is) provides us with the required libraries and header files to compile our C program to run on AVR microcontrollers. It makes use of GCC.
 - **Workings of a C Compiler** - Required for understanding how does a simple C program is compiled to generate the required machine code. (Very Interesting :P)
