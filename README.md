# serverless_auction
Serverless framework, serverless services on AWS using Lambda, DynamoDB

# Lecture : 
1. Action service: https://github.com/arielweinberger/course-auction-service
2. Branches provide source code

# Lecture 26: Defining IAM role statements
1. By default, lambda can only write to CloudWatch logs
2. serverless-pseudo-parameters plugins provide mechanism to store parameters

# Lecture 27: Optimizing serverless.yml
1. Move resources and IAM in separate folders and files and refer them back in serverless.yaml file 

# Lecture 28: Optimizing serverless.yml part 2
1. Table names could be different in different environments
2. When a DynamoDB table is created, this can be returned using ref
3. Javascript file refer as process.env.environment variable

# Lecture 29: Serverless Offline
1. It is not worth

# Lecture 30: Introduction to Middly and Middlewares (Part 2)
1. Used before handlers
```
npm install @middy/core @middy/http-event-normalizer @middy/http-error-handler @middy/http-json-body-parser
npm install http-errors
```
2. Import middy module from @middy/core package. Later we will put them as part of core middleware
3. Make changes to createAuction.js to include middy and error modules imported before
```
sls deploy -f createAuction -v
```

# Lecture 31: CRUD Operation, get auction
1. Define a new lambda function getAuctions in serverless.yaml
2. Create the handler file getAuctions.js
3. 

# Lecture 32: CUUD Operation, Get auction by id
1. Allow Query as part of permissions

# Lecture 33: Creating a common middleware
1. Create lib for helper libraries
2. Default export doesn't need curly braces
3. sls deploy -v - serverless deploys only the changes

# Lecture 34: Placing a bid
1. 

# Lecture : 


# Lecture : 

# Lecture : 


# Lecture : 

# Lecture : 


# Lecture : 
