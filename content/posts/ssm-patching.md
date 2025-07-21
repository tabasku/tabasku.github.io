+++
title = 'AWS Systems Manager Patch Manager'
date = 2025-07-21
draft = false
tags = ['aws','patching','ssm']
+++

{{ .TableOfContents }}

# Patching EC2 instances with AWS Systems Manager Patch Manager

Situation: AWS organization with dozen of accounts and random EC2 instances running everywhere. Most of them without any maintenance plan. Throw in N amount of ephemeral instances like ones of EKS and ECS nodes. There you are as an Cloud person and have to figure out how to safely patch EC2 operating systems without distrupting anything in a process. 

This is post about exploring patch automation possibilities in AWS with its own service.


##  AWS Systems Manager

AWS System Manager is collection of services that mostly revolve around uh, managing systems. There is services like Automation which you can use to run and create so called Documents that include steps including run scripts on EC2s or call AWS API's for example. Then there is Inventory which collects information about software installed on your EC2's etc.  There is lot more but I picked those examples because Patch Manager relies on these services (plus many more).

All this needs System Manager Agent to be running on the EC2 and it should be able to communicate with SSM service. For Agent to connect to SSM service:

- Instance profile with [System Manager permissions](https://docs.aws.amazon.com/aws-managed-policy/latest/reference/AmazonSSMManagedInstanceCore.html)
- Either EC2 instance running public subnet (not recommended) or in private subnet with either
    - NAT Gateway
    - (SSM, SSMMessages, EC2Messages Endpoints)[https://docs.aws.amazon.com/general/latest/gr/ssm.html] (interface endpoints cost money btw)

