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



  

