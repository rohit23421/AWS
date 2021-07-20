## Creating user and assigning them to groups through AWS CLI

AWS CLI  is a great alternative of using AWS management console, where we can work on AWS services from the command line itself and another such way is to create users and groups through IAM in AWS CLI
So first it starts with creating an User in AWS through IAM, lets see how to accomplish the task-

## Step:1
To install AWS CLI on your local machine(Windows), first go to https://docs.aws.amazon.com/cli/latest/userguide/install-windows.html and then navigate to windows section and select the installer that you want
Here we have downloaded the AWS CLI MSI installer for windows(64-bit) and then successfully installed it on our machine and then run 
### aws --version 
on your command prompt fo confirmation of the installation
## Step:2
Now to create an IAM group and add a new IAM user to it
### aws iam create-group --group-name "yourIamGoupName"
## Step:3
Now to create a new user
### aws iam create-user --user-name "yourIamUser"
## Step:4
Now to add the created user "yourIamUser" to the group "yourIamGoupName"
### aws iam add-user-to-group --user-name "yourIamUser" --group-name "yourIamGoupName"
## Step:5
To check about the created user and group
### aws iam get-group --group-name "yourIamGoupName"

We can also verify it in the AWS console by navigating into the IAM console and under the Users section
Also we can list the group that we created by navigating to the groups section

### Benefits of using IAM in AWS:
*   Improved security

*   Information sharing

*   Ease of use

*   Productivity gains

### Conclusion: 
IAM is the best way of managing people who are working for your company, as they can be continuously monitored and can work by there own assigned capability.
