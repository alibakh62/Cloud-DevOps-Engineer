# Introduction
Now that you have you server, you'll need a logical method for organizing and storing the files that make up your website. You may even want to pull data from a database for display on your site, and as you consider high availability and high performance, you may even want to speed up the delivery of your site by caching large image files or videos. 

In this section, we'll learn about storage in the cloud and show to organize and store your files. Next, we'll learn how to process transactions in a relational database. We'll also learn about the concept of a data warehouse and even a NoSQL database. We'll wrap up by learning how to use a content delivery network to speed up the delivery of your website. 

# Why do we need storage in the cloud?
Companies today need to collect, store, and analyze the data they've collected over the years at a massive scale. Storage services in the cloud provide a place for companies to store data, providing several benefits like **durability**, **availability**, and **scalability**. 

- **Durability** guarantees that you will not lose the data that you upload to the cloud. High durability gives you the peace of mind that your data will be there in the future. 
- **Availability** addresses how quickly you can access your data. High availability provides fast and reliable access to the data you stored in the cloud. 
- **Scalability** allows applications runing in your environment to always meet demand seamlessly. By adding or removing the resouces necessary to maintain steady-state and fast response time. There are three types of scaling: **vertical scaling**, **horizontal scaling**, and **diagonal scaling**. 
- >**Vertical scaling** or **scaling up** is where you modify your server to meet demands. An example of this would be adding more memory or capacity to a single server. 
- >**Horizontal scaling** or **scaling out** is where you add or remove servers to meet demands. You may start out with two servers and end up with six servers to support demand. 
- >**Diagonal scaling** is a combination of horizontal and vertical scaling and offers maximum flexibility. 

### Storage & Database Services
- Amazon Simple Storage Service (Amazon S3)
- Amazon Simple Storage Service (Amazon S3) Glacier
- DynamoDB
- Relational Database Service (RDS)
- Redshift
- ElastiCache
- Neptune
- Amazon DocumentDB

# S3 & Glacier
Amazon Simple Storage Service (S3) is an _**object storage**_ system in the cloud. Think of it like a file system in the cloud where you load files such as text documents, image files, HTML files, or whatever you need to store. 

When you upload a file to S3, it gets a unique URL that can then be used to access it. All objects or files are stored in what's called a **bucket**, and **one bucket can hold millions of objects**. S3 bucket live in a region, but bucket names must be globally unique. S3 is designed for _durability_ of 99.99s of objects across _multiple availability zones_ and 99.99 _availability_ over a given year. So, **excellent durability and availability!**

There are several _use cases_ for S3:

- hosting static websites
- content delivery
- backup and recovery 
- archving and big data
- application data
- hybrid cloud storage

There are several S3 _storage classes_. **Storage classes** are essentially different data access levels for your data at certain price points. One storage class called **S3 Glacier** is more for _**data archiving**_ purposes and you should place data there that you don't intend to access frequently. 

**Glacier** is _cheaper_ than the **S3 Standard Class**, but **data retrieval** can be _a few minutes up to hours_. 

So, **when would you want to use Glacier over S3 Standard Class?** Suppose you have an application that generates a lot of log files every month, and for audit purposes you need to keep those files around. You don't intend to access those files often, but they do need to be made available once a year to the auditors. Glacier would be the perfect place to perserve those files since they would be infrequently accessed. 

### Storage Classes
S3 offers several [storage classes](https://aws.amazon.com/s3/storage-classes), which are different data access levels for your data at certain price points.
- S3 Standard
- S3 Glacier
- S3 Glacier Deep Archive
- S3 Intelligent-Tiering
- S3 Standard Infrequent Access
- S3 One Zone-Infrequent Access

### Tips
- S3 is found under the Storage section on the AWS Management Console.
- A single object can be up to 5 terabytes in size.
- You can enable Multi-Factor Authentication (MFA) Delete on an S3 bucket to prevent accidental deletions.
- **S3 Acceleration** can be used to enable fast, easy, and secure transfers of files over long distances between your data source and your S3 bucket.

**Resources**

- [Amazon S3](https://aws.amazon.com/s3/)
- [Amazon S3 Glacier](https://aws.amazon.com/glacier/)
- [What is Amazon S3 Glacier](https://docs.aws.amazon.com/amazonglacier/latest/dev/introduction.html)

# Demo - S3 & Glacier

See the video [here](https://youtu.be/4J2eJMy6nCw).

# DynamoDB
NoSQL databases are taking the world by storm. **DynamoDB** is one such database, and it fits well with modern day:
- serverless web applications, 
- microservices, 
- gaming, 
- IoT data, 
- and mobile backends that need to quickly scale and handle large amounts of data or millions of of requests per second. 

Traditional databases like Oracle don't handle this type of load or scale that well. **So, how's this possible?**

Unlike traditional databases, NoSQL databases are considered to be _schema-less_. **Schema-less** simply means that the database doesn't contain a fixed or rigid data structure, and can easily change on the fly, based on the data being passed in. This offers great flexibility.

Additionally, **data is stored in JSON or JSON like text**. JSON is a simple text representing data in key value pairs. Each row or **record** in a DynamoDB tables is called a **document**. 

DynamoDB is a **fully managed** service offered by AWS, meaning you don't have worry about provisioning or managing servers, or patching or upgrading your databases. AWS does that for you. 

Many of the world's fastest growing businesses such as Lyft, Airbnb, Netflix, and Snap, as well as enterprises such as Samsung, Toyota, and Capital One depends on this scale and performace of DynamoDB to support their mission critical workloads. 

### Tips
- DynamoDB is found under the Database section on the AWS Management Console.
- DynamoDB can handle more than 10 trillion requests per day.
- DynamoDB is serverless as there are no servers to provision, patch, or manage.
- DynamoDB supports key-value and document data models.
- DynamoDB synchronously replicates data across three AZs in an AWS Region.
- DynamoDB supports GET/PUT operations using a primary key.

**Resources**

- [Amazon DynamoDB Overview](https://aws.amazon.com/dynamodb/)
- [What is Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html)

# Demo - DynamoDB

See the video [here](https://youtu.be/Dxmd3PS4Q6s).

# Lab - DynamoDB
In this hands-on exercise, you will create a NoSQL database in the cloud.

### Steps:
1. **Access the DynamoDB service from AWS Management Console**
- >On the AWS Management Console page, type "dynamo" in the `Find Services` box and then select `DynamoDB`.
- >On the DynamoDB Console, click `Create table`.
- >Enter `Course` as the `Table name`.
- >Enter `Name` in for the `Partition key` and ensure `String` is selected. _**Note:**_ The partition key spreads data against partitions for scalability.
- >Keep the remainder of the defaults, and click the “Create” button.
2. **Add Data to the Table**
- >Once the table is created, click on the `Items` tab.
- >Click `Create item`.
- >>In the data entry window, type the following:
- >>>For name, enter, `Course 1` and click `Save`    
- >>>Click the `+` icon to add additional fields:
- >>>>Select `Insert`
- >>>>Select `String`
- >>>>For the field name, enter `Teacher`
- >>>>For the value, enter `Kesha Williams`
- >>>>Click `Save`
- >Follow the same process to add 5 more documents.
3. **Query Data in a Table**
- >In the dropdown that contains `Scan`, change it to `Query`.
- >Where it says `Enter value`, in the row next to the `name` Partition key, enter `Course 1` and click `Start Search`.
- >You should see your search results appear in the window.
4. **Cleanup and delete resources**
- >To clean up the resources to avoid recurring charges, ensure the table name is selected.
- >Click on the `Delete table` button.
- >Ensure `Delete all CloudWatch alarms for this table` is selected and click `Delete`.

# Relational Database Service (RDS)
Most applications need to process or store data for later use. Relational databases like Oracle, Postgres, MySQL, etc. serve this purpose. However, database administration is hard, and time-consuming, and often requires specialized skills, or if you don't have specialists it takes time away from developers responsible for building applications. 

Database administrative tasks include:
- upgrades
- patching
- installs
- backups
- monitoring
- performance checks
- security
- etc.

**RDS** is a service aids in the administration and management of databases. RDS is essentially sits on top of your database to help you manage your database by automating time-consuming administrative tasks. 

RDS is able to manage popular database engines like Oracle, Postgres, MySQL, MariaDB, and SQL Server. RDS even supports Amazon's proprietory relational database engine, **Aurora**, which supports MySQL and Postgres. 

RDS provides features like:
- Failover and backups
- Restoration and encryption
- Security and monitoring
- Data replication
- Ability to scale across a global footprint

**Resources**

- [What Is A Relational Database](https://aws.amazon.com/relational-database/)
- [Amazon Relational Database Service](https://aws.amazon.com/rds/)
- [AWS Product Databases using Relational Databases](https://aws.amazon.com/products/databases/)

# Demo - RDS

See the video [here](https://youtu.be/MvenEn3HB3s).

# RedShift
RedShift is a cloud data warehousing service to help companies manage big data or an extremely large volume of data that needs to be analyzed or reported against and quickly scale. 

RedShift is a **managed** service that allows you to **run fast queries** against your data using **SQL**. **ETL (Extract, Transform, Load)** tools, and **BI (Business Intelligence)** tools. 

RedShift also automates administrative and maintenance tasks. **A data warehouse is designed for fast query and analysis not transaction processing**, and usually contains historical data from transactional systems. For example, let's say you manage your website that allows users to order products online. The more recent transactions, like the orders for the current year, may live in a relational database like Oracle, because you may need to access them during day-to-day operations. But orders from, say 10 years ago, maybe archived to a data warehouse like RedShift. 

RedShift stores data in a **column format** as opposed to a **row** store like a relational database. This aids in fast query and analysis. 

### Tips
- Redshift can be found under the Database section on the AWS Management Console.
- Redshift delivers great performance by using machine learning.
- Redshift Spectrum is a feature that enables you to run queries against data in Amazon S3.
- Redshift encrypts and keeps your data secure in transit and at rest.
- Redshift clusters can be isolated using Amazon Virtual Private Cloud (VPC).

**Resources**

- [What Is Amazon Redshift](https://docs.aws.amazon.com/redshift/latest/mgmt/welcome.html)
- [Amazon Redshift Overview](https://aws.amazon.com/redshift/)

# Lab - RDS
In this hands-on exercise, you will create a MySQL database instance using RDS.

### Steps:
1. **Launch MySQL Database**
- >On the AWS Management Console page, type `rds` in the `Find Services` box and then select `RDS`.
- >On the left-hand side, click `Databases`.
- >Click `Create database`.
- >Under engines option, select `MySQL` and click the `Next` button
- >Under `Instance specifications`, leave the defaults.
- >Under the `Settings` section:
- >>Enter a name for the instance under `DB instance identifier`
- >_**Note:**_ This will not be the database name.
- >Enter a `Master username`
- >Enter a `Master password` and confirm the password.
- >Click `Next`
- >For `Virtual Private Cloud (VPC)`, select `Create new VPC`.
- >Ensure `Create new DB Subnet Group` is selected.
- >Leave the defaults for `Subnet group`, `Public accessibility`, `Availability zone`, and `VPC security groups`.
- >Under `Database options`, enter a `Database name` and leave the rest as defaults.
- >Under `Deletion protection`, uncheck `Enable deletion protection`. _**Important:**_ In a real production scenario, you would leave this option checked.
- >Click Create database`.
2. **View Instance Details**
- >Once your database is created, open it by clicking on `View DB Instance details`.
- >Make sure the `DB instance status` shows `available`.
- >Scroll through and observe how the instance is configured.
3. **Delete Database Instance** Clean up the resources to avoid recurring charges.
- >From the RDS Dashboard homepage, select `Databases` from the left-hand navigation pane.
- >Select your newly created database by clicking on the name radio button next to the name.
- >From the `Actions` menu, select `Delete`.
- >In the confirmation popup:
- >>Uncheck `Create final snapshot`
- >>Select 
```text
I acknowledge that upon instance deletion, automated backups, including system snapshots and point-in-time recovery, will no longer be available.
```
- >>Enter the requested confirmation for deletion.
- >>Click the `Delete` button

# Why do we need content delivery in the cloud?
A **Content Delivery Network (CDN)** speeds up delivery of your static and dynamic web content such as web-pages, casecading style sheets, JavaScript logic, and images. Typically, content is cached or stored for a certain period of time, and when a user requests your website or other web content, content is pulled from the cached speeding up the delivery of the content to your users. 

A CDN reduces latency and decreases the load on your servers, which provides a good end user experience to your customers and users of your applications. **Latency** simply means the time it takes to respond to a request. So, from the time a user attempts to access your website to the time it takes for your website to load. High latency causes your website to take a long time to load while low latency causes your website to load quickly. Low latency is a good and CDNs assist with this. 

To wrap up: A Content Delivery Network (or CDN) speeds up delivery of your static and dynamic web content by caching content in an Edge Location close to your user base.

### Benefits
The benefits of a CDN includes:

- low latency
- decreased server load
- better user experience

# Cloud Front
Cloud Front is Amazon service for content delivery. Cloud Front speeds up the delivery for your content through Amazon's worldwide network of many data centers called **edge locations**. As in a typical CDN, your content is cached or stored for a certain period of time at an edge location that is close to the user. When a user requests your website or other web content, the edge location is consulted first. If the content is not there, then your content is pulled from the origin or the original source, which may be far away from the user's location, then it's stored at the edge location and then delivered to your users. All subsequent requests should now be faster because the content is now stored at the edge location. 

You can configure how long an item remains cached before a refresh, or you can manually expire or remove content from the cache, should it need to be changed.

### Cloud Front
CloudFront is used as a global content delivery network (CDN). Cloud Front speeds up the delivery of your content through Amazon's worldwide network of mini-data centers called Edge Locations.

CloudFront works with other AWS services, as shown below, as an origin source for your application:
- Amazon S3
- Elastic Load Balancing
- Amazon EC2
- Lambda@Edge
- AWS Shield
  
### Tips
- CloudFront is found under the Networking & Content Delivery section on the AWS Management Console.
- Amazon countinously adds new Edge Locations.
- CloudFront ensures that end-user requests are served from the closest edge location.
- CloudFront works with non-AWS origin sources.
- You can use GeoIP blocking to serve content (or not serve content) to specific countries.
- Cache control headers determine how frequently CloudFront needs to check the origin for an updated version your file.
- The maximum size of a single file that can be delivered through Amazon CloudFront is 20 GB.

**Resources**

- [Amazon CloudFront Overview](https://aws.amazon.com/cloudfront/)
- [What is Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html)

# Demo - Cloud Front

See the video [here](https://youtu.be/ST3ZOvVo36s).

# Lab - S3 & Cloud Front
In this hands-on exercise, you will create a S3 bucket with a Cloud Front distribution to speed up our the delivery of content to our website.

### Steps:
1. **Create S3 Bucket**
- >On the AWS Management Console page, type `S3` in the `Find Services` box and then select `S3`.
- >Click `Create bucket`
- >Enter a `Bucket name`.
- >>_**Note:**_ Bucket names must be globally unique.
- >Click the `Create` button.
- >Once the bucket is created, click on the name of the bucket to open the bucket to the contents.
2. **Upload Object to Bucket**
- >Once the bucket is open to its contents, click the `Upload` button.
- >Click the `Add Files` button.
- >Select a file from your local computer to upload.
- >Click `Open`.
- >Click `Upload`.
3. **Create CloudFront Distribution**
- >Select `Services` from the top left corner.
- >Enter `cloud front` in the `Find a service by name or feature` text box and select `Cloud Front`.
- >Click `Create Distribution`.
- >Under the `Web` delivery method, select `Get Started`.
- >Under `Origin Settings`:
- >Under `Origin Domain Name`, select the S3 bucket that you just created.
- >Under `Origin Path`, enter `/` to indicate the root level.
- >Leave the defaults for the rest of the options.
- >Click `Create Distribution`.
- >>_**Note:**_ It may take up to 10 minutes for the CloudFront Distribution to be created.
4. **Delete Bucket and Distribution**
- >To delete the Cloud Front distribution, click on the radio button next to the `Delivery Method` for the distribution. Click `Disable` and then `Yes`, Disable. Click `Close`.
- >Once the distribution is disabled, you can delete it by selecting the radio button next to the `Delivery Method` and clicking the `Delete` button.
- >To delete the S3 bucket, navigate to S3, but clicking on `Services` and typing `S3` in the `Find Services` box and then select `S3`.
- >Select the radio button next to the name of the bucket you want to delete.
- >Click `Delete`.
- >Type the name of the bucket to confirm deletion.
- >Click the `Confirm` button.


  

