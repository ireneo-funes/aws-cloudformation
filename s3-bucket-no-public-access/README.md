# Goal

The following article in the AWS blog explains how to secure Amazon S3 buckets.

[How to Use Bucket Policies and Apply Defense-in-Depth to Help Secure Your Amazon S3 Data](https://aws.amazon.com/blogs/security/how-to-use-bucket-policies-and-apply-defense-in-depth-to-help-secure-your-amazon-s3-data/)

The article is composed of two topics.

1. Preventing your Amazon S3 buckets and objects from allowing public access
2. Securing data on Amazon S3 with defense-in-depth

This directory contains a CloudFormation template that fulfills the first security requirement. This template does not implement the second part.

## How it works

Refer to `Makefile` for detailed explanation.

Change the makefile variable `PARAM-VALUE` as you want because it contains the name of S3 bucket.

### Create CloudFormation stack

```console
aws-cloudformation/s3-bucket-no-public-access
❯ make
```

### Delete CloudFormation stack

```console
aws-cloudformation/s3-bucket-no-public-access
❯ make delete
```
