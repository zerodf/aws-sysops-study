#### Virtual Private Cloud

The first step in creating cloud deployments is to find a home for our compute resources.  To do that, we'll use Amazon [Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).   

##### Parameterization
At first, I have largely avoided over parameterizing templates.  Why?  Because when I search through examples on the Internet, I find over parameterized and mapped templates are generally harder to read.

##### Cloud Formation
1.  `./vpc/bare-vpc.json` - The most bare bones template possible.
1.  `./vpc/bare-vpc-public.json` - This cloudformation template includes a bare minimum needed to spin up EC2 in a public subnet.  
1.  `./monitoring/bare-vpc-public-ec2.yaml` - The first domain on the [AWS Certified SysOps Administrator - Associate](https://aws.amazon.com/certification/certified-sysops-admin-associate/) exam is 'Monitoring and Reporting'.  Therefore, we will need something to report on.  Adding an [EC2](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-ec2-instance.html) instance or two will help and we'll also want this ability when covering high availability.
    1.  `bare-vpc-public-ec2-cloudwatch.yaml` - A VPC consisting of a single, public subnet with a single EC2 instance with enhanced monitoring enabled.  Enableling enhanced monitoring is trivial in [CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-ec2-instance.html#cfn-ec2-instance-monitoring).  
1.  `./secrets_manager/secrets_manager_full.yaml` - A VPC with a single instance with access to secrets manager.
