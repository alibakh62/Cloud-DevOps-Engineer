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

