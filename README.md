# DataHandler

Servlet WEB API that allows to query/filter information from text file over web.

API reads text file from file system and applies filtering/querying logic to produce response.

1. API response content type is JSON
2. Query params:
- limit: integer which represents max number of chars in text that API returns. If parameter is blank or missing returns max 10000 chars.
- q: string which represents text to search in file, i.e. if it q=java - API returns all strings which equals to ‘java’ or containing it. If q is blank or missing - API returns all text from file.
- length: integer which represents max string length. API returns string which doesn’t exceed that number or if there is no such strings empty response. 
- includeMetaData: boolean which if set to true will expose file metadata in API response alongside textual content. That metadata contains: fileName, fileSize (KB), fileCreationDate. 

Example of API call/response:
/result?q=Page&limit=500&length=10&includeMetaData=true

Such call returns all strings that contains "Page" with length <= 10 with total length <=
500. Additionally metadata will be included.

Tech Stack:
1. Servlet 3.1
2. Java 7
3. Tomcat 8
4. Json-simple-1.1.1
5. Gson-2.3.1
