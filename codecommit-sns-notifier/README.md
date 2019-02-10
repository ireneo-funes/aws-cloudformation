# Goal

This directory contains a CloudFormation template for CodeCommit notifier:
Once a user pushes a commit to a CodeCommit repository, the commit message is
sent to a [Slack](https://en.wikipedia.org/wiki/Slack_(software)) channel.

![diagrm.png](./diagram.png)

# Structure

## Input

1. `WebHookURL`: URL for Slack webhook

## Output

1. `SNSTopic`: SNS Topic object that can be used for CodeCommit trigger.

## Resources

This template generates these AWS resources:

1. Lambda Role
2. Lambda Function
3. SNS Topic
4. SNS Permission

All the AWS resource will have the same name as stack name.

# Usage

This project provides a Makefile and CloudFormation template.
