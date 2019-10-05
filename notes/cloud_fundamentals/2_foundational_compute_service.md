# Introduction
The cloud is the perfect place to host your travel blogging website, mytrips.com. The first thing you'll need though is a server, a powerful computer that can serve up your website when a user requests it. Next, you'll want to use security mechanisms to protect your website and data. Lastly, you'll want to use cloud services to help you manage and maintain the life cycle of your website. 

# Why do we need servers in the cloud?
Days of maintaining internal data centers are gone. No longer you have to invest a lot of money and labor upfront to buy server hardware, to rack and stack servers, and to maintain data centers. The cloud provides a new opportunity for deploying your applications and making them accessible to the world. 

Cloud services, more specifically servers in the cloud, have revolutionized the IT industry, and the way we do business and allocate resources, allowing companies of all sizes and even individual developers to obtain new servers in minutes, allowing us to quickly scale capacity up and down based on the individual needs of our applications. 

Servers in the cloud allow you to build failure resilient applications that are isolate from common failure scenarios with capacity that can grow and shrink based on needs, and you only pay for what you use, and you aren't locked into long-term contracts. 

To recap servers in the cloud have revolutionized the IT industry:

- Scale capacity up and down based on demands.
- Storage, more memory, and computing power can be added as needed.
- Obtain servers in minutes.
- No need for onsite hardware or capital expenses.

# Elastic Cloud Compute (EC2)
Elastic Cloud Compute (EC2) is a foundational piece of AWS's cloud computing platform and **is service that provides servers for rent in the cloud**. Users are able to manage the servers and deploy applications to it. These servers are called **instances**. Instances are actual physical servers in an AZ or data center. So, EC2 is **not** considered _serverless_. 

A nice feature of EC2 is that it is elastic, like the name says, and can grow or shrink based on the needs or load on the application. Essentially, additional servers can be automatically provisioned or servers that aren't needed anymore can be removed. You have re-sizable compute capacity in the cloud, pretty amazing! You even have the ability to manage the servers and install applications on it. 

### Pricing Options
There are several pricing options for EC2.

- **On Demand** - Pay as you go, no contract.
- **Dedicated Hosts** - You have your own dedicated hardware and don't share it with others.
- **Spot** - You place a bid on an instance price. If there is extra capacity that falls below your bid, an EC2 instance is provisioned. If the price goes above your bid while the instance is running, the instance is terminated.
- **Reserved Instances** - You earn huge discounts if you pay up front and sign a 1-year or 3-year contract.

### Tips
- EC2 is found under the Compute section of the AWS Management Console.
- Spot instances can save you up to 90% off the on-demand pricing.
- There are several instance types that provide varying combinations of CPU, memory, storage, and networking capacity.

