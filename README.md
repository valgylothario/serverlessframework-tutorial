# serverlessframework-tutorial

Carefull when use aws cloud service , see the account type if is free or not and how much resource are using ,otherwise can cost money if goes to the limit in case of free account.
Evreyone should be responsible for the their own actions.

1- access aws console with your login account

2- create user in aws IAM with programatic access and AdministratorAccess (save the key and secret generated for this user).

3- install serverless framework in your machine globaly

	npm install -g serverless (run this comand in console)

4- configure serverless with provider aws ,add key and secret aswell as profile (run in console)

	serverless config credentials --provider aws --key {key code} --secret {secrect code} --profile serverlessUser

5- create serverless template code with aws and node (aws-nodejs)

	serverless create --template aws-nodejs --path myServerlessProject

6- add profile to your serverless yamel (profile:  serverlessUser)

provider:
  name: aws
  runtime: nodejs12.x
  lambdaHashingVersion: 20201221
  profile:  serverlessUser

7- run a comand to deploy (sls -short end for serverless)

	sls deploy

output consola:

Serverless: Packaging service...
Serverless: Excluding development dependencies...
Serverless: Creating Stack...
Serverless: Checking Stack create progress...
........
Serverless: Stack create finished...
Serverless: Uploading CloudFormation file to S3...
Serverless: Uploading artifacts...
Serverless: Uploading service myserverlessproject.zip file to S3 (2.34 KB)...
Serverless: Validating template...
Serverless: Updating Stack...
Serverless: Checking Stack update progress...
...............
Serverless: Stack update finished...
Service Information
service: myserverlessproject
stage: dev
region: us-east-1
stack: myserverlessproject-dev
resources: 6
api keys:
  None
endpoints:
  None
functions:
  hello: myserverlessproject-dev-hello
layers:
  None

**************************************************************************************************************************************
Serverless: Announcing Metrics, CI/CD, Secrets and more built into Serverless Framework. Run "serverless login" to activate for free..
**************************************************************************************************************************************


