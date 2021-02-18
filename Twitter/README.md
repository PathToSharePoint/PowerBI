# Twitter Power BI Report

## About this solution

This Power BI report allows you to track recent Twitter conversations related to Microsoft 365. 

For a demo, open the report for the [week of February 13, 2021](https://app.powerbi.com/view?r=eyJrIjoiZmIyMDViOGEtMzZmMS00ZTIwLTllOGMtNjE2YmQ3ZmNiN2QxIiwidCI6ImFkNWMwYjhiLWUyYWQtNGU0Yy04MGRmLTFmYjNlMzU0NTc2ZiIsImMiOjZ9)

## Prerequisite

The report relies on the Twitter API v2 to pull tweets and user data. v2 is still in "early access" mode as of February 2021.
Twitter requires you to open a developer account. Access is free for occasional use, for more intensive usage you'll probably need a paid subscription. Follow the instructions to get started:
https://developer.twitter.com/en/apply-for-access

## Initialization

After downloading the pbit template, double click to open it. Provide the parameters:

- Endpoint: the report was built to work with the Twitter recent search API v2, which can be called at
https://api.twitter.com/2/tweets/search/recent
- NumberOfHours: tells the query how far back to go. For example, enter 48 to get the past two days (= 2 x 24 hours).  Keep NumberOfHours below 168 for the Twitter recent search API, as it allows you to look up as far as one week back. I recommend that you set the number to a low value while tweaking the report, or else you'll quickly reach your quota of queries for the month.
- NoiseLevel: tweets with too many hashtags will be discarded, as they are often used by spammers. Having up to 5-6 hashtags in a regular tweet is not uncommon, so it is suggested to set NoiseLevel to a number between 8 and 12.
- BearerToken: used to authenticate you to the Twitter service, this is the token Twitter will provide when you register for a developer account. It is of the form "Bearer xxxxxxxxxxxxxxxxxxxxxxx".

## Hashtags table

The template comes with more than 20 common hashtags related to Microsoft 365. You can customize the table for your own needs, the hashtags don't even have to be related to Microsoft 365.

To update the hashtags table:

- open the report
- click on Transform Data to open the Power Query Editor
- select the hashtags table on the left hand side
- click on the gear in the right hand actions list to edit the table
- modify the table as needed
- save the table
- close the Power Query Editor

![Edit Power Query Table](https://github.com/PathToSharePoint/PowerBI/blob/main/Twitter/Edit%20Power%20Query%20Table.png)
