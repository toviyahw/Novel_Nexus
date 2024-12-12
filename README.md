# Novel Nexus

A collection of the many chapters I have read, over the course of the many different chapters of my life.\

*create canva banner*

Potential entities:\

book table --> (book_id, title, isbn, page_count, start date, end date)\
 \
authors table -->(book_id, name) {BOOKS MAY HAVE MANY AUTHORS}\
 \
genre table --> book_id, genre {BOOKS MAY HAVE MANY GENRES}\
 \
ratings table --> (book_id, plot, writing, pacing, characters, impact, re-redability, immersivity,\
 \
tags table --> (book_id, tag) TAGS:(childhood favorite, one of my favorites OMF, one-sitting (for books that were unputdownable), tearjerker, laughed-out-loud, mind-blown, called-it, never-again, reread-worthy, gut-wrenching, what-just-happened, slump-inducing, thought-provoking) {BOOKS MAY HAVE MANY TAGS}\
 \
format table (book_id, type) TYPES: audio, digital, physical
 \
owned_copies --> (book_id, price)\
 \
***MAYBE***\
awards table (nominations, awards, year)\
Series table (# books included in series, start and end date for series)\
 \
Why was this necessary, no platform provides ratings on what I really care about, this is custom made for me, and will help me understand my reading habits and behaviors, as well as serve as a display of how my reading habits and tastes evolve over time. Goodreads is garbage.\
 \
rating books on a scale from 1-5 and writing a breif 
 \
Whenever I tell someone I love to read books, the question that typically follows is "What's your favorite book?", and thats the part where I freeze and spiral. A question that haunts me relentlessly because the truth is, I could not even begin to answer that. There are too many favorites, for too many different reasons, that change too often. So- instead I wrote this SQL query that will tell me what my current "favorite" is, and I will have a quick and easy answer to that dreaded question that I could never conjure up an answer to on my own.
 \
Stored procedure ideas: favorite ever, best of the month BOM, best of the year, average reading time, average pages read, totals for these, best in each genre, best series, total days read, best audio, physical, hardcover, digital AND MOST IMPORTANTLY my 'favorite' book. total books read, and by each genre.\
 \
GENRES:\
thriller\
horror\
mystery\
romantasy\
fantasy\
romance\
lit-fic\
contemp-fic\
non-fiction\
historicalfic\
rom-com\
sci-fi\
dystopian\
action-adventure\



CHALLENGES:\
keeping fname and lname together, in this instance, author names, especially across different cultures may not be in this format, many authors also use middle initials.\
additional authors table, its not common for books I read to have more than 1 author, so this table contains additional authors of books I have read\
 \
altering data types, creating a new enum data type to hold the formats, changing isbn from INT to varchar to accommodate for kindle digital and audio isbns which may contain non numerical characters.\
 \
creating new page_count table to account for some books that do not have pages aka audiobooks.\
 \
Choosing rankings categories that I can apply to everything I have read (no null values for ratings) and defining a point system (5 pts per category, half values accepted, scale is 1-5)\
Defining my ratings categories:\
plot: how much did I enjoy the overall story progression and conclusion?\
writing: how much did i enjoy the writing and dialogue?\
impact: how much did reading this book actually affect me?\
characters: how much did I enjoy the character(s)?\
originality: is this unlike anything I have ever read, or did it feel familiar and predictable? (As an avid reader, this category is extrememly important to me. I love it when I feel like i have just read something completely fresh and new to me!\
re-readability: how likely is it that I would re-read this book and enjoy it?\
immersivity: did I forget about the real world while reading this? was I transported? (another big category for me)\
