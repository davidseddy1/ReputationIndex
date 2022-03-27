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
clone repository
```
git clone https://github.com/davidseddy1/PrivateBlockchain.git
cd BlockChainCode
```

After cloning the repository build
```
docker build -t imagename
```

Before logging into ecr, ensure that proper credentials are set up, the easiest policy to put in 
place is to give your self administrationaccess. After ensuring this please login to ecr. 

```
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin ACCOUNTIDHERE!!!!.dkr.ecr.us-east-1.amazonaws.com
```

Go into AWS ECR console and select create new repository option
Ensure that Private repository option is picked and add the name of the repository to the end of the path. 

After this go back to the terminal to tag and push your image: 

```
docker tag imagename:latest YOURACCOUNT.dkr.ecr.us-east-1.amazonaws.com/AWSYOURREPO:YOURTAG
docker push YOURACCOUNT.dkr.ecr.us-east-1.amazonaws.com/YOURREPO:YOURTAG
```
Go into your repository, you should see the image, from there copy the image URI, this is needed for later. 


After this the terminal is no longer used. 
Go to ECS and select the cluster tab on the left hand side. 
**Create a new cluster**
- Choose EC2 Linux and Networking, select Next on the bottom
  - Pick a create a name for the cluster
  - Pick On Demand for Provisioning Model
  - EC2 Instance type choose the free tier option of t2.micro
  - AMI option choose the first option Amazon Linux 2
  - Leave the key-pair as none
  - VPC options choose default
  - Choose one of the subnets available 
  - Ensure that Auto-Assign IP address is enabled
  - Choose the default security groups
  - For container Instance IAM Role choose ecsinstancerole or if that is not available choose the create a new one
  - select create cluster, this will take a few minutes. 

**Create a Task Definition**
- On the left hand side choose Task Definition. 
- Select Create new TaskDefinition
  - Select EC2 tile on the bottom
  - Name your task definition
  - Select none for task role
  - leave network mode as default
  - Leave task memory and task cpu along
  - Choose add container under Container Definition
    -Type your container name
    -Paste the image URI which you saved earlier
    -Leave Private Repository authentication alone
    -Do your port mapping, in this case it will DesiredPort:8000, since 8000 is the container port
    -Choose Hard Limit 128 for Memory Limit
    -Select create task, don't bother with the advanced settings
    
**Add TaskDefinition to cluster**
-Go to your cluster, and choose the task tab
-Choose Run new Task
  - Choose EC2 as launch type
  - Select the task you just created for task name
  - choose your cluster
  - leave task number as 1
  - Leave task role as empty
  - Leave everything else as default, and run your task

**Go to your EC2 Instance**
-Go to security Group in the left hand side toward the bottom
-double click on the security group
- Select edit inbound group
  - Add a rule for custom TCP, Anwhere IPv4, for Port 8000
  - Add another rule which is also Custom TCP, Anywhere IPv6, for port 8000
- Now exit and Select Edit Outbound group
  - Add the same rules that are for inbound rules

Go back to the EC2 instance and go to overview detail
- There you should see on the right public IPv4 DNS
- Copy this address, and go to your web browser
- Paste the public IPv4 DNS address and at the end add :8000
- You should see a Get/ Request could not be found
  - This means that everything has been set up correctly.

For a visual Demonstration on how to set up blockchain on AWS, please refer to:
- [AWS setup](https://www.youtube.com/watch?v=zs3tyVgiBQQ)

## Step 5: Running it Locally

In your terminal run the following code: 

```
npm run dev
```
In your browser type the URL: http://localhost:30000 to run the application.

## Additional Information

#### Check that it added to the block chain:
