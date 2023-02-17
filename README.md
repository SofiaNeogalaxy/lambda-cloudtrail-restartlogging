
# AWS Lambda Function to Start CloudTrail Logging if Stopped

![awslambdatrail.png](https://github.com/SofiaNeogalaxy/lambda-cloudtrail-restartlogging/blob/d114ccc5d2a6d15b35b28b780230e4666a26347f/1ad7b0e483cbf309a3414e9fadf034f6.jpg](https://github.com/SofiaNeogalaxy/lambda-cloudtrail-restartlogging/blob/adbd155ec09c9be97d9f7c76468777d954e60ee2/awslambdatrail.png)

## Usage

1. #### Create a new lambda function:
- Runtime: Python 3.7
- Architecture: x86_64
- Permissions:Create new role and attach this policy  [lambda-policy.json](https://github.com/SofiaNeogalaxy/lambda-cloudtrail-restartlogging/blob/f7f136ef842800909e8078672901cf91617ff312/lambda-policy.json)

2. #### Create Amazon EventBridge Rule with an event pattern

Event pattern -> AWS services -> CloudTrail -> AWS API Call via CloudTrail -> Specific operation(s) -> StopLogging ->Target types -> AWS service -> Lambda function

3. #### In Lambda console add lambda functione code [lambda-trail-logs.py](https://github.com/SofiaNeogalaxy/lambda-cloudtrail-restartlogging/blob/f7f136ef842800909e8078672901cf91617ff312/lambda-trail-logs.py) to Code editor. 
4. #### Test and Deploy.
