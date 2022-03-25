# Setting Up the Application

## Step 1: Set up AWS Account

#### Step 1.1: Go to AWS Free Tier and create an account you do not posses one already [https://aws.amazon.com/free](https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc&awsf.Free%20Tier%20Types=*all&awsf.Free%20Tier%20Categories=*all). 
Click on the orange "Create an AWS Account" Button at the top right of the screen. Complete the steps prompted on the screen. Be aware that payment information will be asked for and have to be provided in order to use any of the services.<br>

#### Step 1.2: Set up an IAM User 
  To be able to run the application fully an IAM User will need to be created. <br>
  In the search bar look IAM. The following article will explain how to set up one up:[ https://docs.aws.amazon.com/IAM/latest/UserGuide](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html)


Make sure to select FullAccess policies for DynamoDB, Amplify, ECS, EC2, ECR, and Lambda.


## Step 2: Clone Repository and Set Up Environment Variable


#### Step 2.1: Clone Repository
```
git clone https://github.com/OtRL-Reputation-Index/otrl-referral.git
cd otrl-referral
npm install
```
#### Step 2.2: Set Up Environment Variable

rename .env.template to .env.local. Then in .env.local set the aws credientials to the IAM credientals from AWS.
```
# AWS Authentication Credentials
DEV_DB_AWS_ACCESS_KEY=
DEV_DB_AUTH_AWS_SECRET_KEY=
DEV_DB_AUTH_AWS_REGION=
``` 

## Step 3: Creating The Database with DynamoDB

## Step 4: Setting up BlockChain

## Step 5: Running it Locally

In your terminal run the following code: 

```
npm run dev
```
In your browser type the URL: http://localhost:30000 to run the application.

## Additional Information

#### Check that it added to the block chain:
