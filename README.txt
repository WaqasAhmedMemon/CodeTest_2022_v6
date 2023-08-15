- refactor/app/Http/Controllers/BookingController.php
I refactor the given code to improve its readability, maintainability, and adherence to coding standards. 
My Booking Controller code aims to improve readability by using clear variable names, simplifying conditionals, using the null coalescing operator, and removing unnecessary variables. It's important to note that the refactoring might need to be further tailored to fit the overall architecture and coding standards of your project.

- Repository/BookingRepository.php
getUsersJobs method:
Combined the if conditions related to user types to improve readability.
Moved the checks for $jobs existence and the subsequent processing inside the common if block to avoid code duplication.
Used !empty($jobs) instead of $jobs to check if jobs are available.
Improved indentation and formatting for better readability.
Replaced $usertype = ''; with $usertype = null; for better default value.

getUsersJobsHistory method:
Combined the conditional checks related to user types to enhance readability.
Used the default value in $request->get('page', 1) to set the default value for the page number.
Consolidated variable declarations at the start to make them easier to manage.
Removed unnecessary comments and unused variables.
Set $pagenum to $page regardless of the user type to avoid redundancy.

store function:
Created helper functions for input validation, due date calculation, job_for value mapping, and consumer type mapping to improve code readability and maintainability.
Utilized the helper functions to handle respective logic, making the main code more concise and focused on the higher-level flow.

jobToData method:
I've extracted the mapping of certified values into a separate helper function mapCertifiedValue, which returns an array of corresponding job_for values.
I've created a helper function prepareJobForData to handle the mapping of gender and certified values for the job_for array.
The main jobToData function now uses these helper functions to handle the mapping and preparation of job data in a more modular and readable way.

Refactored version of the jobEnd method:
I've separated the code into smaller functions for better readability and maintainability.
The calculateTimeDifference function calculates the time difference between two dates.
The updateJobAndSendEmails function handles updating the job details, sending emails, and firing events.
The sendEmail function sends the email using the provided mailer.
Usage of now() function instead of date('Y-m-d H:i:s') to get the current date and time.