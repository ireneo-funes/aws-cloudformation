# Goal

This directory contains a [CloudFormation](https://aws.amazon.com/cloudformation/) template making [Amazon Cognito](https://aws.amazon.com/cognito/) backend for user authentication and access control.

## How to use

1. Decide the stack name to update it in the Makefile.
2. Decide the app name to update it in the CloudFormation template.
3. Run the makefile to create the cognito stack.

   ```console
   ❯ make
   ```

4. Run the makefile with `delete` option to delete the cognito stack.

   ```console
   ❯ make delete
   ```

## Structure of Cognito User Pool

- Users can sign up themselves via app.
- It takes email address as user name and this is the only field required.
- A verification mail will be sent to the email address.
