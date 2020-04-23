## PROGRAMS
- ProgramID: Primary Key for the PROGRAMS table being used as a Foreign Key within the COURSE_CATALOG table.
- ProgramCode: Two-letter code that represents the Program Name.
- ProgramName: Identifies the name of the program.

## COURSE_CATALOG
- CourseID: Primary Key for the COURSE_CATALOG table being used as a Foreign Key in the COURSE_OFFERINGS table.
- CatalogYear: Identifies the school year for which the course is taking place.
- CatalogID: ID that represents and identifies a specific course. This is not a unique ID in most cases due to the common practice of having multiple sections of the same course being offered within the same term.
- ProgramID: Primary Key for the PROGRAMS table being used as a Foreign Key within the COURSE_CATALOG table.
- CourseTitle: Identifies the name of the course.
- Credits: Identifies the number of credit hours a student receives upon completion of the course.
- Prereqs: Identifies any prerequisites needed in order to enroll in a given course.
- Coreqs: Identifies any corequisites needed in order to enroll in a given course.
- Fees: Identifies any monetary fees that a student owes upon enrollment in a given course.
- Attributes:
- Description:


## TERM_TO_CATALOG_YEAR
- Term:
- CatalogYear:


## COURSE_OFFERINGS
- CourseOfferingID: Surrogate Key serving as Primary Key for the COURSE_OFFERINGS table. Also found as a Foreign Key within the COURSE_MEETINGS table.
- CourseID: Primary Key for the CATALOG_COURSES table being used as a Foreign Key within the COURSE_OFFERINGS table.
- CatalogID: ID that represents a identifies a specific course. This is not a unique ID in most cases due to the common practice of having multiple sections of the same course being offered within the same term.
- Term: Identifies the time frame (in seasonal form) for which the data is taking place within. format = {season}{year} 
- CRN: 
- Section:
- Credits:
- Title:
- Timecodes:
- PrimaryInstructorID:
- Capacity:
- Actual:
- Remaining:

## COURSE_INSTRUCTORS
- InstructorID:
- Name:

## COURSE_MEETINGS
- CourseMeetingID:
- CourseOfferingID:
- LocationID:
- StartDateTime:
- EndDateTime:

## COURSE_LOCATIONS
- LocationID:
- LocationCode:
