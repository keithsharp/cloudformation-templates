# Cloudformation Templates
This repository contains some of the [Amazon Web Services](http://aws.amazon.com) [Cloudformation templates](https://aws.amazon.com/cloudformation/) that I use to provision infrastructure on Amazon's cloud service.

## VPC Template
This [template creates a simple VPC](https://github.com/keithsharp/cloudformation-templates/blob/master/vpc-template.yaml) with the following resources:

* An Internet gateway.
* A public subnet containing an autoscaling group that launches a single bastion host.  The subnet allocates a public IP address to the bastion host.  The bastion host is placed in a security group that allows SSH access from anywhere on the Internet.
* A public subnet with a single elastic IP address and a NAT gateway.
* A private subnet with an autoscaling group that launches a single worker host.  This host is placed in security group that only allows SSH access from the security group that contains the bastion host.  Outbound Internet access is through the NAT gateway.

Because the template doesn't create any network ACLs AWS will automatically create a fully permissive ACL and apply it to all three subnets.

The template doesn't have any parameterization so you'll need to edit it to set the correct AMI ID if you're not deploying into eu-west-1 (Ireland), if Amazon have released a new Amazon Linux AMI, or if you want to change the subnet structure.

Keith Sharp, [kms@passback.co.uk](mailto:kms@passback.co.uk)
