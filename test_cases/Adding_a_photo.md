# Test Cases Samples #


These test cases can be applied to any website or application where you can add photos.

| No. |	Test Case |	Expected Result |
|----|---------|-----------------|
|1 |Adding a file in the correct format.|Added correctly.|
|2 |Delete added file. |Deleted correctly. Good practice: Validation message such as "Are you sure you want to delete the object?"||
|3 |Adding more than 1 file at a time in the correct format. |Added correctly.|
|4 |Adding file one by one. (Within the quantity limit)	|Added correctly.|
|5 |Adding more files than allowed.|Files over the limit are not added. The user should see a validation message e.g. "Limit exceeded. The maximum quantity is...”. |
|6 |Delete more than 1 file at a time.	|Deleted correctly. |
|7 |Sending a blank form. |Information about the required value should be displayed or The button should be disabled as long as the fields are empty.|
|8 |Entering any string of characters instead of adding a file. |Unable to approve. The user should see a validation message about the file requirements.|
|9 |Adding a file with an unsupported format.|Unable to approve. The user should see a validation message which files are allowed. |
|10 |Adding a damaged file.|Unable to approve / validation message appears.|
|11 |Internet connection disconnected while adding a file. |The file is not added. The user should see a validation message e.g. "Disconnected”. |
|12 |Adding a one large file exceeding the specified limit.	|The file is not added. The user should see a validation message e.g. "File size too large. The maximum size is...MB”.
|13 |Adding a panorama composed of multiple photos or a 360-degree photo.	|Unable to approve / validation message appears. |

## Test raport based on above test cases: ##
1. [Example]()
