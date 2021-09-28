# Take Home assignment

### Problem Statement -
In the script.py file, create a function transform() that
1. opens local files from the input/ folder
2. reads the JSON content of the files
3. applies suggested transformation to the data
4. loads data into output CSV file based on suggested attribute and save it in the output/ folder

The function should be able to parallely perform the above operations based on the number of cores present on the device.

### Transformations to be applied -

1. Convert attribute "ts" to "%Y-%m-%d HH:MM:SS UTC" format and store as column "eventTime"
2. Extract "profile.identity" and create column "identity"
3. Extract "profile.platform" and create column "platform"
4. Extract "deviceInfo.model" and create column "model"
5. Calculate device surface area using "deviceInfo.dimensions" and create column "sArea"
6. Extract "eventProps.templateName" and create column "template"
7. Store attributes "profile", "deviceInfo", "eventProps" as flattedned strings in columns of their original name

### Expected output schema -

| Columns | Data type |
| -- | -- |
| eventTime | TIMESTAMP |
| eventName | STRING |
| identity | STRING |
| platform | STRING |
| model | STRING |
| sArea | FLOAT64 |
| template | STRING |
| profile | STRING |
| deviceInfo | STRING |
| eventProps | STRING |

The output file name for each record should be derived from the "deviceInfo.make" attribute, and each unique value should have a separate CSV file. Remove all spaces and special characters and convert to lower case while renaming the file.
