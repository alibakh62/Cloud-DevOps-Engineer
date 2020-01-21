# Introduction
Now that we know how to route users to our website and handle the incoming traffic, we will want the ability to notify or alert our users when certain events happen. 

As you add additional features to your travel blogging website like the ability to search or even the ability to make a hotel reservation, you might consider adopting a container technology like Docker to help you bundle your web application package that can easily move from environment to environment. 

In this section, we'll learn how to send notifications to our users using cloud services. We will also learn how two systems communicate using messaging. We'll then wrap up by learning about containers and why they are so useful for modern application development. 

# Why do we need messaging in the cloud?
There are often times that users of your applications need to be notified when certain events happen. For example, if a large withdrawal is made from your bank account, it would be nice to receive a text message. 

Notifications such as text messages or emails can be sent through services in the cloud. The use of the cloud offers benefits like lowered cost, increased storage, and flexibility. Through cloud services, you can send notifications and even track the life cycle of those notifications. 

**Messaging** is a form of notifications, but instead of human as the recipient of the message, an application is. Messaging typically occurs between internet-based applications and devices. One system can send a message to another system. 

[video](https://youtu.be/fTCEEDPIMBA).

There are often times that users of your applications need to be notified when certain events happen. Notifications, such as text messages or emails can be sent through services in the cloud. The use of the cloud offers benefits like lowered costs, increased storage, and flexibility.

# Simple Notification Service (SNS)
Amazon **Simple Notification Services (SNS)** is AWS cloud service that allows you to send notification to the users of your applications. SNS allows you to de-couple the notification logic from being embedded in your applications, and allows notifications to be published to a large number of subscribers. 

SNS uses **publish/subscribe model**. This means that in order for your users to be notified, they have to sign up or subscribe first. Subscribers can be a person or another AWS service. Notifications can be sent to end-users using mobile push, text messages, and email. 

[video](https://youtu.be/vW60dbTMQS0).

Amazon Simple Notification Service (or SNS) is a cloud service that allows you to send notifications to the users of your applications. SNS allows you to decouple the notification logic from being embedded in your applications and allows notifications to be published to a large number of subscribers.

## Features

-   SNS uses a publish/subscribe model.
-   SNS can publish messages to Amazon SQS queues, AWS Lambda functions, and HTTP/S webhooks.

## Tips

-   SNS is found under the Application Integration section on the AWS Management Console.
-   SNS Topic names are limited to 256 characters.
-   A notification can contain only one message.

#### Resources

----------

-   [Amazon SNS Overview](https://aws.amazon.com/sns/)
-   [What is Amazon SNS](https://docs.aws.amazon.com/sns/latest/dg/welcome.html)

# Demo SNS
See the demo [here](https://youtu.be/wooRtQ5n10k).

# Why do we need queuing technology?
A **queue** is a data structure that holds requests, sometimes called messages. A queue is similar in concept to waiting in line at a department store. People join the line and wait their turn ro checkout. Similarly, messages join a queue and wait their turn to be processed. Messages in a queue are commonly processed in order, **first-in first-out (FIFO)**. 

Let's say you have a money transfer app with millions of users sending funds back and forth. Instead of making user wait for confirmation while money is being transferred throug the platform, you let them know their request was submitted and allow them to go about their day. Behind the scenes, you place the money transfer request on a queue, and process those requests when system resources are available. Since the money transfer process along with doing security checks could take a while to process. 

The benefit of using a queue is that the user doesn't have to sit there waiting. The use of a messaging queue will help improving performance and scalability. The use of asynchronous processing where a user doesn't wait for a response, improves the overall user experience. 

[video](https://youtu.be/WnkroShldb8).

A queue is a data structure that holds requests called messages. Messages in a queue are commonly processed in order, first in, first out (or FIFO).

Messaging queues improve:

-   performance
-   scalability
-   user experience

# Simple Queue Service (SQS)
Amazon **Simple Queue Service** is a fully managed queuing service that allows you to integrate queuing functionality in your application. With SQS, you can send, store, and receive messages between applications without losing messages. 

SQS offers two types of message queues: **Standard**, and **FIFO**. 

**Standard queues** offer _**Best-effort Ordering**_, while **SQS FIFO queues** are designed to guarantee that messages are processed exactly once in the exact order they were added to the queue. 

Let's say you have created a course registration system, and to improve scalability, you send account creation and course registration messages to a queue. In order for a student to register for a course, their account must first be created then they can be registered. The ordering of these steps is very important. You do not want a student to attempt to register for a course before their account is created. Since ordering is important, a FIFO queue should be used in this case.

[video](https://youtu.be/QdmaZx1jkcw).

Amazon Simple Queue Service (SQS) is a fully managed message queuing service that allows you to integrate queuing functionality in your application. SQS offers two types of message queues: standard and FIFO.

## Features

-   send messages
-   store messages
-   receive messages

## Tips

-   The Simple Queue Service (SQS) is found under the Application Integration on the AWS Management Console.
-   FIFO queues support up to 300 messages per second.
-   FIFO queues guarantee the ordering of messages.
-   Standard queues offer best-effort ordering but no guarantees.
-   Standard queues deliver a message at least once, but occasionally more than one copy of a message is delivered.

#### Resources

----------

-   [Amazon SQS Overview](https://aws.amazon.com/sqs/)
-   [What is Amazon SQS](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)

# Demo - SQS
See the demo [here](https://youtu.be/3m_9ja6qrNw).

# Lab - SNS
In this hands-on exercise, you will learn how to send alerts via SNS by creating a topic, subscribing to a topic, and publishing an alert message to a topic.

## Prerequisites:

-   AWS Account

## Topics Covered:

By the end of this lab, you will be able to:

-   Create a topic
-   Subscribe to a topic
-   Publish a message to a topic

## Steps:

1.  **Create a Topic**
    -   On the AWS Management Console page, type  `sns`  in the  `Find Services`  box and then select  `Simple Notification Service`. The SNS Dashboard appears.
    -   On the left-hand menu, click on  `Topics`.
    -   Click on  `Create topic`.
    -   Enter a name for your topic in the  `Name`  field.
    -   In the  `Access policy – optional`  section, for the  `Define who can publish messages to the topic`  section, ensure  `Everyone`  is selected allowing anyone to publish to the topic. For the  `Define who can subscribe to this topic`  section, ensure  `Everyone`  is selected.
    -   Click  `Create Topic`. The topic screen will display.
2.  **Subscribe to a Topic**
    -   Click  `Create subscription`  from the  `Subscriptions`  section.
    -   For the  `Protocol`  field, select  `Email`.
    -   For the  `Endpoint`, enter the email that should receive the notifications.
    -   Click  `Create subscription`.
    -   The subscription page will display and the status will be  `Pending confirmation`. After your subscription is created, you must confirm it.
    -   In your email client, check the email address that you provided for the  `Endpoint`  and choose Confirm subscription in the email from Amazon SNS.
    -   In your web browser, a subscription confirmation screen appears.
3.  **Publish a Message to a Topic**
    -   From the menu on the left-hand side, click on  `Topics`.
    -   Select the topic you created earlier and then click  `Publish message`.
    -   Enter a subject in the  `Subject`  field.
    -   Enter a value in the  `Message body to send to the endpoint`  box in the  `Message body`  section.
    -   Scroll down and click  `Publish message`.
    -   In your email client, read the email from Amazon SNS.

# Why do we need containers?
Enterprises are adopting container technology at an explosive rate. **Docker** is the leading container technology. There are several container orchestration services that help you manage your Docker clusters. **Kubernetes** is a container orchetration system for Docker containers similar to **Docker Swarm**. 

## Why are containers so popular?
A container consists of everything an application needs to run. The application itself and its dependencies like libraries, utilities, configuration files, etc. all bundled into one package. 

Instead of having to rebuild your application and its environment from scratch as it moves from environment to environment, say from development to production, you can easily move the entire container from environment to envinronment with any issues. Each container is an independent component that can run on its own. 

Let's say you have a huge monolith application, that you're migrating to a microservices architecture. The **microservices architecture** decomposes large complex monoliths systems into discrete, individual stand-alone components that can communicate among themselves, working together, or with external systems. A Docker container works well with the microservices use case because each microservice is its own independent component with no interdependencies.

[video](https://youtu.be/WXuXp3WSz6E)

Enterprises are adopting container technology at an explosive rate. A container consists of everything an application needs to run: the application itself and its dependencies (e.g. libraries, utilities, configuration files), all bundled into one package.

Each container is an independent component that can run on its own and be moved from environment to environment.

**We will be going more in-depth on the topic of Microservices in Course 4: Microservices at Scale using AWS & Kubernetes**

-   [General overview about Docker containers](https://docs.docker.com/engine/docker-overview/)
-   [Documentation on Docker Containers](https://www.docker.com/resources/what-container)

# Elastic Container Service (ECS)
Orchestration tools are used for automating deployment, scaling, and managing your containerized applications. **Amazon ECS** is a container orchestration service that supports Docker, assisting with managing your containers. There are several useful features including:

- launching and stopping Docker containers
- scaling your applications
- querying the state of your applications
- etc.

It is really a convenience type service to assist you with the administration of your Docker containers. 

[video](https://youtu.be/W3XqJWl38k8).

ECS is an orchestration service used for automating deployment, scaling, and managing of your containerized applications. ECS works well with Docker containers by:

-   launching and stopping Docker containers
-   scaling your applications
-   querying the state of your applications

## Tips

-   ECS is under the Compute section on the AWS Management Console.
-   You can schedule long-running applications, services, and batch processeses using ECS.
-   Docker is the only container platform supported by Amazon ECS.

#### Resources

----------

-   [Amazon ECS Overview](https://aws.amazon.com/ecs/)
-   [What is Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html)

# Demo - ECS
See the demo [here](https://youtu.be/2jVSICPoyNE).



