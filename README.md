# Parse-CC-Base
A collection of all my Parsers For the Casual Collection Format

This does not have the actual code to the program, but it a hub where 
all the code can be found. There is code for-

* Python Users
* Java Users
* Kotlin Users
* C/C++ Users
* C# Users
* Rust Users
* Go Users

# Ao3 Coder Lore

As a deeper summary for the lore behind this, I write a series call the
Casual Collection, which is an anthology of various characters 
interacting in my own rendition of Monster Girl Encyclopedia. If you
wish, you can check out the story by [clicking this link!](https://archiveofourown.org/series/2460391)

I've been writing for a while, before I write even more I wanted to 
record all the important information about my series, episode by 
episode, and add songs because giving my stories a soundtrack is fun!

Anyways I made a setup and started recording information. I reached
around halfway before realizing "hey, this looks pretty organized. I
could probably make a code that turns my notes into JSON."

And then I realized. I **could** turn my notes into JSON! And thus
started my hyperfixation into making this a reality. As a bonus, I took
this as an excuse to see what it looks like in other languages, and 
compare and contrast all the aspects of everything.

With that being said, before I can dive into my findings, I first have
to explain how the note system works, and how the programs will be told
to interpret everything.

# Format of CC Notes

To speed up the process of looking through a few years worth of
fanfiction I wrote, I created a system to keep track of important 
things:

```
**Season Name** (The name of the Season that I'm taking notes about)

* **Episode Name** (The name of the Episode that I'm taking notes about)

   * **Characters** (List of characters in the episode)
   
   * **Locations** (List of locations used in the episode)
   
   * **Start Date** (Starting time of the episode)
   
   * **Timeline** (Time progression of the episode)
   
   * **Songs** (Songs used in the episode)
   
      * **Intro Song** (Intro song of episode)
      
      * **Scene Specific** (Songs for specific scenes in the episode)
      
      * **Outro Song** (Outro song of episode)
```
      
In this manner, I keep everything setup with within Seasons, then 
Episodes, then various attributes I consider important to remember.
Character tracking lets me know which episodes characters are in (to
prevent "Araki forgets" moments). 

Same thing with locations, as well as for designing a new map for my 
world. Start Date and Timeline help me keep track of time progression, 
which is useful since each season is self-contained, and characters 
from reach plotline interact with each other down the road. Knowing the 
plot points of each character is the difference between specific 
interactions.

Lastly, songs let me know what songs are used, and which scenes get 
what soundtrack. I won't lie, I had fun with it so it isn't like perfect
SFX, but it's definitely mine. By the way, [here is my spotify link for
the playlist.](https://open.spotify.com/playlist/5dMLr60zHU7IxBRyO5nemc)

With this setup, the strategy for creating a JSON is laid out. Use the
usage of astrisks and space indenetation to progressively nest deeper
and deeper key value pairs until boom! a perfectly created JSON layout.

However, the longer I got with this project, the more I realized that
this simple, high-level explanation ranges from being a very laid back
task to being given a telegraph and being told the commentate on the
World Series in real time through Morse code. 

Not that I hated it, but it got VERY INTERESTING for some of these
languages, which brings me to my next point-

# The Main Criteria & Topics

Doing this project has made me realize that each language has it's own
purpose and niche, to the point where learning one's syntax can feel
entirely new. There are also different levels of support, ease of 
learning, debugging ability, and much else to consider. 

Lastly, there is the "feel" of coding in that language. Some languages 
just feel better, and it's a 50/50 chance I would be able to give a 
good explanation why. 

One more thing as well. The IDE that is use to develop software matters
JUST AS MUCH as the language itself, so it would be more accurate to
say that I am evaluating language-IDE combos. 

With that being said, here is a list of topics and criteria that I will 
cover on a language-by-language basis:

1) Purpose - What was the language initially created for? Why was it
necessary? What was it replacing/adding on to?

2) IDE Integration - How well does it intergrate with my IDE of choice?
How was the autocompletion, the intellisense, the syntax highlighting?

3) Building - How easy is it to build and run my program?

4) Debugging - How easy is it to track down bugs? How does it feel to
work with the debugger?

5) Organization - How does the language like to be organized. More
accurately, what organization did **I** graviate to as a result of the
"feel" of the language?

6) 1st Party Dependencies - How easy was it to leverage out-of-the-box
content?

