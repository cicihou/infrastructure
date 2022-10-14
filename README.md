# infrastructure

This CloudFormation template deploys a basic VPC / Network.

Prerequisite

1. Install & Config AWS Cli
2. git clone & cd {repo} folder
3. Config AWS profile
```
export AWS_PROFILE=demouser
```

Usage

1. create a stack with default settings
```
aws cloudformation create-stack --stack-name myvpc --template-body file://csye6225-infra.yml
```

2. create a stack with declared parameters
```
aws cloudformation create-stack --stack-name myvpcwithparam --template-body file://csye6225-infra.yml --parameters ParameterKey=VpcCidrBlock,ParameterValue="10.0.0.0/16" ParameterKey=Subnet1CIDR,ParameterValue="10.0.1.0/24" ParameterKey=Subnet2CIDR,ParameterValue="10.0.2.0/24" ParameterKey=Subnet3CIDR,ParameterValue="10.0.3.0/24"
```

3. update a stack
```
aws cloudformation update-stack --stack-name myvpc --template-body file://csye6225-infra.yml
```

4. delete a stack
```
aws cloudformation delete-stack --stack-name myvpc
```
