# Singularity
A exploration towards writing code for microcontrollers in any language. Not just in C/C++.

## Objective
The objective of the project is analyze whether it is possible to build a program that allows us to write programs for embedded microcontrollers in any lanugage? Such that the code is also portable, so that we are able to run it from one platform to the other.

What do we require:
 - Supports **multiple programming languages**
 - Supports **multiple microcontroller architecture**
 - Support for code compatibility across different microcontrollers i.e. **code portability**
 - Optimized **production ready code**.

## Things that we've to explore
Here are the list of things that are required to be explored to gauge the feasibility of the project:

 - **GNU Compiler Collection** - I feel most of the work has already been done by GCC. We just need the right tools to stich everything together. It has the following parts:
	 - Front End
	 - Middle End
	 - Back End
 - **AVR GCC** - This thing (I don't really know what it is) provides us with the required libraries and header files to compile our C program to run on AVR microcontrollers. It makes use of GCC.
 - **Workings of a C Compiler** - Required for understanding how does a simple C program is compiled to generate the required machine code. (Very Interesting :P)
