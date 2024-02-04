# ECS Fargate App

This repository contains a CloudFormation template to deploy a containerized application on AWS ECS Fargate.

## Prerequisites
- AWS CLI installed and configured
- Docker image URL for your application

## Deployment Steps

1. Clone this repository:
   ```bash
   git clone https://github.com/cesdias/ecs-fargate-app.git
   cd ecs-fargate-app
   ```

2. Set the `DOCKER_IMAGE_URL` environment variable:
   ```bash
   export DOCKER_IMAGE_URL="your docker image repository url"
   ```

3. Make sure to review and update parameters and configurations according to your specific requirements.

4. Run the AWS CLI command to deploy CloudFormation stack

   ```bash
   aws cloudformation deploy \
      --template-file template.yaml \
      --stack-name ecs-fargate-app \
         ContainerImage="$DOCKER_IMAGE_URL" \
      --capabilities CAPABILITY_IAM
   ```

5. Wait for the deployment to complete.

6. Access your application using the Load Balancer DNS name provided in the CloudFormation stack outputs.

## Cleanup

To delete the CloudFormation stack, run the following command:

```bash
aws cloudformation delete-stack --stack-name ECSFargateAppStack
```
