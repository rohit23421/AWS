## EC2 in action: Creating an EC2 instance with and without bootstrapping and attaching ENI's and playing with hibernate

What is AWS EC2?
AWS EC2 (Elastic Cloud Compute) is a web service offered by Amazon that provides resizable compute capacity in the AWS cloud. It offers Infrastructure as a service (IaaS). It provides complete control of computing resources, which one can scale as per the requirement.EC2 reduces the time required to boot and obtain new server instances i.e. Amazon EC2 instances. It allows scaling capacity as per the computing requirements. Amazon EC2 provides system administrators and developers, isolation from failure scenarios by providing them tools to build failure resilient applications.
Lets launch an EC2 instance first without bootstrapping and then with bootstrap also we will configure 2 ENI's on the instances and check its state and at last we will be playing with hibernate feature of EC2

First we launch an EC2 instance following the procedure as shown below:

First go to the EC2 section
## Step:1
To create a new Instance Click on Launch Instance
## Step:2
Select the AMI(Amazon Machine Image) that you want
## Step:3
Select the Instance type or the machine that you want
## Step:4
Then configure the instance details 
## Step:5
Select the storage details
## Step:5
Add a tag to the EC2 machine but it is optional
## Step:6
Now the most important part Is to configure the security groups,here we are setting an SSH from our own IP and HTTP from everywhere so everyone can access the machine through the IP but only we can SSH
## Step:7
Now we set a key pair and download it for ssh into our instance from our terminal
## Step:8
We can see the listed instance that we just created
## Step:9
Now to ssh from our local machine to the EC2 instance we got the terminal and enter the command as shown below with the user as ec2@user and at the public IP of the instance
## Step:10
Now we will launch a web server from our instance so first we install all the dependencies
## Step:11
Now as we have installed and configured our web server we can view it on the HTTP rule from the browser

Now accessing the same site using bootstrapping
Following the same steps from the previous topic upto the instance type
## Step:12
Now the main part where we are using the bootstrapping method or the user-data part here we will add all the commands that are to be executed when the machine boots p will all the commands in a new line
## Step:13
Using the same security group details as before
## Step:14
We can verify these when we ssh into our instance and hit httpd -v we can see that all our services have been installed already that was because of the bootstrapping that we used while launching the instance
## Step:15
Now we will be playing with the ENI and we will be creating a new ENI and will be attaching it to our instance and verify it
## Step:16
Now when we check the ENI attached to instance before we only see one ENI that is 172.31.46.242
## Step:17
Now to create an ENI we migrate into the ENI section from the EC2 dashboard and fill the details a our requirement
## Step:18
After we hit create Network interface We can see that we have successfully created an ENI
## Step:19
Now to attach the ENI to the instance click the attach option and select the instance that we want to attach with
## Step:20
We can view the instance details and see the ENI that are attached to it
## Step:21
Now to verify it we can also see the ENI that we have attached to instance by ssh and hitting the command ifconfig to see the ENIs and we can see that there is a new ENI with IP 172.31.35.222
## Step:22
To detach the NEI we can hit the Detach option
## Step:23
And confirm the detachment for the ENI
## Step:24
To verify it we can again check it through the command line

Now we will be playing with the hibernate feature of the EC2 instance
## Step:25
keep all the setting same but in the instance details part we will hit/check the checkbox of Stop-hibernate behaviour for hibernate to work
## Step:26
We set up the storage details as hibernate uses encrypted EBS volumes so we have to encrypt the volume that we are creating
## Step:27
Using the same security group
## Step:28
Now we hit some commands to acquire some data so that we can see that when we use hibernate e we can again regain the data of the instance
## Step:29
Now we hit the hibernate option to hibernate the instance 
## Step:30
Now again when we again start the instance and SSH into the instance and check the uptime and we can get our data back or we can say that the RAM is regained

So that's how we create an instance and use bootstrapping and also use ENI's and hibernate features in EC2

### Benefits of using IAM in AWS:
1. Reliability
2. Security
3. Flexibility
4. Cost Saving
5. Elastic Web-Scale Computing
