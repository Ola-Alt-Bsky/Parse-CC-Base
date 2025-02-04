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

Without further ado, lets cover the combination that made me realize
this project was possible.

# Python 3.12 x JetBrains PyCharm


