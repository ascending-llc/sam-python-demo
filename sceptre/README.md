
## Overview

 This quick-start is to deploy a public API gateway using Sceptre. It deploys a docker container with required dependencies to create API.
 User can create config and templates per region if needed. 

## Parameters
  
  - The default parameters are part of template [config](../quickstart/sceptre/config/dev-private/us-west-2/qs/api.yaml).
  - The example API is public API with IAM authorization and you can update `Resource Policy` to allow access to IAM users 
    as given example of root access of your account in the current template.
  - We are using [example API](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-create-api-from-example.html) 
    `Pet store` exported by AWS and will be deployed to stage in us-west-2 after creating this template successfully. 
    The OpenAPI spec is `petstore-api.yaml` as a parameter `ApiSpecS3Key`
  - The default EndpointProtocol is `https` 


## Install

![Terminal](../../_quickstartContainer/img/terminal.gif)

   - Install `docker` and `docker-compose`
   - Build the container from Service Catalog root folder `../../_quickstartContainer`, run `docker-compose build`
   - From `/APIGateway/quickstart/sceptre` run `docker-compose -e USERNAME=your-username run --rm shell`, per commands in [docker-compose.yaml](../quickstart/sceptre/docker-compose.yaml)
   - Login from bash with `okta-login` and choose `GoDaddy AWS`
   - Start the stack creation with `sceptre launch dev-private/us-west-2/qs` to start cloudformation stack create process.
   - Run `sceptre delete dev-private/us-west-2/qs` to delete the stack.


## Notes
   - You can get `Invoke URL` from `Stages`> expand the deployed stage > `GET`/ `POST` pane in AWS console.
   - For testing IAM auth you can use any client for testing, Postman will need access key and secret key of an IAM user, reference attached.
   - You can enable JWT Authorization through the EnableJwtAuth parameter identified [here](https://github.secureserver.net/appservices/service-catalog-products/tree/master/APIGateway#identity-parameters), reference attached.

 
## Reference

   - Test API with Signature Version 4 using Postman [with AWS IAM auth](https://medium.com/@vdespa/create-aws-signature-with-postman-e1e05f1e99cb)
   - Using [JWT](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-jwt-authorizer.html) for authorization
   - [Controlling access via IAM](https://docs.aws.amazon.com/apigateway/latest/developerguide/permissions.html) for APIGateway