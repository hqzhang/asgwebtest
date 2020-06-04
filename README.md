# ASG example
```
Terraform v0.12.25

This example shows how to launch instances using Auto Scaling Groups.

This creates a security group, launch configuration, auto scaling group and an ELB. The user data for launch configuration installs nginx and it listens on port 80.

The example uses latest Ubuntu AMIs.

Make sure you change the list of availability zones that is applicable to your account and region.

To run, configure your AWS provider as described in https://www.terraform.io/docs/providers/aws/index.html
```
Running the example

For planning phase 

```
terraform plan -auto-approve
```

For apply phase

```
terraform apply -auto-approve
Outputs:

asg_name = terraform-example-asg
elb_name = terraform-example-elb-838829863.us-west-2.elb.amazonaws.com

```

For verify phase
Once the stack is created, wait for few minutes and test the stack by launching a browser with ELB url
```
curl https://elb_name
Outputs:
Welcome to nginx!
```

To remove the stack

```
 terraform destroy -auto-approve
```
