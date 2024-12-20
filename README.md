<img width="960" alt="novel_nexus" src="https://github.com/user-attachments/assets/a1c0be0f-2fba-4fe4-8583-5c25fe18756d" />  

### *Welcome to Novel Nexus, a personal project that bridges my passion for reading with my technical skills in data science and database management.*

## Purpose

Novel Nexus is a personal database project designed to catalog all the books I have read and own. Through this project, I aim to:

* Gain practice in designing and managing relational databases using SQL.
* Develop proficiency in writing SQL queries, including joins, to extract meaningful insights.
* Visualize data using Tableau to understand my reading habits and behaviors better.
* Maintain a detailed record of my books for personal reference and analysis.

## Table of contents
1. Introduction
2. Process
3. Data Description
4. Included Files
5. Future Enhancements


## 1. Introduction

As an avid reader who enjoys analyzing patterns, I wanted a way to catalog my collection of books while gaining hands-on experience with relational databases and data visualization. This project allows me to develop and practice my skills in Python, SQL, Excel, and Tableau while exploring my reading habits and preferences. Novel Nexus is not just a functional database but also a tool for self-reflection and growth as I analyze my reading behaviors over time and make informed decisions about future book choices.

Keep reading to explore how I built this project, the dataset details, and the tools I'm using to bring it to life!


## 2. Process

Novel Nexus began as an Excel sheet containing a single CSV export of my Goodreads library (the only book record I had intentionally kept up until that point). The initial CSV file was cluttered- while also providing little of the information I needed. It included unnecessary and inaccurate information on books that I did not read, intend on reading, or own, and I realized that much of my data would have to be input manually. Many of the versions of the books I read had incorrect ISBNs, so I had to update those with the correct ISBNs and associated publishing years. I also removed the many rows of information on books that I had not read until all that was left were books I recorded as read on the Goodreads site. Books that I have read that were not recorded on Goodreads were then input manually. I was also able to combine my archived Libby App information to input records on dates I started and finished audiobooks.

Data input for the my_library table was completely manual as I needed an accurate record of Titles and ISBNs (some of the books I have physical copies of have been read digitally or via audio, so the ISBNs from the table containing information on the books I have read could not be used). As for price, many of my books were purchased online through various retailers, and the majority were purchased quite recently. Using online order records and my memory, I was able to input dollar amounts that provide an approximate value to all of the books in my library. For the few titles that I had no recollection of purchasing and no online record of, the price listed on the physical copy of the book was used instead.

After inputting my data into Excel, I was able to clean it up and complete menial tasks such as calculating scores and removing unnecessary characters using functions. I connected my finalized workbook data to Tableau and created a series of visuals that captured patterns and relationships within my dataset.

With Python, I will check my dataset for duplicates and NULL values and clean it using Pandas before transforming the dataset using Pandas to create visuals using various Python libraries.

Using my terminal and pgAdmin4 I will create tables and insert my data into a PostgreSQL database. Then I will perform joins that answer specific questions and produce additional insights into my reading and book-buying habits.

Novel Nexus is a work in progress and will be updated frequently as I am in the earlier stages of building on this project.


## 3. Data Description

### My Tables

1. **books_read --> (book_id, title, isbn, page_count, start_date, end_date, year)**\
*Table contains general information on the book*
 
2. **authors_read --> (author_id, book_id, author_name)** {Books may have more than one author, so a unique identifier is needed.}\
*Table contains author(s) of a book*

3. **date_read --> (date_read_id, book_id, start_date, end_date, read_duration)** {The same book may be read more than once, so a unique identifier is needed.}\
*Table contains information on when I read the book*

4. **genres_read --> (genre_id, book_id, genre)** {Books may belong to more than one genre, so a unique identifier is needed.}\
*Table contains the genre(s) a book belongs to*

5. **format_read--> (book_id, format)** format types: 'audio', 'paperback', 'hardcover', 'digital'\
*Table contains information on what format the book was read in.*

6. **series_read --> (series_id, series_name, book_number)** {Books may belong to more than one series, so a unique identifier is needed.}\
*Table contains information on books that belong to one or more series.*

7. **my_library --> (library_id, book_id, price, isbn)**\
*Table contains information on books I own physical copies of.*

8. **gr_scores --> (book_id, avg_gr_rating, calculated_score)**\
*Table contains information on the average Goodreads score of books I have read. This table will allow me to see the relationship between my rankings and that of Goodreads.*

9. **ratings --> (book_id, plot, writing, pacing, personages, impact, re-readability, immersivity, overall_score, calculated_score)**\
*Table contains individual scores (0-5) for different categories as well as calculated overall scores. See below for descriptions of individual rating categories.*

### Rating Category Descriptions:

**Plot:** How much did I enjoy the overall story progression and conclusion? What was its entertainment value?

**Writing:** How much did I enjoy the writing and dialogue?

**Pacing:** Did the book feel sluggish and difficult to get through at times?

**Impact:** How much did reading this book impact me? This includes physical reactions while reading (laughter, tears, gasps) as well as how much I found myself thinking about the book after reading it.

**Personages:** How much did I enjoy the character(s)/characterization?

**Re-readability:** How likely is it that I would re-read this book and enjoy it? This is an incredibly important category as it is the factor that often separates the great books from the favorite books.

**Immersivity:** Did I become immersed in the story and forget about the real world while reading this? Was I transported?

**Overall_score:** This is the sum of all scores for a book across the 7 categories.

**Calculated_score** This is the overall score calculated as a percentage. This will allow me to compare my rating to the average on Goodreads.

**NOTE:** I have only included ratings for books that I felt I could provide accurate ratings on. In the dates_read table, I have only included books that I had accurately recorded the read date for. The overall books_read table contains books I have read, but not every book in this table will receive a score or assigned read dates. ISBNs for books_read and my_library may differ, as sometimes I read a digital or audio version of a book I own.


## 4. Included Files
* Readme.md: Outlines project goals, processes, and dataset details.
* Tableau Visuals: Hosted on an adjacent site. *{To be uploaded}*
* PostgreSQL Documentation: A file containing the queries I wrote to create my tables, insert my data, and the executed joins. *{To be uploaded}*
* Finalized Cleaning and EDA with Python: An .ipynb file outlining the process of cleaning my data, loading and transforming it, and performing exploratory data analysis using various Python libraries. *{To be uploaded}*

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
