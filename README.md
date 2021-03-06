# AWS CloudWatch Subscription Filter Gateway to SNS
This Lambda function can be used as CloudWatch Subscription Filter to send log messages to a SNS topic.

## Installation
1. Create a role with a policy to allow _sns:publish_ to your SNS topic, for debug purpose add a policy to write to CloudWatch Logs as well (see [example_policy.json](example_policy.json)).
2. Create a Lambda function with the content of the index.js. Use Node 8.10 or higher. Choose the execution role you just created.
3. Add an environment variable called _sns_arn_ with the full arn of your destination SNS topic.
4. Setup the new Lambda function as Stream destination in your CloudWatch Log Groups. Choose the JSON Log format.
5. Done.

## Debug payload
If you want to see the payload from CloudWatch, add an environment variable called _debug_ and the value _1_. Be sure you have added a policy allowing the Lambda function to write to your CloudWatch Logs.