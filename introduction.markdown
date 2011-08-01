Introduction
============

Ruby is an easy to use object oriented interpreted scripting language. There are a wealth of features for text processing and systems administration, much like Perl. It is easy to extend the language to fit your needs.

If you're looking for an easy to use object oriented language, but Perl is too cryptic, or you like Lisp but can't stand all the parentheses, then Ruby is the right language for you.

Below are the strong points of the language.

Interpreted
------
Since Ruby is an interpreted language, there is no need for compilation to run a program.

Dynamically Typed Variables
---------------
Variables in Ruby can store any type of data, so there is no need to worry about a variable's data type. On the other hand, compile time checking becomes less effective.

Variable Declaration is Unnecessary
-------
Variables in Ruby can be used without having to declare them. The actually type of variable(local, global, instance) can be determined from the variable name.

Simple Grammar
--------------
Ruby has a simple grammar is slightly influenced by Eiffel.

No User-Based Memory Management
--------------
Ruby handles memory management automatically. Objects that are no longer accessed are collected by a garbage collector built into the interpreter.

Everything is an Object
---------
Ruby was designed form the start to be a very simplistic object oriented language. 

Classes, Inheritance, Methods
-----------
Ruby contains basic object oriented language features such as classes, inheritance, and methods.

Singleton Methods
------
It is possible to append methods to a specific object. For example a method could be used to describe an action to be performed when a button is pressed. This allows, should you choose, for prototype based object oriented programming.

Mix-ins Through Modules
---------------
As multiple inheritance is often a source of complexity, Ruby has intentionally left out support for it. However, it is possible to share implementation details by utilization of an object's hierarchy through modules. This feature is known as a "Mix-in".

Methods Can Utilize Blocks (Iterators)
---------------------
In order to support the abstraction of control structures, so-called block methods can be utilized.

Closures
-----
Procedures can be treated as objects. Treating these procedures as objects is known as closures. 

Powerful String Manipulation/Regular Expressions
-------------
Using Perl as a model, Ruby contains powerful string manipulation and regular expression functionality.

Bignum
-----
There is built-in support for Bignum, so very large integer calculations can be achieved (as long as sufficient memory is available). For example, the factorial of 400 can easily be calculated.

Exception Handling
------
Exception handlers can be easily written to handle exceptional program behavior.

Direct OS Access
----------
Ruby is able to make UNIX style system calls. This means that system programming can be done using Ruby alone.

Dynamic Loading
------------
The loading of shared object files is supported if the OS allows for it.