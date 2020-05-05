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
 - **Measurable** - Once I get an overview of what needs to be done. Breaking the porject down in individual tasks would be much easier. Maybe I can up to setup a Kanban board  here at Github to track the tasks in the project.
 - **Attainable** - This is something that I just wanted to do. We'll have to evaluate whether this is possible or not.
 - **Relevant** - Super relevant. If implemented, people would be able to program embedded devices in all sorts of different languages, don't have to worry about code interoperability on different micrcocontrollers (ideally speaking).
 - **Time Bound** - This looks like a really long project, but let's see how much can be done by **31st May, 2020**.

There are certain **personal pain points** that I want to relieve for myself while doing this project.
 - **Lack of resources** - There is not enough documentation available in the embedded space. Even if we have the documentation available, it's extremely complicated to navigate around.
 - **Lack of examples** - The best possible way anyone can pickup how something is supposed to work is by looking at examples. We need more example codes!
 - **Extensive Fragmentation** - There are numerous frameworks, libraries, RTOSes for embedded system which has made the entire space completely fragmented, code reuse is highly inefficient because it was developed for some other framework.
 - **Maximum code reuse** - Can we use code that is was written for some other platform in different project, without giving up a lot of resources.
 - **Keep it Simple** - The individual components involved in this project are already extremely complicated. I would love to keep it as simple as possible.
 - **Better Abstraction** - All tasks we require micrcontrollers to do are communicated to them via memory address or registers, using our C/C++ code we are essentially loading/unloading stuff from registers which makes the microcontroller do something useful. **Can we build a better abstraction for this?** An abstraction that hides the useless details and verbosity, but still has provisions to make changes. For example, File System API, Sockets API for networking.
 - **Faster, Better, More Accessible** - I intend to make hardware development faster, starting from the software part. Make it a better experience for developers writing embedded code. And finally, if we are able to make hardware development simple, elegant and fast. We'll allow more and more to play around with hardware and build stuff. Enabling a revolution similar to that of the **Software Industry**.
 - **Simulation** - Ability to simulate code on hardware devices comes in handy. Due to the COVID-19 situation getting a  microcontroller was not possible. Only if there were simulators available that could do the job of running your code and verifying everything is working would be amazing. Access to simulators would allow us to write better test suites.
 - **Vision** - My vision is to make hardware development simple by making a system that allows people to create code that is simple to understand, looks elegant, runs like a production code and is super accessible because of tons of documentation. Personal Computers are the single best invention of mankind, its a tool that can be morphed to work in any area, any domain, it's just amazing! It we are able to create the right set of software tools so that people can create hardware, PCBs, layout and firmware all from your computer without soldering a single wire. It would be amazing! Suddenly, people who could never afford a microcontroller board can start writing code that runs on that platform, they can create hardware designs that other people can reuse. We need a community like GitHub but for Hardware. A revolution is yet to happen. There is a huge scope for innovation left. I'm trying to do my part by creating this repository :)

## Things that we've to explore
Here are the list of things that are required to be explored to gauge the feasibility of the project:

 - **GNU Compiler Collection** - I feel most of the work has already been done by GCC. We just need the right tools to stich everything together. It has the following parts:
	 - Front End
	 - Middle End
	 - Back End
 - **AVR GCC** - This thing (I don't really know what it is) provides us with the required libraries and header files to compile our C program to run on AVR microcontrollers. It makes use of GCC.
 - **Workings of a C Compiler** - Required for understanding how does a simple C program is compiled to generate the required machine code. (Very Interesting :P)

## C Code Compilation
There are 4 steps:

 1. **Preprocessing**
	 - Removing comments
	 - Expanding Macros
	 - Expanding included files
	 - Works in language extension
 2. **Compilation** - It takes the output of the preprocessor and generates assembly language, an intermediate human readable language, specific to the target processor.
	 - Lexical Analyzer
	 - Syntax Analyzer
	 - Semantic Analyzer
	 - Intermediate Code Generator
	 - Machine Independent Code Optimiser
	 - Code Generator
	 - Machine Dependent Code Optimiser
	 - Output: Machine Code 
 3. **Assembler** - Assembly code in, pure binary code or machine code (zeros and ones) out. Also known as object code. Every microcontroller vendor must have a specific assembler for every microcontroller that they produce.
 4. **Linker** - The linker merges all the object code from multiple modules into a single one. If we are using a function from libraries, linker will link our code with that library function code.
	 - **Static Linking** - linker makes a copy of all used library functions to the executable file.
	 - **Dynamic Linking** - the code is not copied, it is done by just placing the name of the library in the binary file.

Image showing steps of compilation:

![enter image description here](/docs/imgs/steps-of-compilation.jpg)

Phases of compilation:

![enter image description here](/docs/imgs/phases-of-compiler.jpg)

### Stuff that microcontroller vendors provide us with

 - **Assembler** - Nobody knows the opcodes for a microcontroller other than the uC vendor. This is a must have.

### Jargons

 - **Cross Compilers** - A compiler that runs on platform (A) and is capable of generating executable code for platform (B) is called a cross-compiler. This is something that we need.
 - **Source-to-source Compiler** - A compiler that takes the source code of one programming language and translates it into the source code of another programming language is called a source-to-source compiler. Also known as a transpiler. This might be helpful to create C code using Python, C++, Java code.

## GCC
Here's the architecture for GNU Compiler Collection:
![enter image description here](/docs/imgs/gcc-arch.jpeg)

## Resources
Here are the list of resources that I consulted or find useful:

 - [Writing a C Compiler, Part 1 - Nora Sandler](https://norasandler.com/2017/11/29/Write-a-Compiler.html)
 - [How the Compilation Process works for C Programs](https://medium.com/datadriveninvestor/compilation-process-db17c3b58e62)
 - [Tutorials Point - Compiler Design](https://www.tutorialspoint.com/compiler_design/compiler_design_overview.htm)
