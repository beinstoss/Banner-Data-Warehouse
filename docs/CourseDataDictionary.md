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
- Attributes: Provides a high-level description of a specific course.
- Description: Provides a short overview of a specific course.


## TERM_TO_CATALOG_YEAR
- Term: Identifies the semester and year of a given course.
- CatalogYear: Identifies the school year a given course is offered.


## COURSE_OFFERINGS
- CourseOfferingID: Surrogate Key serving as Primary Key for the COURSE_OFFERINGS table. Also found as a Foreign Key within the COURSE_MEETINGS table.
- CourseID: Primary Key for the CATALOG_COURSES table being used as a Foreign Key within the COURSE_OFFERINGS table.
- CatalogID: ID that represents a identifies a specific course. This is not a unique ID in most cases due to the common practice of having multiple sections of the same course being offered within the same term.
- Term: Identifies the time frame (in seasonal form) for which the data is taking place within. format = {season}{year}
- CRN: Stands for Course Registration Number and is a unique ID associated with a given section of a course that's used when registering for classes.
- Section: Identifies unique offerings of the same course that's being offered in the same semester.
- Credits: Identifies the number of credit hours a student receives upon completion of the course.
- Title: Identifies the name of the course.
- Timecodes: Identifies the meeting days, times, dates, and locations of each course section. format = {'days', 'times', 'dates', 'location'}
- PrimaryInstructorID: Surrogate Key serving as the Primary Key for the COURSE_INSTRUCTORS table.
- Capacity: Identifies the total amount of seats in a course section.
- Actual: Identifies the number of students registered for a course section.
- Remaining: Identifies the number of available seats in a course section.

## COURSE_INSTRUCTORS
- InstructorID: Primary Key for the COURSE_INSTRUCTORS table being used as a Foreign Key within the COURSE_OFFERINGS table.
- Name: Identifies the name of the instructor teaching a given course section.

## COURSE_MEETINGS
- CourseMeetingID: Primary Key for the COURSE_MEETINGS table.
- CourseOfferingID: Surrogate Key serving as Primary Key for the COURSE_OFFERINGS table. Also found as a Foreign Key within the COURSE_MEETINGS table.
- LocationID: Surrogate Key serving as the Primary Key for the COURSE_LOCATIONS table.
- StartDateTime: Identifies the start date and start time of a course section.
- EndDateTime: Identifies the end date and end time of a course section.

## COURSE_LOCATIONS
- LocationID: Primary Key serving as a Foreign Key in the COURSE_MEETINGS table.
- LocationCode: Identifies the building and room number of where a course section is being held.