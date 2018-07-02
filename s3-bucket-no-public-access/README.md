# Goal

This directory contains CloudFormation template for making S3 Bucket with [no public access allowed](https://aws.amazon.com/blogs/security/how-to-use-bucket-policies-and-apply-defense-in-depth-to-help-secure-your-amazon-s3-data/)

Note that it implements the first part of the document which explains `Preventing your Amazon S3 buckets and objects from allowing public access`.

This template does not implement the second part of `Defense-in-Depth`.

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