**Resources:** [Amazon Elastic Cloud Compute](https://www.amazonaws.cn/en/ec2/)

# Demo - EC2

See the video [here](https://youtu.be/MdoG9MuTib8).

# Elastic Block Store (EBS)
EBS is a storage solution for EC2 instances. It is a physical drive that is connected to the servers to increase storage. It has to be attached to your server and mounted before you can start storing data on it. Some instance types come with EBS volume already attached. 

There are **two types of memory** for an EC2 instance:

- in-memory (or instance store) 
- EBS

The **benefit of using EBS** over the instance store is that **you're able to presist data after the EC2 instance is terminated**. Any data stored on the volume are still accessible. A neat feature provided by AWS is that **each Amazon EBS volume is automatically replicated within its availability zone**. This protects you from component failure, offering high availability and durability. 

**Tips**

- EBS is found on the EC2 Dashboard.
- There are several EBS volume types that fall under the categories of Solid State Drives (SSD) and Hard Disk Drives (HDD).

**Resources**

[Amazon Elastic Block Store](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEBS.html)

# Demo - EBS

See the video [here](https://youtu.be/L2uyenlb_LA).

# Why do we need security in the cloud for our servers?
Security in the cloud allows you to have complete control over your virtual networking environment. Once you configured your virtual network with public or private facing subnets, you can then launch a place your servers in the selected network to secure access. 

Security in the cloud allows you to have complete control over your virtual networking environment.

- Configure your virtual network with public or private facing subnets.
- Launch your servers in the selected network to secure access.

# Virtual Private Cloud (VPC)
Let's see how AWS implements security for servers. Typically, when you create resources, they are on a _flat network_ that is shared among various AWS users, such as EC2 classic. A _flat network_ is a simple network design that reduces the cost and overall administration. All devices and workstations are connected to a single switch, meaning all devices are a part of the same broadcast network and communicate with each other. 

**Virtual Private Cloud (VPC)** allows you to create your own private space/network in the cloud. Then, you launch your servers like EC2 inside of that private network and EC2 inherits security. This is done as a security measure. We control the network configuration and security and expose what we do or do not want exposed to the internet using public or private subnets. VPC lives within a region and can span across multiple AZs. 

**Virtual Private Cloud (VPC)**

VPC allows you to control your virtual networking environment, which includes:

- IP address ranges
- subnets
- route tables
- network gateways

**Tips**

- VPC is found under Networking & Content Delivery section of the AWS Management Console.
- The default limit is 5 VPCs per Region. You can request an increase for these limits.
- Your AWS resources are automatically provisioned in a default VPC.
- There are no additional charges for creating and using the VPC.
- You can store data in Amazon S3 and restrict access so that it’s only accessible from instances in your VPC.

**Resources**

- [Virtual Private Cloud](https://en.wikipedia.org/wiki/Virtual_private_cloud)
- [Amazon Virtual Private Cloud](https://aws.amazon.com/vpc/)
- [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)

# Demo - VPC

See the video [here](https://youtu.be/md9n5hoxb-8).

# Lab - Launch an EC2 instance

## Virtual Servers in the Cloud
In this hands-on exercise, you will launch a virtual server in the cloud within a secure network. You will also manage additional storage options for your server.

**Prerequisites:**

- AWS Account

**Topics Covered:**
By the end of this lab, you will be able to:

- Launch a secure EC2 (Elastic Cloud Compute) instance within a VPC (Virtual Private Cloud)
- Manage an EBS volume

### Steps:
1. **Access VPC service from AWS Management Console**
- >On the AWS Management Console page, type `vpc` in the `Find Services` box and then select `VPC`.
- >Click the `Launch VPC Wizard` button and select `VPC with a Single Public Subnet`. _**Important:**_ In the `VPC Name` text box, enter a name for the VPC, and then select the first AZ from the `Availability Zone` dropdown. Leave everything else as the defaults.
- >Select `Create VPC` button.
- >You should see the `VPC Successfully Created` page, click the OK button in the far right. _**Important:**_ You should see a table that lists all of the VPCs, make a note of the one just created.
2. **Launch an EC2 instance**
- >Navigate to the EC2 console page, by clicking on `Services` in the upper left-hand menu. Type `EC2` in the text box and click on `EC2` found in the search results.
- >On the EC2 Dashboard page, click on `Instances` in the left-hand navigation.
- >Click `Launch Instance`.
- >Select the `Amazon Linux 2 AMI (HVM), SSD Volume Type` Amazon Machine Image (AMI). _**Important:**_ You are free to choose a different AMI, but to avoid excessive charges, pick one that says, `Free Tier Eligible`.
- >For the `Instance Type`, select the free-tier instance type of `t2.micro`.
- >Click on `Next: Configure Instance Details`.
- >Enter the 1 for the `Number of Instances`.
- >For Purchasing option, leave unchecked.
- >For Network, select the VPC that was created in the previous step, and then select the subnet in to which to launch the instance.
- >Keep the other default settings on this page as is.
3. **Attach an EBS volume**
- >Click on `Next: Add Storage` to attach an EBS volume. _**Important:**_ Here we already see there is a root volume (or device) attached to your instance, this is an EBS volume. We are going to add additional storage.
- >To attach additional storage, click on `Add New Volume`.
- >Select `Delete on Termination` and keep the other default settings.
- >Click `Review and Launch`.
- >Click `Launch Instances`.
- >Generate and download a new key pair and then launch the instance. _**Important:**_ This will allow you to SSH into your instance from your local machine. This is a one-time process, so generate and download the new key pair now.
- >The launch will take a couple of minutes, select `View Instances` during the wait.
- >Check the instance state, it should say running.
4. **Cleanup & Disable EC2 Instance:** To avoid recurring charges for leaving an instance running, let’s disable the EC2 instance and terminate the VPC
- >From the EC2 Dashboard, select the instance just created, click `Actions`, then `Instance State`, and then select `Terminate`.
- >From the VPC Dashboard, select the VPC just created, click `Actions`, then `Delete VPC`.

# Why do we need compute power in in the cloud?
The ability to run application code in the cloud without having to provision or manage servers is a software developer's dream come true. Placing your code in an environment that automatically scales offers high availability and fault tolerance, frees you up to focus on what's most important, adding new features to or fixing issues with your existing systems. 

Compute power in the cloud is a faster way to build applications. Compute power in the cloud provides no servers to manage, the ability to continuously scale, the ability to run code on demand in response to events, and you only pay when your code runs. 

**Compute Power In The Cloud**

Compute power in the cloud is a faster way to build applications, providing:

- no servers to manage (i.e. serverless)
- ability to continuously scale
- ability to run code on demand in response to events
- pay only when your code runs

# Lambda
AWS Lambda provide you compute power in the cloud by letting you execute code without standing up or managing servers. Just think of Lambda as a chunk of code that runs in the cloud, and **it's meant to do one specific task**. Lambda should really focus on one specific task because there's currently a **time limit of 15 minutes** which was recently increased from 5 minutes.

An application developed using Lambda is considered to be **serverless** because you're not concerned with the server your code is running on. 

Lambda offers several **benefits**. 

- You only pay for the compute time you consume and you are not charged when your code is not running. 
- You can author code locally and upload it OR you can write code directly via the **Lambda Console**. 
- Lambda is **event-driven**, so you can run your code based on certain events happening, like a file upload, or a record being inserted in a database. 
- Once the code is uploaded, the environment takes care of everything needed to run and scale your code. 

Lambda supports several **run-time environments**:

- Node.js
- Python
- Ruby
- Java
- Go
- .NET

**NOTE:** If you need a language that's not supported, you can use custom run-times, so the environment is very flexible.

**Lambda**

AWS Lambda provides you with computing power in the cloud by allowing you to execute code without standing up or managing servers.

**Tips**

- Lambda is found under the Compute section on the AWS Management Console.
- Lambdas have a time limit of 15 minutes.
- The code you run on AWS Lambda is called a “Lambda function.”
- Lambda code can be triggered by other AWS services.
- AWS Lambda supports Java, Go, PowerShell, Node.js, C#/.NET, Python, and Ruby. There is a Runtime API that allows you to use other programming languages to author your functions.
- Lambda code can be authored via the console.

**Resources**

- [AWS Lambda](https://aws.amazon.com/lambda/)

# Lambda - Demo

See the video [here](https://youtu.be/grV-jThkxDM).

# Lab - Create and Execute a Lambda
By the end of this lab, you will be able to:

- Author a Lambda function using Node.js via the console
- Test a Lambda function via the console

### Steps:
1. **Create a Lambda Function**
- >On the AWS Management Console page, type `lambda` in the `Find Services` box and then select `Lambda`.
- >Click the “Create function” button and select `Author from scratch`.
- >Enter a `Function name` and select `Node.js 8.10` as the runtime.
- >For `Permission`, click `Choose or create an execution role`, and select `Create a new role with basic Lambda permissions`.
- >Click `Create function`.
2. **Modify a Lambda Function**
- >Scroll down to the code for the Lambda function.
- >Replace the code on Line 5 with the statement below:
```js
body: JSON.stringify('Hello ' + event.key1 + ' from Lambda!'),
```
- >Click the `Save` button in the upper right-hand corner.
- >Scroll down to the `Basic Settings` section.
- >>For the Description, enter `Udacity Function`.
- >>Change the `Timeout` from 3 seconds to 10 minutes.
- >>Click the `Save` button in the upper right-hand corner.
3. **Test a Lambda Function**
- >Click on the `Test` button in the upper right-hand corner.
- >Ensure the `Event template` is `Hello World`.
- >For the `Event name` enter `TestEvent`. _**Important:**_ The name cannot contain spaces.
- >Update the JSON to the statement below, replacing the statement with your name.
```json
{
"key1": "Place your name here"
}
```
4. **Click `Create`.**
5. **Click the `Test` button in the upper right-hand corner again.**
6. **Scroll up to see the output in the `Execution Results` pane.**
7. **Review your results in the window.**

# Elastic Beanstalk
We've discussed the need for servers in the cloud. In our EC2 lab, we stood up our own server. AWS provides services that make the process of standing up servers and deploying applications to them easier. 

**Elastic Beanstalk** is an orchestration service that allows you to deploy a web application at the touch of button by spinning up or provisioning all of the services that you need to run your application. This service is essential because it automates the process of getting applications setup on the AWS infrastructure. 

At a click of a button, Elastic Beanstalk can create an EC2 instance, setup auto-scaling, and an elastic load balancer for you. You still retain control of the services automatically spun up, and you can administer them separately if you so choose. 

Elastic Beanstalk supports Java, PHP, Python, .NET, Node.js, Ruby, and Docker, and several common cert rephrase, and several common servers like Apache, HTTP, Tomcat, Engine X, IIS, etc. 

Elastic Beanstalk can even spin up database instances for you, VPCs and security groups all while deploying your code. 

**Resources**

- [AWS Elastic Beanstalk Overview](https://aws.amazon.com/elasticbeanstalk/)
- [What is AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html)

# Lab - Deploy App to Beanstalk
In this hands-on exercise, you will use Elastic Beanstalk to deploy a web application to the cloud.

**DOWNLOAD THIS:** [WAR file](https://s3.amazonaws.com/video.udacity-data.com/topher/2019/June/5d0296f8_udacity/udacity.war) containing the web application code.

### Steps:
1. **Access Elastic Beanstalk service from AWS Management Console**
- >On the AWS Management Console page, type `elastic beanstalk` in the `Find Services` box and then select `Elastic Beanstalk`.
- >If this is your first time accessing Elastic Beanstalk, click the `Get started` button.
- >Enter an `Application name`.
- >Under `Platform`, click the dropdown for `Choose a platform`. Select `Tomcat`.
- >Under `Application code`, select `Upload your code`. Click the `Upload` button.
- >Under `Upload your code`, make sure `Local file` is selected for `Source code origin`.
- >Click `Choose File` and upload the downloaded WAR file (link above in pre-requisites), `udacity.war`.
- >Click the `Upload` button.
- >Click the `Create application` button. _**Important:**_ It will take about 10 minutes for your application to be created. There are several resources that need to be spun up to support your application. Your application is created once you see a green check mark and the `Health` of your application is `Ok`.
- >After the application is created, copy the application’s URL. _**Important:**_ The URL can be found on the top of the page, to the right of your application’s name.
2. **Test the deployed web application in a browser**
- >Navigate to a web browser like Chrome or Safari.
- >Paste the application URL and append `/message` on the end of the URL.
- >Upon successfully accessing that URL, you will see the text `Hello World` in your browser window.
3. **Inspect the EC2 instance created for you**
- >Navigate to the EC2 console and inspect the instance that was created for you. The instance has the same name as your application. You can administer and manage this EC2 as if you created it yourself.
4. **Cleanup and delete resources**
- >To clean up the resources to avoid recurring charges, navigate back to the Elastic Beankstalk console.
- >Select your application.
- >Select the `Actions` button in the upper-right hand corner.
- >Select `Terminate environment`.
- >Enter the name of the application to be deleted.
- >Click the `Terminate` button.
- >After the application is terminated, you will be brought to the main page for the application.
- >Click on the `Actions` button in the upper right-hand corner.
- >Select `Delete application`.
- >Enter the name of your application.
- >Click the `Delete` button.

# Recep

See the video [here](https://youtu.be/0Ig9MwaxQq0).

