# Novel Nexus

*insert canva banner*

Welcome to Novel Nexus, a personal project that bridges my passion for reading with my technical skills in data science and database management.

**Purpose:**

Novel Nexus is a personal database project designed to catalog all the books I have read and own. This project combines my passion for reading with my interest in data science and database management. Through this project, I aim to:

 -Gain practice in designing and managing relational databases using SQL.

 -Develop proficiency in writing SQL queries, including joins, to extract meaningful insights.

 -Visualize data using Tableau to better understand my reading habits and behaviors.

 -Maintain a detailed record of my books for personal reference and analysis.

**Table of contents:**
1. Introduction
2. Process
3. Data Description
4. Included Files
5. Future Enhancements


**1. Introduction**

As an avid reader who enjoys analyzing patterns, I wanted a way to catalog my collection of books while gaining hands-on experience with relational databases and data visualization. This project allows me to develop and practice my skills in Python, SQL, Excel, and Tableau while exploring my reading habits and preferences. Novel Nexus is not just a functional database but also a tool for self-reflection and growth as I analyze my reading behaviors over time and make informed decisions about future book choices.

Keep reading to explore how I built this project, the data it includes, and the tools I'm using to bring it to life!

**2. Process**

Novel Nexus began as a csv export of my goodreads library (the only books record I had kept up until that point). The initial csv file was horrendous, and included unneccessary and innacurate information on books that I did not read or own, and I realized that much of my data would have to be input manually. I created an ER Diagram for my database, and produced excel sheets (my future SQL tables) with columns based off of that information. 

After inputting my data on Excel, I opened the workbook using Tableau and created a series of visuals that capture patterns and relationships within my dataset.

**3. Data Description**


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
 

CHALLENGES:\
keeping fname and lname together, in this instance, author names, especially across different cultures may not be in this format, many authors also use middle initials.\
additional authors table, its not common for books I read to have more than 1 author, so this table contains additional authors of books I have read UPDATE NOT NECESSARY, all authors go into author table.\
 \
altering data types, creating a new enum data type to hold the formats, changing isbn from INT to varchar to accommodate for kindle digital and audio isbns which may contain non numerical characters.\
 \
creating new page_count table to account for some books that do not have pages aka audiobooks.\
 \
Choosing rankings categories that I can apply to everything I have read (no null values for ratings) and defining a point system (5 pts per category, half values accepted, scale is 1-5) UPDATE: no need for half values, as I am rating- I am able to assign whole numbers quite easily.\
 \
*Defining my ratings categories:*

Plot: How much did I enjoy the overall story progression and conclusion? What was its entertainment value?

Writing: How much did i enjoy the writing and dialogue?

Pacing: did the book feel sluggish and difficult to get through at times?

Impact: How much did reading this book impact me? This includes physical reactions while reading (laughter, tears, gasps) as well as how much I found myself thinking about the book after reading it.

Personages: How much did I enjoy the character(s)/characterization?

Re-readability: How likely is it that I would re-read this book and enjoy it? This is an incredible important category as it is the factor that often separates the great books from the favorite books.

Immersivity: Did I become immersed in the story and forget about the real world while reading this? Was I transported?



NOTE: I have only included ratings for books that I felt I could provide accurate ratings on. I have also only included books that I recorded the read date for in the date_read table. Hence, the overall books table contains books I have read, but I may not be alble to include them in additional more detailed tables.
 
 12-13-2024 changes: isbn --> read_isbn for books table to record the specific book read- library_isbn attribute added to my_library table to account for books that I own that I have read in a different format.\

 12-15-2024 changes: using excel functions to streamline manual data entry, aggregate calculations, custom functions, removing characters.\
 adding isbn for copies that I currently own- for some books i have more than one copy in more than 1 different format. This will help me differenciate copies.\

 Thank you for exploring the Novel Nexus project! This project not only reflects my enthusiasm for reading but also showcases my technical skills in data management and visualization. If you have feedback or suggestions, feel free to reach out as I am always making updates and improvements!
