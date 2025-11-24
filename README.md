## AWS Developer Examples

This repository is a collection of small, focused examples for many AWS services. Each folder demonstrates one service (or a related group of services) with minimal code and companion scripts/templates.

Use this repo as a hands‑on reference while preparing for AWS certifications or learning individual services.

## How to Use This Repo

- **Browse by service**: Each top‑level folder is an AWS service (for example `api-gateway`, `lambda`, `s3`, `cloudformation`, `aws-cicd`, `step-functions`).
- **Read the code and scripts**: Most examples are self‑contained and can be deployed with the AWS CLI, CloudFormation, SAM, or the console.
- **Run selectively**: These examples create real AWS resources. Clean up after testing to avoid unexpected costs.

## Prerequisites

- AWS account
- AWS CLI configured (`aws configure`)
- (Optional) Node.js, Python, or other runtimes depending on the example
- Permissions to create and delete resources used in the examples

## Service Folders Overview

- **api-gateway/**  
  - `index.html`: Simple frontend calling an API Gateway endpoint.  
  - `lambda-code.py`: Python Lambda handler used behind API Gateway.  
  - `mapping-template.md`: Velocity Template Language (VTL) examples for request/response mapping.  
  - `stage-variables-commands.sh`: Sample AWS CLI commands using stage variables.  
  - `websocket.sh`: Commands to work with API Gateway WebSocket APIs.

- **aws-cicd/**  
  Examples for CI/CD on AWS:
  - `codebuild/`: Contains `buildspec.yml` showing how to build and test code with AWS CodeBuild.  
  - `codedeploy/`: Sample CodeDeploy application bundle (including `SampleApp_Linux` ZIP and scripts like `install_dependencies`, `start_server`).  
  - `nodejs-v2-blue/`: Example Node.js application and deployment configs for a blue/green style deployment.

- **beanstalk/**  
  Elastic Beanstalk example application and configuration files for simple web app deployment.

- **cdk/**  
  Example AWS CDK project with code and assets (for example images) to define infrastructure as code using higher‑level constructs.

- **cli/**  
  Shell scripts and examples showing how to use the AWS CLI directly to interact with services (create resources, list, update, delete).

- **cloudformation/**  
  Raw CloudFormation templates to practice infrastructure as code:
  - `0-just-ec2.yaml`: Minimal EC2 instance.  
  - `1-ec2-with-sg-eip.yaml`: EC2 instance with security group and Elastic IP.  
  - `2-trigger-failure.yaml`: Template intentionally designed to fail to demonstrate error handling.  
  - `3-drift-security-group.yaml`: Used to demonstrate drift detection with security groups.

- **cloudwatch-logs/**  
  Examples for creating log groups/streams and integrating applications or Lambda functions with CloudWatch Logs.

- **dynamodb/**  
  Example table definition and code snippets for basic CRUD operations with Amazon DynamoDB.

- **ec2-fundamentals/**  
  Simple EC2 examples (instances, security groups, key pairs) to understand the basics of compute on AWS.

- **ecs/**  
  Amazon ECS examples for running containers, including task definitions, service configuration, and supporting assets.

- **kinesis/**  
  Streaming examples using Amazon Kinesis (data streams, producers/consumers, basic CLI commands or code samples).

- **kms/**  
  AWS KMS examples showing how to manage keys and encrypt/decrypt data from applications or the CLI.

- **lambda/**  
  - `asynchronous.sh` / `synchronous.sh`: CLI examples invoking Lambda functions in different modes.  
  - `lambda-cloudformation/`: CloudFormation templates that deploy Lambda functions and permissions.  
  - `with-dependencies/`: Example of packaging a Lambda with third‑party dependencies.

- **route53/**  
  Basic Route 53 examples for hosted zones and DNS records useful for integrating with other services like CloudFront or API Gateway.

- **s3/**  
  Static website hosting and S3 basics:
  - `index.html`, `index-with-fetch.html`, `extra-page.html`: Static website pages, including an example that calls APIs from the browser.  
  - `beach.jpg`, `coffee.jpg`: Sample assets for hosting.  
  - `CORS_CONFIG.json`: Example CORS configuration for cross‑origin requests.

- **s3-advanced/**  
  More advanced S3 patterns (for example event notifications, lifecycle rules, or access patterns).

- **sam/**  
  AWS SAM templates and code for serverless applications (API Gateway + Lambda + DynamoDB, etc.), showing `template.yaml` plus function code.

- **sam-codedeploy/**  
  Examples combining AWS SAM with CodeDeploy for traffic shifting and safe Lambda deployments.

- **serverless-application-repository/**  
  Templates and policies for publishing applications to the AWS Serverless Application Repository.

- **sqs/**  
  Example scripts and code using Amazon SQS queues (send, receive, delete messages, dead‑letter queues).

- **ssm/**  
  Systems Manager (SSM) examples such as running commands via SSM, using parameters, and automations.

- **step-functions/**  
  AWS Step Functions state machine examples:
  - `0-hello-world/`: Minimal state machine with sample input/output.  
  - `1-error-handling/`: State machine focused on retries, catches, and error handling patterns.

## Running Examples

Because each folder is independent, follow the instructions inside the folder (scripts, comments in templates, or any local README). In general:

- **CloudFormation**: `aws cloudformation deploy --template-file TEMPLATE.yaml --stack-name STACK_NAME --capabilities CAPABILITY_NAMED_IAM`
- **SAM**: `sam build` and `sam deploy --guided`
- **Lambda + CLI scripts**: Run the provided `.sh` scripts from a terminal configured with AWS credentials.

Always delete stacks or resources after finishing experiments:

- CloudFormation: `aws cloudformation delete-stack --stack-name STACK_NAME`
- Check for leftover S3 buckets, EIPs, or other billable resources.

## Contributions / Customization

You can clone this repository and adapt any example to your own AWS account, region, or naming conventions. Add your own service folders or extend existing ones as you learn more AWS features.
