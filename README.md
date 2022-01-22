# AWS CloudFormation

## Overview
Proof of concept to demonstrate how to create AWS resources using CloudFormation service.

AWS CloudFormation is a service that gives developers and businesses an easy way to create a collection of related AWS and third-party resources, and provision and manage them in an orderly and predictable fashion.

When you use AWS CloudFormation, you work with templates and stacks. You create templates to describe your AWS resources and their properties. Whenever you create a stack, CloudFormation provisions the resources that are described in your template.

**Benefits**
- Simplify infrastructure management
- Quickly replicate your infrastructure
- Easily control and track changes to your infrastructure

Reference: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html

## Use case
The dynamodb table will be created (aws resource).

## Requirements
- docker: https://www.docker.com/
- awscli: https://aws.amazon.com/cli/

## Setup
1. Run localstack
`docker run --rm -it -p 4566:4566 -p 4571:4571 localstack/localstack`

## Running
1. Validate template
`aws cloudformation validate-template --endpoint-url http://localhost:4566 --template-body file://cloudformation/stack.yml`

2. Create stack
`aws cloudformation create-stack --endpoint-url http://localhost:4566 --stack-name poc-stack --template-body file://cloudformation/stack.yml`

3. Check created resources
`aws cloudformation list-stack-resources --endpoint-url http://localhost:4566 --stack-name poc-stack`

## Testing
1. Put a new item
`aws dynamodb put-item --endpoint-url http://localhost:4566 --table-name Users --item file://data/item.json --return-consumed-capacity TOTAL --return-item-collection-metrics SIZE`

2. Scan table
`aws dynamodb scan --endpoint-url http://localhost:4566 --table-name Users`

https://docs.aws.amazon.com/cli/latest/reference/dynamodb/index.html