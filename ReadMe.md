Final Presentation Outline
======

## Early Scoping

- First efforts were concentrated on understanding the data that lived within the three csv files provided.
    - Course Catalogs
    - Course Meetings
    - Course Offerings

- Click [here](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/docs/CourseDataDictionary.md) to access the CourseDataDictionary containing the definition of each field within the three files mentioned above.


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

- Click [here](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/CourseDataTests.ipynb) to access the CourseData.db integrity checks.

## Step 3: Create CourseDataWarehouse.db

- Step 2: [Test CourseData.db](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/CourseDataTests.ipynb)

- Step 3: [Create CourseDataWarehouse.db Using Star Schema](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/CourseDataWarehouse.ipynb)

- Step 4: [Test CourseDataWarehouse.db](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/CourseDataWarehouseTests.ipynb)

- Step 5: [Demo CourseDataWarehouse.db](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/CourseDataWarehouseDemo.ipynb)

## Supplemental Docs

- [CourseDataERD]

- [FactTableOne](https://github.com/fairfield-ba510-spring2020/term-project-sql/blob/master/docs/fact-table-one.pdf)

- 