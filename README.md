# Simple EC2 Instance CloudFormation Template

This repository contains a basic AWS CloudFormation template that launches an EC2 instance along with associated security groups and an Elastic IP.

## Files

- **simpleEC2Instance.yaml**  
  CloudFormation template that defines:
  - One `AWS::EC2::Instance`
  - One or more security groups (e.g. `SSHSecurityGroup`, `ServerSecurityGroup`)
  - An `AWS::EC2::EIP` associated with the instance

## Prerequisites

- An AWS account
- AWS CLI installed and configured (`aws configure`)
- Appropriate IAM permissions to create EC2 instances, security groups, and Elastic IPs

## Validate the template

```bash
aws cloudformation validate-template \
  --template-body file://simpleEC2Instance.yaml
```

## Deploy the stack

```bash
STACK_NAME=simple-ec2-stack

aws cloudformation create-stack \
  --stack-name $STACK_NAME \
  --template-body file://simpleEC2Instance.yaml \
  --capabilities CAPABILITY_NAMED_IAM
```

Wait until the stack finishes creating:

```bash
aws cloudformation wait stack-create-complete \
  --stack-name $STACK_NAME
```

## Update the stack

If you change the template, deploy the changes with:

```bash
STACK_NAME=simple-ec2-stack

aws cloudformation update-stack \
  --stack-name $STACK_NAME \
  --template-body file://simpleEC2Instance.yaml \
  --capabilities CAPABILITY_NAMED_IAM
```

## Delete the stack

To remove the resources created by this template:

```bash
STACK_NAME=simple-ec2-stack

aws cloudformation delete-stack \
  --stack-name $STACK_NAME
```

This will delete the EC2 instance, security groups, and Elastic IP associated with this stack.
