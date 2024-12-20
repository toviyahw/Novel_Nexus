<img width="960" alt="novel_nexus" src="https://github.com/user-attachments/assets/a1c0be0f-2fba-4fe4-8583-5c25fe18756d" />  

### *Welcome to Novel Nexus, a personal project that bridges my passion for reading with my technical skills in data science and database management.*

## Purpose

Novel Nexus is a personal database project designed to catalog all the books I have read and own. This project combines my passion for reading with my interest in data science and database management. Through this project, I aim to:

* Gain practice in designing and managing relational databases using SQL.
* Develop proficiency in writing SQL queries, including joins, to extract meaningful insights.
* Visualize data using Tableau to better understand my reading habits and behaviors.
* Maintain a detailed record of my books for personal reference and analysis.

## Table of contents
1. Introduction
2. Process
3. Data Description
4. Included Files
5. Future Enhancements


## 1. Introduction

As an avid reader who enjoys analyzing patterns, I wanted a way to catalog my collection of books while gaining hands-on experience with relational databases and data visualization. This project allows me to develop and practice my skills in Python, SQL, Excel, and Tableau while exploring my reading habits and preferences. Novel Nexus is not just a functional database but also a tool for self-reflection and growth as I analyze my reading behaviors over time and make informed decisions about future book choices.

Keep reading to explore how I built this project, the data it includes, and the tools I'm using to bring it to life!


## 2. Process

Novel Nexus began as a csv export of my goodreads library (the only books record I had kept up until that point). The initial csv file was horrendous, and included unneccessary and innacurate information on books that I did not read or own, and I realized that much of my data would have to be input manually. I created an ER Diagram for my database, and produced excel sheets (my future SQL tables) with columns based off of that information. I 

Using Python, I will check my dataset for duplicates and NULL values and clean it using pandas before transforming the dataset into a dataframe to create visuals using various Python libraries.

After inputting my data on Excel, I was able to clean it up and complete menial tasks such as calculating scores and removing unneccessary characteres using functions. I connected my finalized workbook data to Tableau and created a series of visuals that capture patterns and relationships within my dataset.

Using my terminal and pgAdmin4 I will create tables and insert my data into a PostgreSQL database. Then I will perform joins that give me insights into my reading and book buying habits.

Novel Nexus is a work in progress and will be updated frequently as I am in the earlier stages of building on this project.


## 3. Data Description

### My Tables

1. **books_read -->** (book_id, title, isbn, page_count, start_date, end_date, year)\
*Table contains general information on the book*
 
2. **authors_read -->** (author_id, book_id, author_name) {Books may have more than one author, so a unique idenifier is needed.}\
*Table contains author(s) of a book*

3. **date_read -->** (date_read_id, book_id, start_date, end_date, read_duration) {The same book may be read more than once, so a unique idenifier is needed.}\
*Table contains information on when I read the book*

4. **genres_read -->** (genre_id, book_id, genre) {Books may belong to more than one genre, so a unique idenifier is needed.}\
*Table contains the genre(s) a book belongs to*

5. **format_read-->** (book_id, format) format types: 'audio', 'paperback', 'hardcover', 'digital'\
*Table contains information on what format the book was read in.*

6. **series_read -->** (series_id, series_name, book_number){Books may belong to more than one series, so a unique idenifier is needed.}\
*Table contains information on books that belong to one or more series.*

7. **my_library -->** (library_id, book_id, price, isbn)\
*Table contains information on books I own physical copies of.*

8. **gr_scores -->** (book_id, avg_gr_rating, calculated_score)\
*Table contains information on the average Goodreads score of books I have read. This table will allow me to see the relationship between my personal rankings and that of Goodreads.*

9. **ratings -->** (book_id, plot, writing, pacing, personages, impact, re-redability, immersivity, overall_score, calculated_score)\
*Table contains individual scores (0-5) for different categories as well as calculated overall scores. See below for descriptions of individual rating categories.*

### Rating Category Descriptions:

**Plot:** How much did I enjoy the overall story progression and conclusion? What was its entertainment value?

**Writing:** How much did i enjoy the writing and dialogue?

**Pacing:** did the book feel sluggish and difficult to get through at times?

**Impact:** How much did reading this book impact me? This includes physical reactions while reading (laughter, tears, gasps) as well as how much I found myself thinking about the book after reading it.

**Personages:** How much did I enjoy the character(s)/characterization?

**Re-readability:** How likely is it that I would re-read this book and enjoy it? This is an incredible important category as it is the factor that often separates the great books from the favorite books.

**Immersivity:** Did I become immersed in the story and forget about the real world while reading this? Was I transported?

**Overall_score:** This is the sum of all scores for a book across the 7 categories.

**Calculated_score** This is the overall score calculated as a percentage. This will allow me to compare my rating to the average on Goodreads.

**NOTE:** I have only included ratings for books that I felt I could provide accurate ratings on. In the dates_read table I have only included books that I had accurately recorded the read date for. The overall books_read table contains books I have read, but not every book in this table will recieve a score or assigned read dates. ISBN numbers for books_read and my_library may differ, as sometimes I read a digital or audio version of a book I own.


## 4. Included Files
* Readme.md: Outlines project goals, processes, and dataset details.
* Tableau Visuals: Hosted on adjacent site. *{To be uploaded}*
* PostgreSQL Documentation: A file containing the queries I wrote to create my tables, insert my data, and joins executed. *{To be uploaded}*
* EDA with Python: An .ipynb file outlining the process of cleaning my data, loading it into a dataframe, and performing exploratory data alaysis using various python libraries. *{To be uploaded}*

## 5. Future Enhancements
After initial completion, I will update the SQL database and Excel sheets monthly at a minimum as I continue to read. By continuing to populate Novel Nexus, I will be able to produce more robust visuals and draw more accurate insights surrounding my reading habits over time.

## TABLEAU VISUALS PREVIEW
**NOTE: Pardon the construction, this project is still in the works! The images below are only a static look at some of the early visuals created for Novel Nexus. This section will be removed upon the upload of the complete set of finalized dynamic visuals.**
<img width="1440" alt="Pages Read" src="https://github.com/user-attachments/assets/1cb3b238-2176-4970-a9d1-0a8580f19c54" />
<img width="375" alt="Formats Read" src="https://github.com/user-attachments/assets/7028ee5b-771a-406c-9db6-d6e2f025b4b0" />
<img width="239" alt="Page Count Stats" src="https://github.com/user-attachments/assets/20e86730-967a-4b4a-9d4b-7ac166367bed" />
<img width="1440" alt="Scores Comparison" src="https://github.com/user-attachments/assets/6bee4f0b-b910-40bf-9d3c-f072e26e3e8f" />
<img width="1440" alt="Genres Read" src="https://github.com/user-attachments/assets/6cb4d756-155f-4444-9346-1df335b4d402" />




**Thank you for exploring the Novel Nexus project! If you have feedback or suggestions, feel free to reach out as I am always making updates and improvements!**
