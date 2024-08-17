# EC2-Start-and-Stop-Lambda-EVentbridge-IAM

Here is the detailed description: Scheduled EC2 Server Start and Stop Project. 2 Lambda functions were created to execute the start and stop job
2 IAM roles werected for each Lambda function to execute it's job.

Step 1: Create 2 IAM policies respectively
ec2:StartInstances
ec2:DescribeInstances

ec2:StopInstances
ec2:DescribeInstances

Create 2 IAM roles with permissions:
    -The above policy attached respectively
    -LambdaExecute
    -Ec2ReadOnlyAccess
    -CloudwatchEventInvocationAccess

Step 2: Launch an EC2 Instance

Step 3: Create Lambda Functions
Create Lambda function StartEC2Instance with:
Runtime: Python
Role: IAM role

Create Lambda function StopEC2Instance with:
Runtime: Python
Role: IAM role

Step 4: Create Amazon EventBridge Rules
Create Start and Stop rules respectively
Clink on create rule and select schedule as the target type and set desired frequency.
Add Lambda as target.
Select the lambda functions accordingly to to be triggered.

Test setup by verifying EC2 instances start and stop at scheduled times
