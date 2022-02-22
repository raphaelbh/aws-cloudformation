# AWS CloudFormation

[![Project Status](https://img.shields.io/static/v1?label=project%20status&message=complete&color=success&style=flat-square)](#)

Proof of concept to demonstrate how to create AWS resources using CloudFormation service.

> AWS CloudFormation is a service that gives developers and businesses an easy way to create a collection of related AWS and third-party resources, and provision and manage them in an orderly and predictable fashion.

When you use AWS CloudFormation, you work with templates and stacks. You create templates to describe your AWS resources and their properties. Whenever you create a stack, CloudFormation provisions the resources that are described in your template.

**Benefits**
- Simplify infrastructure management
- Quickly replicate your infrastructure
- Easily control and track changes to your infrastructure

## Requirements

[![docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)

## Installation

```bash
$ docker run --rm -it -p 4566:4566 -p 4571:4571 localstack/localstack
```
    
## Usage

```bash
$ aws cloudformation validate-template --endpoint-url http://localhost:4566 --template-body file://cloudformation/stack.yml
$ aws cloudformation create-stack --endpoint-url http://localhost:4566 --stack-name poc-stack --template-body file://cloudformation/stack.yml
$ aws cloudformation list-stack-resources --endpoint-url http://localhost:4566 --stack-name poc-stack
```

## Tech Stack

[![docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![aws](https://img.shields.io/badge/Amazon_AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)](https://aws.amazon.com/)

## Reference

- https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html

## Feedback

If you have any feedback, please contact me at raphaeldias.ti@gmail.com

[![github](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/raphaelbh)
[![linkedin](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/raphaelbh/)