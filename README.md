# AWS API Gateway done with Cloudformation


### Initial setup

__This should only be run once!__

```bash
$ aws cloudformation create-stack --stack-name dl-api-gw-base --template-body file://./templates/dl-api-gw-base.json  --parameters file://./parameters/dl-api-gw-base.json --capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM

$ aws cloudformation create-stack --stack-name dl-api-gw-foobar --template-body file://./templates/dl-api-gw-foobar.json  --parameters file://./parameters/dl-api-gw-foobar.json --capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM

$ aws cloudformation create-stack --stack-name dl-api-gw-foo --template-body file://./templates/dl-api-gw-foo.json  --parameters file://./parameters/dl-api-gw-foo.json --capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM


```


### Update stack

After every merge you can run this command to update the stack.

```bash
$ aws cloudformation update-stack --stack-name dl-api-gw-base --template-body file://./templates/dl-api-gw-base.json  --parameters file://./parameters/dl-api-gw-base.json --capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM

$ aws cloudformation update-stack --stack-name dl-api-gw-foobar --template-body file://./templates/dl-api-gw-foobar.json  --parameters file://./parameters/dl-api-gw-foobar.json --capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM

$ aws cloudformation update-stack --stack-name dl-api-gw-foo --template-body file://./templates/dl-api-gw-foo.json  --parameters file://./parameters/dl-api-gw-foo.json --capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM

```


### Re-deploy an API Stage

After you update your resources you need to redeploy your stages to make the changes visible.

```bash
$ aws apigateway create-deployment --rest-api-id 'tac6j1feei' --stage-name 'prod'

$ aws apigateway create-deployment --rest-api-id 'tac6j1feei' --stage-name 'prod'
```
