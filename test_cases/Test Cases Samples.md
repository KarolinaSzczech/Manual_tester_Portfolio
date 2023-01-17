# Test Cases Samples #

## Default login test cases (high level test cases) ##
These test cases can be applied to any system that has login functionality. Since these are high-level cases, they do not have specific test data in the input.

| No. |	Test Case |	Expected Result |
|----|---------|-----------------|
|1 | Log in as an existing user with correct credentials	|The user is logged into the application|
|2 | Attempt to log in as an existing user with an invalid password|	The user should see a message e.g. "Invalid credentials"|
|3 |	Attempt to log in with a random login and password (not existing in the application)|	The user should see message e.g.: "Invalid credentials" |
|4 |	Attempt to log in with leaving the login credentials blank |	Information about the required value should be displayed or The button should be disabled as long as the fields are empty|
|5 |	Validate login field: use uppercase for login and valid password	| The user is logged into the application Note: Only if that's how it's supposed to work |
|6 |	Validate login field: for email use only @domain.com and valid password |	Information "invalid value" should be displayed Note: If the system uses email as login, it would be good to display login@domain.com along with the message "Invalid value"|
|7 |	As a logged-in user, enter the login url	| The user is redirected to the home page |
|8 |	Enter login page and type password |	Password should be masked ****|

|9 |	Use Tab key to navigate throw login form |	User is able to use only keyboard to login to application |
|10 |	Use Enter key to confirm login form |	The user is logged into the application |
|11	| Mark Remember password checkbox and log in with correct credentials |	The user should be logged in after re-entering the site, after restarting the browser |
|12	| Attempt to log in as an existing user with an invalid password 3 or more times	| Login lockout for several minutes and/or email to user about suspicious login attempt. |


 # Test cases for XYZ #
 
Low-level test cases, they do require specific test data in the input.

link
    
