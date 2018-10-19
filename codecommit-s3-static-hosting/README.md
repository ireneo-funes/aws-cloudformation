# Goal

This directory contains a CloudFormation template for static website hosting and its management. Suppose that your website is `example.com`. This template builds these AWS resources.

- S3 bucket for `www.example.com` containing static files
- S3 bucket for `example.com` redirecting visitors to `www.example.com`
- CodeCommit repository containing static files for `www.example.com` and CloudFormation template.

## Note

- All the AWS resource will have the same name as stack name.
- CodeCommit repository needs a [trigger](https://docs.aws.amazon.com/codecommit/latest/userguide/how-to-notify-lambda.html) and [SNS](https://aws.amazon.com/sns/) as arguments.

## Usage

This project provides a [Makefile](https://en.wikipedia.org/wiki/Makefile) and [CloudFormation](https://aws.amazon.com/cloudformation/) template.
