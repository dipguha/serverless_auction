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
1. New end point so adding in serverless file
2. PATCH - not creating a new record/resource, it updates the bid of an auction
3. Create a new Auction - highest bid is zero
4. Update bid end point with PATCH

# Lecture 35: Validation placing a bid
1. Calling function getAuctionByID from another JS file. Is this the right approach?

# Lecture 36: Using scheduled events to process our auctions - Part 3
1. Schedule using AWS EventBridge
2. Create a new lambda in serverless file
3. New Rule in EventBridge with target of Lambda function with event schedule as rate
```
sls logs -f processAuctions -t/ --startTime 1m
sls invoke -f processAuctions -l
```
# Lecture 37: Creating Global secondary index
1. Identify all auctions with status OPEN and end date in the past. Partion key of status and sort key of end date
2. Change AuctionsTable.yml file

# Lecture 38: Identifying ending auctions
1. Create getEndedAuctions in lib folder
2. Import the function in
3. Change AuctionsTable.yml file

# Lecture 39: Closing Auctions
1. lib/closeAuction.js
2. export function closeAuction
3. Call from processAuctions.js

# Lecture 40: Validation: Bidding on closed auctions
1. Add validation

# Lecture 41: Getting auctions filter by status
1. Change to DDB query and change code to accept status as query parameter.
2. The status needs validation, no status or wrong status name

# Lecture 43: JSON schema validation
1. Create getAuctionSchema.js
2. const schema = {}. export default schema
3. Define status can accept defined values and assign default value
```
npm install @middy/validator
```
4. Add extra validator on top of common validators


# Lecture 47: Auth0 flow
1. User authenticates with Auth0
2. Auth0 sends back JWT
3. createAuction handler serverless authorizer: auth
4. Any further request would include Authorization header
5. authorizer would verify it first
6. Send information in claims

# Lecture 49: Creating an Auth0 app
1. Sign up to Auth0 with email and password
2. Create a SPA apps
3. Settings - allowed callback url
4. Advanced settings - Grant types - password

# Lecture 50: Getting test token
1. Create a test user on Auth0
2. curl auth0 to get auth JWT
```
curl --location --request POST "https://auth_domain/oauth/token" \
--header 'Content-Type: application/x-www-form-urlencoded" \
--data-urlencode 'client_id=' \
--data-urlencode 'username=' \
--data-urlencode 'password=' \
--data-urlencode 'grant_type=password' \
--data-urlencode 'scope=openid'
```
5. { access_token, id_token, scope, expires_in, token_type
6. Portman AUTH_TOKEN = id_token

# Lecture 51: Deploying Auth service


# Lecture :


# Lecture :

# Lecture :


# Lecture :


# Lecture :


# Lecture :

# Lecture : 
