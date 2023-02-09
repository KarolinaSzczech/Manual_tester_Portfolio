## Test report of adding photos in the advertisement on the https://olx.pl website ##

**Testing time:**

 - Adding photo testing - 2h
 - Preparing a report - 3h

### Used for testing: ###

**Desktop:**

OS: Windows 10 PRO

 - Browser: Chrome Version 107.0.5304.108)
 - Browser: Firefox Version 109.0
 - Browser: Firefox Developer Edition Version 108.0b6
 - Browser: Microsoft Edge Version 107.0.1418.56
 - Browser: Opera Version 94.0.4606.37

| No. |	Test Case | Expected Result | Actual Result |
|----|----|----|----|
|1 |Adding a file in the correct format.|Added correctly.|Correct result. |
|2 |Delete added file. |Deleted correctly. Good practice: Validation message such as "Are you sure you want to delete the object?"|Correct result. No validation message.|
|3 |Adding more than 1 file at a time in the correct format. |Added correctly.|Correct result. |
|4 |Adding files one by one. (Within the quantity limit)	|Added correctly.|Correct result. |
|5 |Adding more files than allowed.|Files over the limit are not added. The user should see a validation message e.g. "Limit exceeded. The maximum quantity is...”. |Correct result. The user see a validation message. |
|6 |Delete more than 1 file.	|Deleted correctly. |Correct result. |
|7 |Sending a blank form. |Information about the required value should be displayed or The button should be disabled as long as the fields are empty.|The confirm button is inactive as long as the field is empty. |
|8 |Entering any string of characters instead of adding a file. |Unable to approve. The user should see a validation message about the file requirements.|Correct result. The user sees a validation message. |
|9 |Adding a file on with an unsupported format.|Unable to approve. The user should see a validation message which files are allowed. |Other expected behavior. No validation message. The accepted photo format is set by default in the file selection window.  If we change to "All Files" and upload a file in a different format, it will not be possible to save the ad.|   
|10 |Adding a damaged file.|Unable to approve / validation message appears.|Incorrect result. **Bug ID-001**  |
|11 |Internet connection disconnected while adding a file. |The file is not added. The user should see a validation message e.g. "Disconnected”. |Incorrect result. **Bug ID-002**  |
|12 |Adding one large file exceeding the specified limit.	|The file is not added. The user should see a validation message e.g. "File size too large. The maximum size is...MB”. |Correct result. |
|13 |Adding a panorama composed of multiple photos or a 360-degree photo.	|Added correctly. _(Only if it is intended.)_  |Correct result. | 


## Detected Bugs ##

### ID-001 No validation message when adding a damaged photo ###

**Priority:** Medium

**_Precondition: Logged user_**

**Steps to reproduce the behavior:**

1. Go to page https://olx.pl
2. Sign in
3. Click on the "DODAJ OGŁOSZENIE" button in the upper right corner
4. Scroll down to where you add photos
5. Add damaged photo.

**Expected Result:** Unable to add damaged photo. The user should see a validation message.

**Actual Result:** The user not see a validation message. The damaged photo keeps loading. It doesn't stop loading even after a few minutes.

![olx - uszkodzony plik](https://user-images.githubusercontent.com/118970045/216030907-74da2ad7-8d90-415a-be9e-ed3ccda92bd4.png)
![Ładowanie się](https://user-images.githubusercontent.com/118970045/216031915-c8d79aa6-3e49-4fca-8f0d-afd37188acc2.gif)



### ID-002 No validation message after disconnecting the Internet ###

**Priority:** Medium

**_Precondition: Logged user_**

**Steps to reproduce the behavior:**

1. Go to page https://olx.pl
2. Sign in
3. Click on the "DODAJ OGŁOSZENIE" button in the upper right corner
4. Scroll down to where you add photos
5. Disconnect the internet while uploading the photo

**Expected Result:** Unable to add photo. The user should see a validation message.

**Actual Result:** The user not see a validation message. The damaged photo hangs while loading. It is the same situation as bug ID-001.


