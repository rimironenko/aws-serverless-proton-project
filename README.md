## AWS Proton

AWS Proton is the first fully managed delivery service for container and serverless applications. Platform engineering teams can use AWS Proton to connect and coordinate all the different tools needed for infrastructure provisioning, code deployments, monitoring, and updates.

## AWS Serverless Project

This repository represents Proton configuration to establish the following simple Serverless architecture:
- Dynamo DB Table
- Lambda handlers
- API Gateway

Lambda handlers are attached to API Gateway (AWS_PROXY integration) and can interact with Dynamo DB.

As Proton entities, resources above are grouped as:
- Proton Environment: Dynamo DB and API Gateway. It is a shared infrastructure which can be created from Proton Environment Template ("environment" folder).
- Proton Service: Lambda handlers. It is handlers created from Proton Service template ("lambda-service" folder) which work inbetween API Gateway and Dynamo DB in a particular environemnt. 

Please read more at AWS documentation at https://docs.aws.amazon.com/proton/index.html

## Build

To create Proton Environment template, create a tar.gz archive with content of "environment" folder:
```
tar -cvzf my-proton-environment-template.tar.gz environment/
```
To create Proton Service template, create a tar.gz archive with content of "lambda-service" folder:
```
tar -cvzf my-lambda-service-template.tar.gz lambda-service/
```
Use both archives to create Proton Environemnt and Services via console or CLI. Read how to create both at https://docs.aws.amazon.com/proton/latest/adminguide/ag-getting-started-console.html and https://docs.aws.amazon.com/proton/latest/userguide/ug-get-started-console.html

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

