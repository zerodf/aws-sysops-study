#### Virtual Private Cloud

The first step in creating cloud deployments is to find a home for our compute resources.  To do that, we'll use Amazon [Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).   

##### Parameterization
At first, I have largely avoided over parameterizing templates.  Why?  Because when I search through examples on the Internet, I find over parameterized and mapped templates are generally harder to read.

##### Cloud Formation
1 - `./bare-vpc.json` - The most bare bones template possible.
1 - `./bare-vpc-public.json` - This cloudformation template includes a bare minimum needed to spin up EC2 in a public subnet.  
