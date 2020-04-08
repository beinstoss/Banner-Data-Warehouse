## PROGRAMS
- ProgramID: 
- ProgramCode
- ProgramName

## COURSE_CATALOG
-
-
-
-
-
-
-
-
-
-
-


## TERM_TO_CATALOG_YEAR
-
-


## COURSE_OFFERINGS
- CourseOfferingID: Surrogate Key serving as Primary Key for the COURSE_OFFERINGS table. Also found as a Foreign Key within the COURSE_MEETINGS table.
- CourseID: Primary Key for the CATALOG_COURSES table being used as a Foreign Key within the COURSE_OFFERINGS table.
- CatalogID: ID that represents a identifies a specific course. This is not a unique ID in most cases due to the common practice of having multiple sections of the same course being offered within the same term.
- Term: Identifies the time frame (in seasonal form) for which the data is taking place within. format = {season}{year} 
- CRN: 
-
-
-
-
-
-
-
-

## COURSE_INSTRUCTORS
-
-

## COURSE_MEETINGS
-
-
-
-
-

## COURSE_LOCATIONS
-
-
