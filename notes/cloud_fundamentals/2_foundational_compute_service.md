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

