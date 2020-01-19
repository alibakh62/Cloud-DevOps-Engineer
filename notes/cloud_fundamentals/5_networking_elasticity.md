# Introduction
You will need a way for users to find your website. That's where networking connectivity comes into play tou route internet traffic to your site. 

You'll also want to make sure that your website can handle the incoming traffic, providing peak performance to your users. The ability to scale up or down based on the load or how many users are using your applications at a given time is critical. 

## Additional Resources

We have also provided another lesson that covers the basic knowledge and tools required to configure and investigate network connectivity. This is a refresher course you can access under the "Extracurricular" Section within the Classroom. Here is the link to it:  [Networking](https://classroom.udacity.com/nanodegrees/nd9991/parts/f13626bd-985f-4085-88f5-65c2fce28762)

# Why do we need networking in the cloud? 
Networks reliably carry loads of data around the globe allowing for the delivery of content and applications with high availability. The network is the foundation of your infrastructure. Without it, you wouldn't be able to do your day-to-day job, things like check your email, or even access services on your smartphone. 

**Cloud networking** includes network architecture, network connectivity, application delivery, global performance and delivery.

**Network connectivity** includes services that offer reliable and cost-effective ways to route end-users to internet applications. 

Let's explore a real world example.

Every computer on the internet has an address, called an **IP address (Internet Protocol address)**, which is a long string of numbers. It's hard for a person to easily remember the long string of numbers to access a website. For example, Google's IP address is `74.125.21.147`. Although we're not using the IP address in the browser. Instead, we enter a user-friendly name: www.google.com. Behind the scenes, there is a **DNS (Domain Name System)** resolver that ask a **domain authority** for the IP address that maps to google.com. **Domain authority** is a service the domain names are registered with. You are then routed to that address and the Google's website displays on your browser.

[video](https://youtu.be/dr8mRps-UVg).

Networks reliably carry loads of data around the globe allowing for the delivery of content and applications with high availability. The network is the foundation of your infrastructure.

Cloud networking includes:

-   network architecture
-   network connectivity
-   application delivery
-   global performance
-   delivery

# Route 53
**Route 53** is AWS's cloud DNS service. It is a reliable and scalable service that has DNS servers distributed around the globe. 

It scales automatically to manage spikes in DNS queries, allows you to register a domain name or manage an existing one. Route's internet traffic to the resources for your domain and checks the health of your resources. 

The health checks are useful because they help to ensure that your web servers are up and running and offer DNS fail over to automatically route your website visitors to an alternate location to avoid site outages. 

[video](https://youtu.be/Orkgd16gcLk).

Route 53 is a cloud domain name system (DNS) service that has servers distributed around the globe used to translates human-readable names like  [www.google.com](http://www.google.com/)  into the numeric IP addresses like 74.125.21.147.

## Features

-   scales automatically to manage spikes in DNS queries
-   allows you to register a domain name (or manage an existing)
-   routes internet traffic to the resources for your domain
-   checks the health of your resources

## Tips

-   Route 53 is found under the Networking & Content Delivery section on the AWS Management Console.
-   Route 53 allows you to route users based on the user’s geographic location.

#### Resources

----------

-   [Amazon Route 53 Overview](https://aws.amazon.com/route53/)

# Why do we need elasticity in the cloud?
One of the main benefits of the cloud is that it allows you to stop guessing about capacity when you need to run your applications. When applications run in a traditional on-premises data center, you have to buy your servers upfront. Sometimes you buy too much, or you don't buy enough to support the running of your applications. 

With **elasticity**, your servers, databases, and application resources can automatically scale up or down based on the load, or how many users are using your applications at a given time. Resources can **scale up (vertically)** in Amazon EC2. This can easily be achieved by stopping an instance and resizing it to an instance type that has more RAM, CPU, IO, etc., or you can **scale out (horizontally)** which increases the number of resources, e.g. adding more servers. 

[video](https://youtu.be/RzdF5THMM_U)

One of the main benefits of the cloud is that it allows you to stop guessing about capacity when you need to run your applications. Sometimes you buy too much or you don't buy enough to support the running of your applications.

With elasticity, your servers, databases, and application resources can automatically scale up or scale down based on load.

# EC2 Auto Scaling
**EC2 Auto Scaling** is a service that monitors your EC2 instances and automatically adjust by adding or removing EC2 instances based on conditions you defined in order to maintain application availability and to provide peak performance to your users. 

EC2 Auto scaling works with **AWS Messaging Services** like the **Simple Notification Service (SNS)** to alert you when EC2 auto-scaling is launching or terminating your EC2 instances. You can configure the alert message to contain information about the terminated or launched instance and the reason for termination or launch.

There's also an AWS auto-scaling service that is different than the EC2 auto-scaling that allows you to set up other services such as _DynamoDB_ to automatically scale. 

[video](https://youtu.be/PHher5CL1iE).

EC2 Auto Scaling is a service that monitors your EC2 instances and automatically adjusts by adding or removing EC2 instances based on conditions you define in order to maintain application availability and provide peak performance to your users.

## Features

-   Automatically scale in and out based on needs.
-   Included automatically with Amazon EC2.
-   Automate how your Amazon EC2 instances are managed.

## Tips

-   EC2 Auto Scaling is found on the EC2 Dashboard.
-   EC2 Auto Scaling adds instances only when needed, optimizing cost savings.
-   EC2 predictive scaling removes the need for manual adjustment of auto scaling parameters over time.

#### Resources

----------

-   [Amazon EC2 Autoscaling Overview](https://aws.amazon.com/ec2/autoscaling/)
-   [What is Amazon EC2 Autoscaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html)

# Demo - EC2 Auto Scaling
See the demo video [here](https://youtu.be/zgy3Y2YyEy4).

In this hands-on exercise, you will use Auto Scaling to automatically launch Amazon EC2 instances in response to conditions you specify. You will also see auto scaling in action as it automatically provisions a replacement instance.

## Prerequisites:

-   AWS Account

## Topics Covered:

By the end of this lab, you will be able to:

-   Use auto scaling to launch EC2 instances
-   Create an auto scaling group
-   Test auto scaling

## Steps:

1.  **Create a Launch Configuration**
    
    -   On the AWS Management Console page, type  `EC2`  in the  `Find Services`  box and then select  `EC2`.
    -   Scroll down to the  `Auto Scaling`  section on the left-hand menu and click  `Auto Scaling Groups`.
    -   Click the  `Create Auto Scaling group`  button.
    -   Review the steps and click on  `Get started`.
    -   Create a launch configuration by first selecting an Amazon Machine Image (AMI). In the row for  `Amazon Linux 2 AMI (HVM), SSD Volume Type`, click the  `Select`  button.
        
        **_Note:_**  An AMI is a template for an instance that indicates the operating system, an application server, and applications.
        
    -   Confirm that  `t2.micro`  is selected.
        
    -   Click  `Next: Configure details`.
    -   Enter a name of your choosing in the  `Name`  field.
    -   Expand the  `Advanced Details`  section.
    -   Next to  `IP Address Type`, click on  `Assign a public IP address to every instance.`
    -   Click  `Next: Add Storage`. Review the screen.
    -   Click  `Next: Configure Security Group`.
    -   Ensure  `Create a new security group`  is selected.
    -   Click  `Review`.
    -   Click on  `Create launch configuration`.
    -   On the  `Select an existing key pair or create a new key pair`, select  `Create a new key pair`, enter a key pair name in the  `Key pair name`  field, and click  `Download Key Pair`.
    -   Click on  `Create launch configuration`.
2.  **Create an Auto Scaling Group**
    -   On the  `Create Auto Scaling Group`  page, enter a group name of your choosing in the  `Group name`  field, ensure the  `Group size`  is set to  `1`, for  `Network`  leave the default value. If no default value is shown, click on  `Create new VPC`, and select the first  `Subnet`  by clicking in the  `Subnet`  field.
    -   Click  `Next: Configure scaling policies`.
    -   Ensure that  `Keep this group at its initial size`  is selected.
    -   Click  `Review`.
    -   Review the selected options and click  `Create Auto Scaling group`.
    -   Click  `Close`.
3.  **Verify your Auto Scaling Group**
    -   Verify that the group has launched your EC2 instance by first ensuring the auto scaling group you just created is selected and examining the  `Details`  tab shown on the bottom of the screen.
    -   Click the  `Activity History`  tab. The status of your instance should be  `Successful`, which means the instance is launched.
    -   Click on the  `Instances`  tab. Notice the  `Lifecycle`  column states  `InService`.
4.  **Test Auto Scaling**
    -   Click on the  `Instances`  tab.
    -   Under the  `Instance ID`  column, click on the blue Instance ID link.
    -   You will be taken to the Amazon EC2 console Instances page.
    -   Your instance should be selected.
    -   Click the  `Actions`  button, scroll down to  `Instance State`, and select  `Terminate`. Then select  `Yes, Terminate`.
    -   In the left-hand navigation pane, click  `Auto Scaling Groups`.
    -   Click the  `Instances`  tab. You will eventually see a new instance appear. If the new instance doesn’t appear, click refresh occasionally to update the list.
    -   Click on the  `Activity History`  tab to review the history for the Instance.
5.  **Delete Auto Scaling Resources**
    -   At the top of the screen, click the  `Actions`  button next to the  `Create Auto Scaling group`.
    -   Click the  `Delete`  option.

# Elastic Load Balancing
**Elastic Load Balancer** is a service that balances load between two or more servers, stands in front of a web server, and provides **redundancy** and **performance**. 

**Redundancy** simply means that if you lose a server, the load balancer will send requests to other working servers. **Good performance** simply means that if a server starts having issues or bottlenecks, the load balancer will add more servers to the pool of available servers. 

[video](https://youtu.be/7DpXBqzBUrc).

Elastic Load Balancing automatically distributes incoming application traffic across multiple servers.

Elastic Load Balancer is a service that:

-   Balances load between two or more servers
-   Stands in front of a web server
-   Provides redundancy and performance

## Tips

-   Elastic Load Balancing can be found on the EC2 Dashbaoard.
-   Elastic Load Balancing works with EC2 Instances, containers, IP addresses, and Lambda functions.
-   You can configure Amazon EC2 instances to only accept traffic from a load balancer.

#### Resources

----------

-   [Amazon Elastic Load Balancing Overview](https://aws.amazon.com/elasticloadbalancing/)

# Demo - Load Balancer
See the demo [here](https://youtu.be/k94dp2caK-o).


