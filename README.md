# Introduction

This project provides CloudFormation templates for the following operations:

- [Make a CodeCommit Repository and add an SNS trigger](codecommit-repo/README.md)
- [Make a static website using S3 bucket and CodeCommit repository](codecommit-s3-static-hosting/README.md)
- [Make Slack Notifier for CodeCommit operations](codecommit-sns-notifier/README.md)
- [Make an S3 bucket with no public access](s3-bucket-no-public-access/README.md)
- [Make an S3 bucket for static website hosting](s3-bucket-static-hosting/README.md)

Each directory consists of three files:

- [CloudFormation](https://aws.amazon.com/cloudformation/) template to create, update, and delete a CloudFormation stack
- [Makefile](https://en.wikipedia.org/wiki/Makefile) as a wrapper of a CloudFormation template
- [README](https://en.wikipedia.org/wiki/README) document explaining how to use the CloudFormation template
