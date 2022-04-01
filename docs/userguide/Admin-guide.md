# Admin Guide

## Confirm DynamoDB Update
1. Open AWS and search for DynamoDB, select the first option

![Search for DynamoDB](./img/aws_search.jpg)


2. Select the "Tables" button in the leftmost navigation panel

![Select Table Option](./img/aws_select_tables.jpg)

3. Select the "referral" table from the existing tables

![Select referral table](./img/aws_select_referral.jpg)

4. Select the "Explore More Items" button in the top right of the window

![Explore Table](./img/aws_explore_tables.jpg)

5. You can now see the updated referral items in the window.

![Referral Table](./img/aws_referral_table.jpg)

## Confirm Blockchain Update
1. Go to the AWS Dashboard and search cloudwatch
![Search CloudWatch](./img/Cloudwatchdirection.png)

2. Click on Log Groups on the CloudWatch Dashboard
![Click on LogGroups](./img/cloudwatchview.png)

3. Select the Desired Log Group
![Click on Log group](./img/PreLogview.png)

4. View the Logs for Blockchain
![View Logs](./img/Logs.png)
    - error code Post /requestValidation 200 -> Success
    - error code Post /requestValidation 404 -> Failure
    - error code Post /submt 200             -> Success
    - error code Post /submit 404            -> Failure
