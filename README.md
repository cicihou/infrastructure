# infrastructure

This CloudFormation template deploys a basic VPC / Network.

Prerequisite

1. Install & Config AWS Cli
2. git clone & cd {repo} folder
3. Config AWS profile
```
export AWS_PROFILE=dev
```

Usage

1. create a stack with default settings
```
aws cloudformation create-stack --stack-name myvpc --template-body file://csye6225-infra.yml
```

2. create a stack with declared parameters
```
aws cloudformation create-stack --stack-name myvpcwithparam --template-body file://csye6225-infra.yml --parameters ParameterKey=AmiID,ParameterValue="ami-0e23821d5c2890f1d" --capabilities CAPABILITY_NAMED_IAM
```

3. update a stack
```
aws cloudformation update-stack --stack-name myvpc --template-body file://csye6225-infra.yml
```

4. delete a stack
```
aws cloudformation delete-stack --stack-name myvpc
```

5. validate a template
```
aws cloudformation validate-template --template-body file://csye6225-infra.yml
```

6. delete a non-empty bucket before delete stack
```
aws s3 rm s3://webapp-6cc2cd00 --recursive
```
