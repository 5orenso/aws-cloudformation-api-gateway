# AWS API Gateway done with Cloudformation


### Initial setup

__This should only be run once!__

```bash
$ bash ./bin/create-stack.sh --template base

```


### Update stack

After every merge you can run this command to update the stack.

```bash
$ bash ./bin/create-stack.sh --template base --update-stack
```


### Re-deploy an API Stage after adding more resources

After you update your resources you need to redeploy your stages to make the changes visible.

```bash
$ aws apigateway create-deployment --rest-api-id 'my-api-id' --stage-name 'dev'
```


## Other Resources

* [AWS Lambda boilerplate](https://github.com/5orenso/aws-lambda-boilerplate)
* [Automated AWS Lambda update](https://github.com/5orenso/aws-lambda-autodeploy-lambda)
* [API Gateway setup with Cloudformation](https://github.com/5orenso/aws-cloudformation-api-gateway)