7) 3rd Party Dependencies - How easy was it to leverage additional
content made by the community?

8) Syntax - What is it like organizing lines, methods/functions, etc.?

# The Program Criteria & Topics

Other than that, I will also comment on how each language is able
to do the following tasks, broken down into further subtasks:

1) Read in input from the user for the path of the text file.
	1) Print welcome message
	2) Read the input
	3) Parse out possible quotes
2) Use the file path to read in content from the text file.
	1) Catching exceptions
	2) Reading into a iterable object
3) Parse the information into JSON
	1) Creating a JSON object
	2) Going line by line through a conditional tree
	3) Dynamically adding objects and values
	4) Removing excess information
	5) Passing and returning different objects
4) Using JSON Object to retrieve specific items
	1) Creating a set or set-like iterable
	2) Iterating through the JSON Object
	3) Using an int setting to decide what items to get
5) Saving JSON and sets to file
	1) Getting a parent directory path
	2) Creating a new directory
	3) Writing information to file

Each language will handle these five tasks different, with varying 
levels of lenience, support, and stubborness for each particular thing.

Without further ado, lets start the languages in chronological order.
I think that doing that will help understand how each language feeds
into each other.

But to do that at all, we first have to understand C.

# The C Language's Creation

C was created by Dennis Ritchie and Ken Thompson around 1972 and 1973 
for developing Unix utilities. It took off in the 1980s, was 
standardized by the American National Standards Institute (ANSI), the 
International Organization for Standardization (ISO, weirdly), and 
other orgs.

Going back to the early 1970s, Ritchie and Thompson's main goal was
around the Unix Operating System. At first,the Unix OS was developed in
assembly, but Thompson was looking for a language that could abstract
assembly for developing OS utilities. 

Thompson first attempted Fortran, didn't work. After, he turned his
sights on BCPL, a procedural language designed for creating small
compilers. BCPL used a front-end parser to convert source code to an
intermediate form, then used a back-end translator to turn the
intermediate form into machine code. If this sounds familiar, this
two-step system would go on to inspire the strategies for Java and 
Python.

BCPL only had one datatype called a **word**. A word had the same
number of bytes as the computer's architecture width (i.e. 32-bit).
BCPL also used operators like +, and ! for pointers, but did no type
checking as common today.

The most fundemental influence arguably came in it's use of braces,
which could have been {}, $($), or \[] depending on the hardware at the 
time.

Although the language was already pretty light Thompson stripped it 
down and configured it to his needs, which he would call B. 

B had major changes throughout development, guided by preferences like
a reduction in the whitespace taken up by the source code. Like BCPL, 
B only had a word type, with some operators treating it like integers
and other operators treating it like general memory. Common functions 
such as printn() make their apperance here, such as comparison 
operators like ==. 

Ritchie and Thompson improved on B, adding a character type, more
involved types like arrays and the handling of them like pointers
within specific scenarios, and much more. Eventually, all the new
additions necessated a new Unix compiler, with C becoming the new name
of the developing language.

# C as a Language

With this background, we can say that C was created to abstract the
development of system applications away from Assembly. As a 
standardized language, C organizes codes using brackets, creates
changable values called variables by specifying the type (i.e. char) 
then the name of the variable to be referenced, and allows for decision
making using switch, if, else, whlie, do, for, break, and continue. 

C allows the defining of pointers to reference variables that take up
multiple bytes worth of space in memory, which then allows for more
complex structures such as arrays and structs. If it feels like I am
forgetting a structure, you are not crazy. We are just not there yet,
and from the perspective of the UNIX kernel makers, we don't need to
be. C is supposed to be a general procedural language that bridges the
gap between low-level memory management (both automatically and 
manually through keywords like malloc and free) and higher, complex
programs. C is programming freedom at its most basic level, and cares
not for holding your hand. If you *really* want to use more, you have
standard libraries you can access using the include keyword.

Basically a kernel developer's dream.

Although, it is pretty basic, which makes sense because it came from a
basic compiler maker. But what if...

# C++ 14 x Microsoft Visual Studio 22

This is techincally the oldest language I used for this project,
although what I use is far from the original.

Bjarne Stroustrup created "C with classes" in '79, seven years removed
from the beginnings of C. In his eyes, the existing languages at the
time were either-

* Great for large scale applications with complex needs, but too slow to 
be used practically.
* Great for fast compiling programs but too low level to be used for
complex large-scale needs.

