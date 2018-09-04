# AWS API Gateway done with Cloudformation


### Initial setup

__This should only be run once!__

```bash
# Create the base API setup
$ bash ./bin/create-stack.sh --template base

# Create a new resource
$ bash ./bin/create-stack.sh --template proxy
```


### Update stack

After every merge you can run this command to update the stack.

```bash
# Update the base API setup
$ bash ./bin/create-stack.sh --template base --update-stack

# Update the proxy resource
$ bash ./bin/create-stack.sh --template proxy --update-stack
```


### Re-deploy an API Stage after adding more resources

After you update your resources you need to redeploy your stages to make the changes visible.

```bash
# Redeploy your dev stage
$ aws apigateway create-deployment --rest-api-id 'my-api-id' --stage-name 'dev'

# Redeploy your prod stage
$ aws apigateway create-deployment --rest-api-id 'my-api-id' --stage-name 'prod'
```


## Other Resources

* [AWS Lambda boilerplate](https://github.com/5orenso/aws-lambda-boilerplate)
* [Automated AWS Lambda update](https://github.com/5orenso/aws-lambda-autodeploy-lambda)
* [AWS API Gateway setup with Cloudformation](https://github.com/5orenso/aws-cloudformation-api-gateway)
* [AWS IoT setup with Cloudformation](https://github.com/5orenso/aws-cloudformation-iot)
