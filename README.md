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
basic compiler maker. 

# C++ 14 x Microsoft Visual Studio 22

This is techincally the oldest language I used for this project.

# Python 3.12 x JetBrains PyCharm

# Java 23 x JetBrains IntelliJ

# C# (.Net 9.0) x Microsoft Visual Studio 22

# Go x Microsoft Visual Studio Code

# Rust x Microsoft Visual Studio Code

# Kotlin x Jetbrains IntelliJ

# A random note about Zig, Perl, and Ruby