Stroustrup leaned on prior experience looking at the UNIX Kernel and
decided to enhance C, which was supposed to be the original bridge-gap,
with features that Simula (which fell in the first category of existing
languages) had for large scale development, along with inspiration from
other langugaes. 

*C with Classes* was the result, which introduced classes, inlining, 
default arguments for functions, and more. 

1982 marked the creation of, C++, which was Stroustrup next improvement 
and named by adding the increment operator "++" to C as a symbol of
additions to the popular language. Overloading, references, better type
checking, and the return of "//" commenting from BCPL came with C++.
C++ would also bring the first stream I/O library.

C++ 2.0 would come in 1989 and add multiple inheritance, abstract
classes, static class functions, protected members, templates, 
namespaces, and a boolean type.

C++98 would come in 1998 and continue to build upon existing features
and standardizing the language. The next standard for C++ would be
C++11 which enlarged the standard library, and C++14 which was more
minor than the others. C++17 and C++20 would follow after.

With this background, C++14 is the minor update to C++11, the last
major standard before C++14. C++11 improves on C++98, which improves on
C++2.0. C++ as a whole served as a means to bring Object-Oriented
Programming and accessible complexity to a simple, but very powerful
language. C++'s development principles stress immediately useful
additions, implemental features, freedom of programming style, 
user-created types having just as much support as built-in types, and
optimizing the program. 

One last thing to note is that while C++ builds upon C, it is not an 
ABSTRACTION of C, and the only thing underneath it should be the
ASM itself.

## My Experience with C++ 14 and VS 2022

Now, I can put into perspective how I feel about C++. I answered the
purpose pretty well, so I can now talk about everything else.

Visual Studio's IDE is something you have to get used to. Like alot of
well developed IDEs it takes some exploring before you can get into a
flow state developing the program. The first thing I did when starting
a new C++ project was trying to use CMake, which I promptly failed it
at first try. I still don't know how to do it, so I guess it is an
adventure for the future.

In the mean time, getting VS to build my code was pretty easy. It came
with default x32 and x64 build configurations for both debug and 
release, so most of the work was pressing a button. The debugger built
into to VS was great, and gave me plenty of options to work with.
Syntax highlighting lagged behind a bit with certain changes (i.e.
uncommenting a block of code I commented to safe for later) and the
intellisense was pretty run of the mill IMO.

Without the debugger, i think it would have been much harder to find
problems in my code, but because of that I don't have to think of that
reality. VS 2022 in full debug mode will stop at the source of the
exception, and then you can analyze the state to see what went wrong
with execution.

The organization of the code was bottom up, which meant the main
function was down at the bottom, followed by other functions, and then
smaller utility functions that supported the other functions. At the
top, I declared all the cpp libraries I used, along with a 3rd party
json library by stating the path to the file from the code's location.

That leads me to dependencies. It was very easy to utilize 1st party
dependencies as VS 2022 intellisenses all the out-of-box stuff.
However, there will be times that you forget which library came with
which standard of C++. When attempting to use the filesystem library,
I ran into problems before realizing that the library was introduced in
C++17, meaning I could not use it.

As for third-party stuff, I have the option of using a package manager,
or copying the files into my project folder and specifying the path to
it. As you could tell, the latter helped alot when I couldn't figure
out CMake and the other thing.

Lastly, the syntax is as nice as ever. With C being the mother of alot
of languages and C++ only adding to it, the syntax is very refined. At
least the way I used it. I have heard horror stories and the best
advice I've ever read is that everyone has their own way of using C++,
and while other people would leverage templates and overloading, I 
kept it basic so that I could work within my means. Coding the latter
half of the script forced me to learn what "auto" meant, but once I did
I was able to use it pretty easily.

## C++ 14 and VS 2022 when turning notes into JSON

Now lets see how my experience was in relation to the five main subtasks
I had to do to convert my notes.

The first task whats to get input on where the user's file was. In the
case of C++, this meant declaring the string variable where the 
filepath will be placed, and using getline() to read the line to ensure
that the input isn't cut off early due to possible spaces being in the
filepath. Afterward, the last thing was ensuring that any quotations
in the input are removed, as copying a filepath from specific sources
can have the path be entered as a quoted string into the terminal. This
process was fairly straightforward to figure out within two attempts.

