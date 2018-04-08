# Myers Briggs Personality Type Natural Language Processing Project

## Inspired by the Kaggle competition [here](https://www.kaggle.com/datasnaek/mbti-type)

### Introduction
My name is Nathan Fritter and I am obsessed with data. I have a B.S. in Applied Statistics from UCSB and was an active member of the Data Science club @ UCSB. I have completed numerous projects utilizing various methods, have presented my findings to others and sat on the executive board of the club. Feel free to take a look at any and all other projects and make suggestions. 

### The Project
This project is based on the Kaggle competition linked above. Tweets from various accounts on Twitter (all with an accompanying personality type) were gathered together; each account has anywhere from a couple to 20+ tweets each. 

My goal here is to remove the noise (stop words), categorize the data (tokenize), and use things such as word frequencies and sentence orientation to try and predict the personality type of the user. 

I have attempted to make comments outlining my thought process. Feel free to clone the repo, make a branch, leave comments or contribute in any way you'd like.

### What is the Myers Briggs Personality Type?

The Myers Briggs Personality Type is based on psychological theory around how people perceive their world and then make accompanying judgements about these perceptions. 

It is a rather simplistic view, but one that does have surprising effectiveness at predicting people's behaviors in general when taking into account the limitations of the theory. There are four categories:

+ Extroverted/Introverted (E/I):
	+ Rather than the mainstream view that this distinction means talkative versus antisocial (and other similar variations), this difference actually stems from where one derives their energy from.
		+ Extroverts gain energy from being around other people: talking, conversing, being noticed, etc. They are capable of being alone, but will get tired out without contact with others.
		+ Introverts gain energy from being alone. Being alone and allowed to let their thoughts flow is very energizing, and allows one to clear their head (coming from personal experience). Opposite to extroverts, introverts have the capability to socialize and be the center of attention quite effectively; but after a while, even a five minute break alone may be necessary.

+ Intuitive/Sensory (N/S):
	+ Here, the differences lie in how the individual perceives their world. The two domains here are either through the five senses (immediate environment) or within their mind.
		+ Intuitives (N) are better at perceiving their world through their mind and imagining possibilities in the world. 
		+ Sensories (S) are better at perceiving their world through their five senses

+ Thinking/Feeling (T/F):
	+ This domain deals with how the individual judges the information they have perceived: Either the individual makes judgments in a Thinking (T) way or a Feeling (F) way
		+ Thinkers make conclusions about their world through logic and reasoning
		+ Feelers make conclusions about their world through emotion and gut feeling

+ Judgmental/Perceiving (J/P):
	+ Lastly (and a little more complicated), this domain basically states whether the perceiving trait or the judging trait is the dominant trait of the individual
		+ Judgers (J) will have their judging trait be their dominant overall trait
		+ Perceivers (P) will have their perceiving trait be their dominant overall trait

[Here](http://www.myersbriggs.org/my-mbti-personality-type/mbti-basics/) is more in depth detail on the theory and the complexities behind it. 

### General Analysis & Findings
In a sentiment analysis project, there are some limitations on the types of analysis one can do. What we CAN do, is things like word frequencies/clouds, label frequencies, remove stop words and analyze

#### Word Frequencies (Top 25; no change after stop words are removed) 

|  Word  | Frequency |
| ------ | --------- |
|  Like  |   69675	 |
|  Think |   49836	 |
|  People |  47854  |
|  One |  37166  |
|  Know |  36934  |
|  Really |  35291  |
|  Would |  35015  |
|  Get |  30804  |
|  Time |  27610  |
|  Feel |  23336  |
|  Much |  23120  |
|  Well |  22928  |
|  Love |  21030  |
|  Good |  20719  |
|  Things |  20487  |
|  Say |  20267  |
|  Way |  19653  |
|  Something |  19538  |
|  Want |  19378  |
|  See |  19134  |
|  Also |  18330  |
|  Type |  17149  |
|  Even |  16914  |
|  Always |  16809  |
|  Lot |  16440  |


#### Label (Personality Type) Frequencies

|  Type  |  Frequency  |
|  ----  |  ----- |
| ENFJ   |   190  |
| ENFP   |   675  |
| ENTJ   |   231  |
| ENTP   |   685  |
| ESFJ   |   42  |
| ESFP   |   48  |
| ESTJ   |   39  |
| ESTP   |   89  |
| INFJ   |   1470  |
| INFP   |   1832  |
| INTJ   |   1091  |
| INTP   |   1304  |
| ISFJ   |   166  |
| ISFP   |   271  |
| ISTJ   |   205  |
| ISTP   |   337  |


Clearly this may be an issue down the line; "INFP", "INFJ", "INTP", and "INTJ" shows up the most, and disproportionally so. Because of this, there will likely be something called "class imbalance", 

### Steps to Reproduction

+ Clone the repo onto your machine (instructions [here](https://help.github.com/articles/cloning-a-repository/) if you are not familiar)
+ Download the package `virtualenv`
	+ Assuming you have made it this far you should have experience with one of `pip/pip3`, `brew` or another package manager
	+ Here we will use `pip3` (python3 compatible)
+ Run the following commands:
	+ `virtualenv venv` 
		+ This creates a virtual environment called "venv"
		+ Feel free to change the second word to whatever you'd like to call it
	+ `source venv/bin/activate` 
		+ This turns on the virtual environment and puts you in it
	+ `pip3 install -r requirements.txt`
		+ Installs every python package listed in the requirements.txt file
	+ `python3 NLPAnalysis.py *text*`
		+ Examine the code at the bottom of each part
		+ Replace *text* with whichever part you'd like to run
		+ E.g. "tokenize" to tokenize data, "cloud" to create a word cloud, etc.

### Contributing

If you would like to contribute:
+ Create a new branch to work on (instructions [here](https://github.com/Kunena/Kunena-Forum/wiki/Create-a-new-branch-with-git-and-manage-branches))
	+ By default the branch you will receive after cloning is the "master" branch
	+ This is where the main changes are deployed, so it should not contain any of your code unless the changes have been agreed upon by all parties (which is the purpose of creating the new branch
	+ This way you must submit a request to push changes to the main branch)
+ Submit changes as a pull request with any relevant information commented
	+ Reaching out in some way would also be great to help speed up the process

If you do contribute, I will add your name as a contributor!

### Iterations

This project is a work in progress; first it started as an ipython notebook on Kaggle, then I translated the work to a script.

It initially started with no functions just to make sure that it worked. however, I have now separated out the parts into different functions, allowing for the user to input what part they'd like to run. 

I will attempt to implement "try/except" functions as well; will update.

Also, there are some parts that do not work (word cloud, word frequencies) because for whatever reason, the tokenization is happening at the letter level rather than the word level. Will investigate and update as well.

### Sources Cited

+ Will update