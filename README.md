
# AWS Lambda Function to Start CloudTrail Logging if Stopped

### This Lambda function Start Logging Cloud Trail if it Stopped Logging and sends logs to CloudWatch Log group.

![](https://github.com/SofiaNeogalaxy/lambda-cloudtrail-restartlogging/blob/4702929be4b6c65bffd964e84416f1ca4cc3a966/awslambdatrailpic.png)

## Usage

1. #### Create a new lambda function:
- Runtime: Python 3.7
- Architecture: x86_64
- Permissions:Create new role and attach this policy  [lambda-policy.json](https://github.com/SofiaNeogalaxy/lambda-cloudtrail-restartlogging/blob/f7f136ef842800909e8078672901cf91617ff312/lambda-policy.json)

2. #### Create Amazon EventBridge Rule with an event pattern

Event pattern -> AWS services -> CloudTrail -> AWS API Call via CloudTrail -> Specific operation(s) -> StopLogging ->Target types -> AWS service -> Lambda function

3. #### In Lambda console add lambda functione code [lambda-trail-logs.py](https://github.com/SofiaNeogalaxy/lambda-cloudtrail-restartlogging/blob/f7f136ef842800909e8078672901cf91617ff312/lambda-trail-logs.py) to Code editor. 
4. #### Test and Deploy.

### Note

This Lambda function Start Logging any existing CloudTrail which stopped logging, if you want to specify trail add 

```python
def lambda_handler(event, context):
    name = 'TRAIL_ARN'
```
and than in Lambda console add in Configuration -> Enviroment variables -> Key:TRAIL_ARN ->Value: arn of your trail
Also you can specify trail in your Lambda role policy Resource.
