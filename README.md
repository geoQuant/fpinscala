[![Build status](https://travis-ci.org/fpinscala/fpinscala.svg?branch=master)](https://travis-ci.org/fpinscala/fpinscala) [![Join the chat at https://gitter.im/fpinscala/fpinscala](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/fpinscala/fpinscala?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) 
# My Notes
1. Change Build.sbt to compile to scala 2.11.6
2. Mac OSX error: https://coderwall.com/p/ktbkea/play-framework-2-error-nodename-nor-servname-provided-or-not-known

# Chapter 2
- scala code has to be in an object or a class
- def is used to define methods
- left-hand side of a method is called the signature, and the right hand-side of the equal sign is called the definition
- a private method means that it cannot be called from any code outside of the object
- Unit == void 
- () represents a Unit type
- scalac filename.scala -> scala filename OR scala filename.scala
- scala -> :load filename.scala -> MyModule.abs(-42)
- to access and object's methods: namespace(the name that refers to the object), dot, member. For example: MyModule.abs(-42)
- Syntactic Sugar: 2 + 1 == 2.+(1) // pass 1 as an argument of the + method on the object 2
- any method can be used infix like above! for example: MyModule abs 42 == MyModule.abs(-42)
- To bring an object's members into scope by importing: import MyModule.abs
- To bring ALL of an object's (non-private) members into scope do: import MyModule._
- FUNCTIONS ARE VALUES, therefore can be assigned to variables, stored in data structures, and passed as arguments to functions
- Higher order function: accepts other functions as arguments
- Pg 22: MyModule.formatResult("absolute value", -42, MyModule.abs)
- Pg 23: PolymorphicFunctions.findFirst2(Array(7,9,13), (x: Int) => x == 9)
- (x: Int) => x == 9 // This is a function literal or anonymous function
- <function2> notation in the REPL indicators that the value is a function that takes two arguments

---
This repository contains exercises, hints, and answers for the book
[Functional Programming in Scala](http://manning.com/bjarnason/). Along
with the book itself, it's the closest you'll get to having your own
private functional programming tutor without actually having one.

Here's how to use this repository:

Each chapter in the book develops a fully working library of functions
and data types, built up through a series of exercises and example code
given in the book text. The shell of this working library and exercise
stubs live in
`exercises/src/main/scala/fpinscala/<chapter-description>`, where
`<chapter-description>` is a package name that corresponds to the
chapter title (see below). When you begin working on a chapter, we
recommend you open the exercise file(s) for that chapter, and when you
encounter exercises, implement them in the exercises file and make sure
they work.

If you get stuck on an exercise, let's say exercise 4 in the chapter,
you can find hints in `answerkey/<chapter-description>/04.hint.txt` (if
no hints are available for a problem, the file will just have a single
'-' as its contents) and the answer along with an explanation of the
answer and any variations in
`answerkey/<chapter-description>/04.answer.scala` or
`04.answer.markdown`. The finished Scala modules, with all answers for
each chapter live in
`answers/src/main/scala/fpinscala/<chapter-description>`. Please feel
free to submit pull requests for alternate answers, improved hints, and
so on, so we can make this repo the very best resource for people
working through the book.

Chapter descriptions:

* Chapter 2: gettingstarted
* Chapter 3: datastructures
* Chapter 4: errorhandling
* Chapter 5: laziness
* Chapter 6: state
* Chapter 7: parallelism
* Chapter 8: testing
* Chapter 9: parsing
* Chapter 10: monoids
* Chapter 11: monads
* Chapter 12: applicative
* Chapter 13: iomonad
* Chapter 14: localeffects
* Chapter 15: streamingio

To build the code for the first time, if on windows:

    $ .\sbt.cmd

If on mac/linux, first make sure you have not checked out the code onto
an encrypted file system, otherwise you will get compile errors
regarding too long file names (one solution is to put the fpinscala repo
on a unencrypted usb key, and symlink it into your preferred code
location).

    $ chmod a+x ./sbt
    $ ./sbt

This will download and launch [sbt](http://scala-sbt.org), a build tool
for Scala. Once it is finished downloading, you'll get a prompt from
which you can issue commands to build and interact with your code. Try
the following:

    > project exercises
    > compile

This switches to the exercises project, where your code lives, and
compiles the code. You can also do:

    > console

to get a Scala REPL with access to your exercises, and

    > run

To get a menu of possible main methods to execute.

To create project files for the eclipse IDE you can install the
[sbteclipse](https://github.com/typesafehub/sbteclipse)
[sbt](http://scala-sbt.org) plugin. This makes a new command available
in [sbt](http://scala-sbt.org):

    > eclipse

All code in this repository is
[MIT-licensed](http://opensource.org/licenses/mit-license.php). See the
LICENSE file for details.

Have fun, and good luck! Also be sure to check out [the community
wiki](https://github.com/fpinscala/fpinscala/wiki) for the **chapter
notes**, links to more reading, and more.

_Paul and Rúnar_

