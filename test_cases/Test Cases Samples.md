# Test Cases Samples #

## Default login test cases (high-level test cases) ##
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
|8 |	Enter login page and type password |	Password should be masked *** |
|9 |	Use Tab key to navigate throw login form |	User is able to use only keyboard to login to application |
|10 |	Use Enter key to confirm login form |	The user is logged into the application |
|11	| Mark Remember password checkbox and log in with correct credentials |	The user should be logged in after re-entering the site, after restarting the browser |
|12	| Attempt to log in as an existing user with an invalid password 3 or more times	| Login lockout for several minutes and/or email to user about suspicious login attempt. |
 

## Default login test cases (low-level test cases) ##

### Use Facebook authentication to log in and create an account ###

**Precondition:** The user has account in the Facebook application that are not synchronized with the website.

| No. |	Test Case |	Expected Result |
|----|---------|--------|
|1 |Press the Login with Facebook button  |	The user has been transferred to the simplified registration screen |
|2 |Tick the required consent and then press the Register button | The checkbox with consent to the terms of the regulations has been marked. The user has been registered and transferred to the application |
|3 |Log out of the application	 | The user has been logged out |
|4 |Press the "Login" button	 | The user has been taken to the login screen |
|5 |Press the Login with Facebook button |The user has logged into the application |


## My test case examples: ##
1. [Ceneo.pl](https://github.com/KarolinaSzczech/Manual_tester_Portfolio/blob/nowy_raport/test_raport/Ceneopl_raport.md)
    
