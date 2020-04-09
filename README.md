# API Gateway + Lambda REQUEST Authorizer Example

This example shows you how to create an API Gateway API with a Lambda REQUEST Authorizer using SAM.

It also add a Cognito User Pool, a fake api key and ui to demonstrate the capability to combine 2 auths: 1. check if the request is from a valid cognito user 2. if it's from a service with an API key

## Running the example


Deploy the example into your account:

```
sam build
sam deploy --guided --stack-name sam-lambda-request-auth
```

Cognito User Pools doesn't currently have CloudFormation support for configuring their Hosted Register/Signin UI. For now we will create these via the AWS CLI:

```bash
npm run configure-cognito-user-pool
```

Open the registration page created and hosted for you by Cognito in your browser. After the page loads, enter a Username and Password and click the Sign Up button.

```bash
npm run open-signup-page

# Alternatively, you can open the login page by running `npm run open-login-page`
```

After clicking Sign Up, you will be redirected to the UI client for your API.


## Additional resources

- https://aws.amazon.com/blogs/compute/introducing-custom-authorizers-in-amazon-api-gateway/
- https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-use-lambda-authorizer.html
