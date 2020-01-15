# Introduction
In this lesson we'll learn about security in the cloud, showing how to protect your data and systems. We'll talk about cloud security services that help us ensure that users are who they say they are, and they only have access to the specific data they need, and not everything else. 

# Why do we need security for our applications?
As adoption of cloud services has increased, so has the need for increased security in the cloud. It is important for companies to secure their customers data, especially data that is considered to be **Personally Identifiable Information (PII)**, such as social security number, bank account information, passport number, etc. 

Along with protecting the data, it is important to protect the applications that provide access to that data. The great thing about cloud security is that it not only protects the data, it also protects applications that access the data, and it even protects the infrastructure like servers that the applications run on. 

The way security is delivered, depends on the cloud provider and the security options it offers. 

## Security In The Cloud

As adoption of cloud services has increased, so has the need for increased security in the cloud. The great thing about cloud security is that it not only protects data, it also protects applications that access the data. Cloud security even protects the infrastructure (like servers) that applications run on.

The way security is delivered depends on the cloud provider you're using and the cloud security options they offer.

See the video [here](https://youtu.be/tTDVF_GtAyw).

# AWS Shield
**AWS Shield** is a **managed DDoS (Distributed Denial of Service)** protection service that safeguards web applications running on AWS. 

A **DDoS attack** is an attempt to make a website or an application unavailable by overwhelming it with traffic from multiple sources. When a server is overwhelmed, it typically crashes and can no longer serve requests. An attack like this would leave your website or web application unavailable which could result in a loss of revenue. 

**AWS Shield** is a service that you get out of the box. It is always running automatically and as a part of the free standard tier. If you want to use more of the advanced features, you'll need to utilize the paid tier. 

See the video [here](https://youtu.be/BBgUtzXUGjI).

## AWS Shield

AWS Shield is a managed DDoS (or Distributed Denial of Service) protection service that safeguards web applications running on AWS.

AWS Shield is a service that you get "out of the box", it is always running (automatically) and is a part of the free standard tier. If you want to use some of the more advanced features, you'll have to utilize the paid tier.

## Tips

-   AWS Shield can be found under the Security, Identity, & Compliance section on the AWS Management Console.
-   AWS Shield Standard is always-on, using techniques to detect malicious traffic.
-   AWS Shield Advanced provides enhanced detection.

#### Resources
----------
-   [AWS Shield Overview](https://aws.amazon.com/shield/)

# AWS Web Application Firewall (AWS WAF)
**AWS WAF** provides a firewall that protects your web applications. A **firewall** is a network security mechanism that monitors and controls incoming and outgoing network traffic based on preset security rules. 

A **firewall** stands in front of your application as a way to guard who can access it. The rules that you set up inside of your firewall allows certain traffic or block it. 

Firewalls are largely used to protect your web applications from unintended access. **WAF** can stop common web attacks such as **SQL injection**, **cross-site scripting**, etc. by reviewing the data being sent to your application and stopping well-known attacks. 

See the video [here](https://youtu.be/79_HJIwT-fE).

## AWS WAF

AWS WAF (or AWS Web Application Firewall) provides a firewall that protects your web applications.

WAF can stop common web attacks by reviewing the data being sent to your application and stopping well-known attacks.

## Tips

-   WAF is found under the Security, Identity, & Compliance section on the AWS Management Console.
-   WAF can protect web sites not hosted in AWS through Cloud Front.
-   You can configure CloudFront to present a custom error page when requests are blocked.

#### Resources
----------
-   [AWS Web Application Firewall](https://aws.amazon.com/waf/)

# Identity & Access Management (IAM)
Along with protecting your data and systems, we also need to ensure that users are who they say they are, and that they only have access to the specific data they need to and not everything. This concept is called **least priviledged access**. This is where the **IAM** service helps out. 

**IAM** is an AWS service that allows us to configure who can access our AWS account, services, or even applications running in our account. IAM is a global service and is automatically available across all regions. 

When you initially sign up for a free tier AWS account, the email address you used to sign up with becomes your root level account, and has full access and permission to any and everything within your account. I cannot stress enough that you must secure your root account, and that **you shouldn't use the root user credentials for everyday access**. 

One way to secure your root account is by using **Multi Factor Authentication (MFA)**, which will always require an additional form of authentication along with your password like, a code sent to your cell phone, or a code from a multi authentication app on your cell phone before logging you in. If you haven't secured your account in this manner, do it now!

There are several security concepts within IAM. An **IAM user** is an entity that you create an AWS to represent the person or service that interacts with services or applications running in your AWS account. A user in AWS consists of **username** and **access credentials** like a **console password on access key** which includes an **access key ID** and a **secret key**.  

An **IAM group** is a collection of users. You can specify permissions for a collection which makes permissions easier to manage. 

A **role** is an identity with permission or a set of priviledges that are not associated with a specific IAM user or IAM group. Roles can be attached to a user, and a user can assume a single role temporarily to perform a specific task. 

A **policy** is a way to define granular level permissions and can be attached to users, groups, and roles. AWS provides a pre-defined list of policies. Additionally, you can create your own custom policies using JSON. 

**NOTE:** EC2 security groups aren't technically a part of IAM. New AWS users often confuse it with an IAM security group but they are two totally different things. EC2 security groups are associated with an EC2 instance and act as a built-in firewall for your virtual servers to either allow or deny access. 

See the video [here](https://youtu.be/sECvyZxb7Cw).

## Identity & Access Management

Identity & Access Management (IAM) is an AWS service that allows us to configure who can access our AWS account, services, or even applications running in our account. IAM is a global service and is automatically available across ALL regions.

## Security Concepts

-   User
-   IAM Group
-   IAM Role
-   Policy

#### Resources
----------
-   [AWS IAM Overview](https://aws.amazon.com/iam/)
-   [What is IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)

