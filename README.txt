
AWS Cloudformation for Sparta

AS Future DevOps Engineers, we are expected to keep up to date with the latest
in technology and cloud services. As such it may be likely that particular services,
such as AWS Cloudformation may appear when working on assignment. This template is
made to create the AWS infrastructure that DevOps students often use when working
on cloud platforms. This repo can be used as reference by anyone including other
DevOps students and Trainers to improve their skills in Infrastructure-as-a-code
projects.

The reason I think that AWS Cloudformation is a worthwhile tool to learn is that
it's existence is specifically to keep AWS infrastructure creation as DRY (Don't Repeat Yourself)
as possible. By having templates on stand-by we can spin up infrastructure on AWS
without having to manually configure networking, which is of great use in the case
of a systems failure by significantly reducing time to restoration.

What's in the template?

For simplicity sake, this template is simply made up of the format version, the Description
and the resources that Cloudformation will create:
- a VPC with Cidr 10.0.0.0/16
- two subnets, public (10.0.1.0/24) and private (10.0.2.0/24)
- an Internet Gateway with association
- a Route Table associated with the public subnet, and route between the subnet and
the Internet Gateway
- Two instances for the App and the Database (currently these only contain basic
 Ubuntu 16.04 virtual machines but will be updated in the future)
- Two security groups with appropriate rules and associated with the instances

How to use

- Download the template from this repo

- When you are in the AWS management console, navigate to "Cloudformation" service

- Find the button for "Create Stack" and click it.

- click on "upload a template" and then "Choose file", find the template you downloaded
and select it

- (optional) click "view in designer", this will show the visual representation of
the infrastructure, click on the checkbox in the top left to validate the template
then click the cloud to upload the template to an AWS S3 bucket, so that it can be
retrieved online if needed.

- click on next and name your stack, click next again until you see "create Stack"
at the bottom

- click "create stack" and the stack will start building all the resources, this
may take a few minutes
