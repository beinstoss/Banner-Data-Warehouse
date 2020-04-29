Final Presentation Outline
======

## Early Scoping

- First efforts were concentrated on understanding the data that lived within the three csv files provided.
    - Course Catalogs
    - Course Meetings
    - Course Offerings

- The [CourseDataDictionary](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/docs/CourseDataDictionary.md) contains the definitions of each field within the three files mentioned above. The fields in the dictionary are segmented by the database tables in which the field lives in, these tables will be created within __Step 1__ of this process.


## Step 1: Creation of CourseData.db

-  After analyzing the raw data, we began to build the ERD schema for our database. The final output contained the following 7 tables normalized down to BCNF.
    - PROGRAMS
    - CATALOG_COURSES
    - TERM_TO_CATALOG_YEAR
    - COURSE_OFFERINGS
    - COURSE_MEETINGS
    - COURSE_INSTRUCTORS
    - COURSE_LOCATIONS

- Click [here](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/docs/CourseDataERD.pdf) to access the CourseDataERD pdf file containing the ERD schema for CourseData.db

- Using the ERD Schema as a guide, we began the [CourseData.db ETL process](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/CourseDataETL.ipynb) in order to "Extract, Transform and Load" from the raw csv files into the CourseData.db.

## Step 2: Test CourseData.db

- Now that we have build our database, testing is required to check for possible issues around:
    - Domain Integrity
    - Entity Integrity
    - Relational Integrity

- [CourseData.db Integrity Testing](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/CourseDataTests.ipynb)

## Step 3: Create CourseDataWarehouse.db Using Star Schema

- The purpose of the CourseDataWarehouse.db Star Schema is to answer user specific questions and make rollup queries as simple as possible.
    - The users of our Data Warehouse include Fairfield University Deans, Department Chairs and Program Directors.

- Since the data being used for the CourseDataWarehouse.db is coming from the CourseData.db, we are already familiar with the data and can proceed to creating our Fact Table ERD which contains the following tables:
    - FACT_TABLE
    - INSTRUCTOR_DIMENSION
    - CATALOG_DIMENSION
    - LOCATION_DIMENSION
    - TIME_DIMENSION
    - COURSE_DIMENSION

- Using the [Fact Table ERD](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/docs/Fact_Table.pdf) as a guide, we can now create the necesseray tables for our Data Warehouse, as well as extract data from CourseData.db in order to populate these tables. This process can be seen [here](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/CourseDataWarehouse.ipynb).

## Step 4: Test CourseDataWarehouse.db

- Now that we have created and populated the CourseDataWarehouse.db, we must now test the integrity of the data with the same type of checks that were ran on __Step 2__ of this process.

- [CourseDataWarehouse.db Integrity Testing](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/CourseDataWarehouseTests.ipynb)

## Step 5: Demo CourseDataWarehouse.db

- We have now succesfully created and tested our CourseDataWarehouse.db and have created some demo queries as examples of possible real-world use cases for this Data Warehouse.

- [CourseDataWarehouse.db Demos](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/CourseDataWarehouseDemo.ipynb)

The End.. Thanks!
======