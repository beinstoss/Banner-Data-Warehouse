# BA 510 Course Data Project
__Spring 2020__

## Objectives
In this project you will ...
- Extract, translate, and load data into a normalized database of your own design
- Design and populate a (read-only) data warehouse designed to address common analytical questions
- Test your databases to ensure domain, entity, relational integrity
- Demonstrate that the course objectives have been met  
- Work in small teams, sharing code and data files equally

## Expectations
- You will be given time to work on this in class. However, expect to also do some work at home.

- Each student should be able to fully present the work of her/his team. While it is on your honor to share the load with your teammates, the instructor ask individuals to present separately from the team in private. These private presentations will be graded separately from the rest of the team.

- __All work is due in your team GitHub repository by 10pm the night before our final class period.__

## Instructions
__0. Form teams of 2-3 students each.__

- You may select whoever you like to be on your team.
- A GitHub classroom link will be provided on the class agenda. Use it to create a shared repository. If you need help with this step, just ask.
- Note to experienced Git users: __Use GitHub classroom as directed. Do not try to manage your team roster by adding collaborators in GitHub. Use the GitHub Classroom link like everybody else.__

__1. Study the Source Data.__  
Inside the `SourceData` folder is a large number of subfolders:

- `AcademicCalendars` and `Catalogs` folders contain printable PDF files that cover the years 2014-2019. You will also find a couple of CSV files in the `Catalogs` folder that you will need to import into your database.
- The rest of the folders (`Fall2014`, `Winter2015`,`Spring2015`, etc.) contain course offering data for every academic term since Fall 2014. Each folder contains:    
    - `banner.html`: a dump of the data scraped from Banner Web
    - `cal_rules.yaml`: configuration rules that account for holidays, schedule shifts, etc. (Note: YAML is actually a standard! Look it up.)
    - `course_meetings.csv`: a CSV-formatted table of class meetings, one line per meeting
    - `course_offerings.json`: a JSON-formatted extract all data extracted from the banner.html file; this is used to generate the final CSV files
    - `courses.csv`: a CSV-formatted table of course data
    - `Calendars`: a folder of ical files, one per course (CRN) that can be directly imported into any standard calendaring software; it has been tested with Outlook (Exchange), Mac Calendar (iCloud), and Google Calendar

__Please take time to get to know these files.__ If you find any bugs in the source data files report them [here](https://github.com/christopherhuntley/ba510-course-data-project/issues).

__2. Design a normalized relational database that can contain all CSV data in your `SourceData` repository. Document the design with an ERD and a data dictionary.__

- The database should not leave off any files or columns.
- Normalize to at least BCNF.
- The ERD should be a PDF file named "CourseDataERD.PDF" to be dropped in the `docs` folder.
- Also in the `docs` folder, add a Markdown-formatted `CourseDataDictionary.md` file that defines every column on every table. Use the table names as second level headings (`##`) and bullet lists for the column definitions. If you are feeling frisky, then perhaps use Markdown tables instead of bullet lists.  
- Take care with the [Markdown formatting](https://github.github.com/gfm/). Dropping big, stupidly-formatted blobs of text is very bad form. It's also extremely unprofessional.

__3. Create a SQLite database called `CourseData.db` in this folder. The database should exactly match your ERD. Populate the database with data from the CSV files.__

- CSV files are best imported using the SQLite3 tool we discussed in class. Experiment with it to get the imports right before writing any SQL.
- You will likely have to import the CSV file data into tables that you will ultimately drop when the database is completed. To keep track of them all, please the prefix the table name with `import_` to indicate that the table contains raw source data.
- Use SQL to create and populate the tables in your ERD. The code will likely look a lot like what we did in class, with lots of JOINs. You should implement FOREIGN KEY constraints (With cascading updates/deletes) as well.
- Capture all of your SQL DDL and DML code in a new notebook called `CourseDataETL.ipynb` in this project folder. Use Markdown to annotate your work as you go along. Also, make sure you can re-run your code from scratch to rebuild the database when needed.

__4. Test the integrity of your new `CourseData.db` database.__

- Create a new notebook called `CourseDataTests.ipynb`.
- Write queries to ensure that  ...
    - Each column has a sensible data type (Domain integrity); are there truncation or translation errors?   
    - Each row describes a unique entity (Entity integrity); just having a PK is not enough: you will need to look for duplicate a data records
    - Each relationship is implemented correctly (Relational integrity); are the FKs JOIN-compatible with the PKs? does each mandatory relationship have a corresponding NOT NULL constraint?
- Annotate your queries in Markdown cells so we know what you are testing and why.

__5. Design and build data warehouse called `CourseDataWarehouse.db`.__

- Use a star schema design. The idea is to make writing 'rollup' queries with SELECT ... FROM ... WHERE ... GROUP BY as easy as possible. The dimension FKs are likely redundant -- they can be usually be inferred from other table relationships -- but often eliminate the need for complex JOINs.
- Document each fact table (and associated dimensions) as a separate ERD. Each ERD should be named using the pattern `fact-table-name.pdf` and contain no spaces or other unnecessary punctuation. Store the PDF files in the `docs` folder.
- You will need to figure out how to extract data from `CourseData.db` in order to insert it into `CourseDataWarehouse.db`.

__6. Test your `CourseDataWarehouse.db` for data integrity.__

- This is pretty much the same process as you used for the first database.
- Call your new notebook `CourseDataWarehouseTest.ipynb`.

__7. Demo your results with useful queries.__

- Create yet another new notebook called `CourseDataWarehouseDemo.ipynb` that illustrates the usefulness of the data warehouse with a few informative queries.
- Number the queries so we can refer to them by number later. (In other words, make sure your queries have entity integrity.)
- In your Markdown include remarks about why, when, and how the query might be used in practice. If your query results suggest anything insightful, then include a cell below the query results with Markdown-formatted remarks.

__8. Deliver a walkthrough presentation of your work.__

- Add a Markdown-formatted `Readme.md` file with a step-by-step tour of your work, including links to files as needed.
- You will have exactly 10 minutes to present your work in class. There will be no Q&A, but each team is expected to peer review every other team's work with the an online form provided just prior to the final class session.  
- There are no slides for presentation itself. Just walk us through your work using your `Readme.md` file. What ever you do, please do not try to _sell_ your work. The purpose of the walkthrough is to review the work for completeness, relevance, and professionalism. If you have met the course objectives, then your work should stand on its own.