The second task was reading the contents in from the file path
provided. This sometimes necessitates exception handling while reading
each line into an iterable of strings. In C++, vectors were the
structure of choice to do this, plus a declared string to be a location
to hold lines while the file is read. A while loop and a file close()
later, and it is done.

Next comes things I have to program myself, the building of the JSON
object using the lines. This was made easy as a 3rd-party has created 
[a very robust JSON library.](https://json.nlohmann.me/) The function
itself returns a json object and takes the pointer to the vector of
file content I have created. Due to the way I organize my notes, I can
store levels of context in strings, as every thing related to one 
season is stored in one place, as for everything in one epsiode, and
everything in an attribute specific to an episode. I can go one
direction and expect the structure of my notes to enable me to just
record what parent a given value belongs to. 

Making the If statements was simple. However, since this is C/C++, the
usual resources afforded to me by other high end languages did not
exist. I wrote utility functions to delete specific characters and to
trim the leading and trailing whitespace, but doing that made it
simple to implement. 

As for populating the JSON, being able to call values through a \[]
operator made it as simple as pie. 

I can not say the same thing for retrieving character, location, and
song lists. C++14 has set functionality, so that can take care of
keeping unique items for me. However, I could not figure out a way to
iterate through my JSON information for what I needed. After alot of
documentation and chat-gpt, I finally figured out how I could.

JSON Objects and Arrays from this library can be iterated through as an 
auto& type, with objects being iterated as item pairs, while arrays are
just values. In addition, I could not get it to work with a switch, but
using if-else conditions worked just fine.

Lastly, I had to save the JSON information to a folder, which involved
using some sort of file writing object to create and save the 
information.

I ran into issues with my C++ standard here, as a lot of information
on the internet recommended using the **filesystem** standard library.
However, this library was only introduced in C++17. This meant I had to
use basic concatanation to dynamically create the filepath I want,
which isn't as pretty as I would want, but gets the job done. 

From there, I could just create an ofstream variable, use it to open
new json and txt files, and write the manually created strings to each
file. 

Overall, using C++ was pretty easy once I figured out how to use it. 
However, CMake wouldn't work with me, and I have to be aware of
solutions I find on the internet as they may take advantage of features
introduced in later standards of C++. 

# Python 3.12 x JetBrains PyCharm

Around the time of C++2.0's release, another programming language began
to take form. Guido van Rossum started the implementation in 1989, with 
the language being named after _Monty Python's Flying Circus_. It was
intended to be a successor to ABC, which was a high-level language 
designed to reduce the amount of lines and content that a programmer
would need to create an application.

The first version ever released was 0.9.0, which included classes, 
classes with inheritance, exception handling, functions, and common
structures that we see today like list, str, and dict. Python would use
a Module system to organize sets of classes and methods.

By Python 1.0, additonal functional programming tools like lambda, 
reduce(), filter() and map() were added. van Rossum would move jobs to
the Corporation for National Research Initiatives (CNRI) and continue
developing the language, adding complex number support, keyword
arguments, and more.

Python 2.0 would release in 2000. From 2.1 and onward, it would be
owned by the Python Software Foundation and use a Python Software 
Foundation License. New features over time included list comprehension,
an improved garbage collector, nested scopes, type unification, and
context management with the `with` keyword.

Python 3.0 is the current major version of Python, and released in 2008.
It was designed to fix design flaws with Python 2.0 from the ground up,
at the cost of losing compatibility with Python 2.0 code. 

Over the entire timeline of Python's development, the core philosophy 
remained unchanged. Python syntax focuses on beautiful, simple,
readable code. The module system and the ability to easily create
classes emphasizes a solid foundation where anyone can create an 
expansive library with relative ease. This makes it a great teaching
tool - inspired by ABC's teachability - and a serious language good for
creating complex utilities and software.

Unlike C/C++, Python has an official 3rd-party repository to leverage
other people's work in PyPi. This allows creators to share their 
creations across the internet, resulting in packages such as Pandas,
PyTorch, and Seaborn becoming as crucial to the Python experience as
the core interpreter and base packages themselves.

## My experience with Python and PyCharm

# Java 23 x JetBrains IntelliJ

# C# (.Net 9.0) x Microsoft Visual Studio 22

# Go x Microsoft Visual Studio Code

# Rust x Microsoft Visual Studio Code

# Kotlin x Jetbrains IntelliJ

# Code Length

# A random note about Zig, Perl, and Ruby
