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

# The Criteria/Topics
