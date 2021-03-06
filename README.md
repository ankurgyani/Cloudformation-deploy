# Cloudformation-deploy
Automate infrastructure provisioing on AWS with cloudformation template deployed through Jenkins. 


## Infrastructure 
I have used a simple flask webapp to deploy on the AWS console using ECS via Fargate launch type. The deployment is done through a Cloudformation template which gets deployed using Jenkins(through the Jenkinsfile). The application can be accessed by navigating to the Public IP of the Task(``my-stack``) in the ECS service console and running it on port 5000 (```eg-http://3.85.235.254:5000/```) . The IAM roles required to complete this task were created manually in the aws console. I have used the default VPC and default security groups.

## Application 
The application is a simple flask web-app which is rendering a message on the web page. The application is dockerized and the image is pushed to my dockerhub repository which is public https://hub.docker.com/r/gyania/flaskdemo. 

## Deployment
The CloudFormation template gets deployed using Jenkins . Jenkins is installed on the EC2 instance(named Jenkins) and can be accessed by using the public-ip of the instance with the port ( http://52.55.94.175:8080/job/DeployCloudformation/) . Jenkins has 2 jobs created in it , One for deployment(`DeployCloudformation`) and one for deleting the stack(``deleteStack``) . The repo consists of 2 Jenkinsfile one for each job of Deploying and Deleting the infrastructure on AWS.
