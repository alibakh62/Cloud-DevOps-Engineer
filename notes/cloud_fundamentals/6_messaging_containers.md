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

