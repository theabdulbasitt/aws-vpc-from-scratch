<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Virtual Private Cloud

**Project Link:** [View Project](http://nextwork.ai/projects/aws-networks-vpc)

**Author:** Abdul Basit  
**Email:** iabdulbasit.se@gmail.com

---

## Build a Virtual Private Cloud (VPC)

![Image](http://nextwork.ai/intense_magenta_peaceful_coriander/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project!

In this project, I will demonstrate how I designed and implemented a Virtual Private Cloud (VPC) on Amazon Web Services. 
VPC is a private, Isolaated section of Cloud where you can  resources in a virtual network that you define. It gives you control over your network environment, including IP address ranges, subnets, route tables, and network gateways.

### What is Amazon VPC?

### Personal reflection

---

## Virtual Private Clouds (VPCs)

### What I did in this step

Before moving ahead I have created a an AWS Root Account, and also create an Iam account for better security, without any kind of breach. This is a best practice and you will come to know about this when working in a team or organization.

### How VPCs work

To put it simply, without VPCs, every AWS resource would exist in one giant, open space in the cloud, like a country without cities or districts.

Resources would be randomly scattered with no privacy or personal space, so everyone could see and access everyone else's resources.

VPCs are the reason why resources can be made private to you. You also get control over resources in a VPC, so you can organize how they communicate and integrate with each other without the public internet.

p.s. if we're still a little unsure about the difference a VPC makes, here's another analogy that might help. Imagine if every file in Google Drive from any account was put into the same folder with no privacy or subfolders. You'd have to find your files amongst everything uploaded by everyone, which makes managing/securing your files really hard! That's what managing your resources would feel like without VPCs.

### Why there is a default VPC in AWS accounts

When you created your AWS account, AWS automatically sets up a default VPC for you! This default VPC is why you could launch resources (e.g. EC2 instances) and connect services together from Day 1 of using AWS. If it didn't exist, you would've had to learn how to create a VPC before you can use some of the services that need VPCs to function.

This default VPC is a handy starting point, especially for beginners, but you can always create custom VPCs to fit specific requirements e.g. strict security measures.

![Image](http://nextwork.ai/intense_magenta_peaceful_coriander/uploads/aws-networks-vpc_2facf927)

### Defining IPv4 CIDR blocks

---

## Subnets

### What I did in this step

In this step, I will create subnets to manage the ip more efficiently. At its core, subnetting exists to solve one problem: taking one large network and splitting it into smaller, more manageable, more controlled pieces.

### Creating and configuring subnets

If your VPC is a city, subnets are like different neighborhoods inside your city. You use subnets to group resources with similar access rules and restrictions. Some subnets might be public areas that all resources can access (public subnets) while others are private areas with limited access (private subnets).

A VPC can have as many public and private subnets as you need, but subnets in the same VPC cannot have overlapping IP address CIDR blocks! This means each subnet must have a unique range of IP addresses.If your VPC is a city, subnets are like different neighborhoods inside your city. You use subnets to group resources with similar access rules and restrictions. Some subnets might be public areas that all resources can access (public subnets) while others are private areas with limited access (private subnets).

A VPC can have as many public and private subnets as you need, but subnets in the same VPC cannot have overlapping IP address CIDR blocks! This means each subnet must ha

### Public vs private subnets

The difference between a public and private subnet is whether it has a path to communicate with the internet. A subnet is private by default, it has no way to reach outside the VPC. To make a subnet public, two things are needed: first, an Internet Gateway (IGW) must be attached to the VPC (this is done once, at the VPC level, not per-subnet). Second, the subnet's route table must include a route sending internet-bound traffic (0.0.0.0/0) to that IGW. Only subnets whose route table points to the IGW are considered public, other subnets in the same VPC can remain private even after the IGW is attached.

![Image](http://nextwork.ai/intense_magenta_peaceful_coriander/uploads/aws-networks-vpc_157c4219)

### Auto-assigning public IPv4 addresses

---

## Internet gateways

### What I did in this step

Right now, nobody can communicate with my vpc as their is no way for someone to find it. It like an house with no road toward it, with no signboards. 
In this step I will attach Internet Gateway (IGW) to my VPC with also router tables, so that anyone on internet can access my public resources inside my VPC.


### Setting up internet gateways

An internet gateway connects your city (VPC) and the outside world (internet).

Internet gateways are key to making applications available on the internet. By attaching an internet gateway, your instances can access the internet and be accessible to external users.

![Image](http://nextwork.ai/intense_magenta_peaceful_coriander/uploads/aws-networks-vpc_4ae90410)

---

## Using the AWS CLI

### What I'm doing in this extension

In this project extension, this process was a little slow and tedious, and suppose you have to create mulltiple VPC, different Availaiblity Zones, multiple subnettings, all manually then it can become a very long, repetitive task. But, dont worry we can fast this thing. By using Amazon CloudShell, a terminal where we can perform all the tasks that we did visually only by writting some commands and thats it! And we can also automate the these steps, by writting it in a script file, and will only need to run that file just.

In this mission, I will do the same exact steps using Amazon CloudShell.

### Exploring CloudShell and CLI

What is CloudShell?
AWS CloudShell is shell in your AWS Management Console, which means it's a space for you to run code. The awesome thing about AWS CloudShell is that it already has AWS CLI pre-installed.


What is CLI?
AWS CLI (Command Line Interface) is a software that lets you create, delete and update AWS resources with commands instead of clicking through your console.
You usually have to install AWS CLI into your computer to use it, but in our case, CloudShell already has CLI installed for us

### Debugging my setup

![Image](http://nextwork.ai/intense_magenta_peaceful_coriander/uploads/aws-networks-vpc_9b2465411)

### Comparing CloudShell vs AWS Console

Setting up resources in CloudShell make things very fast and easy, and one can also automate the entire process. 

At the end also make sure to delte the resources created, as if not delted it can cost money. 

---

---
