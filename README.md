# Static Web Hosting Implementation

### Introduction

This project serves as the implementation of goals to grow from basic AWS knowledge to understanding and deploying complex architectures in an automated way.
The main goal is to find out and implement the "right way", not the quick way. We do the quick way first then refactor to the right way before moving on.
Shut down or de-provision as much as we can between learning sessions. Rebuilding often will reinforce concepts anyway.


We use a simple website as an excuse to use all the technologies AWS puts at our fingertips. This guide takes us from the most basic webpage to an extremely cheap scalable web application.

*Stock-Symbol-of-the-Day* - Display a random stock symbol each page load, have a text field and a submit button to add a new symbol to the random symbol list.


#### Account Basics

- [x] Create an IAM user for personal use.
- [x] Set up MFA for the root user, turn off all root user API keys.
- [x] Set up Billing Alerts for anything over a few euros.
- [x] Configure the AWS CLI for our user using API credentials.

- [x] **Checkpoint:** We can use the AWS CLI to interrogate information about our AWS account.

#### Web Hosting Basics

- [x] Deploy an EC2 VM and host a simple static *Stock-Symbol-of-the-Day Coming Soon* web page.
- [x] Take a snapshot of our VM, delete the VM, and deploy a new one from the snapshot. Basically, disk backup + disk restore.

**Checkpoint:** We can view a simple HTML page served from our EC2 instance.

#### Auto Scaling

- [x] Create an AMI from that VM and put it in an autoscaling group, so one VM always exists.
- [x] Put an Elastic Load Balancer in front of that VM and load balance between two Availability Zones (one EC2 in each AZ).

**Checkpoint:** We can view a simple HTML page served from both of our EC2 instances. We can turn one off, and our website is still accessible.


#### External Data

- [x] Create a DynamoDB table and experiment with loading and retrieving data manually, then do the same via a script on a local machine.
- [x] Refactor static page into Stock-Symbol-of-the-Day website (JS, PHP, Python ... ) which reads/updates a list of symbols in the AWS DynamoDB table. (Hint: EC2 Instance Role)

**Checkpoint:** High-Available(HA)/AutoScaled website can now load/save data to a database between users and sessions.
