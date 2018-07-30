# CloudFormation command
CFN=aws cloudformation
# User option. Only use for multiple AWS accounts.
USR-OPT=
#USR-OPT=--profile=Alice 
# template file in YAML format
TEMPLATE=s3-static-hosting.yaml
# the CFN template takes one parameter
PARAM-KEY=S3BucketName
# this is the valuef of the parameter
PARAM-VALUE=(Your Bucket Name goes here)
# stack name is set to param-value
STACK-NAME=$(PARAM-VALUE)

all:create

validate:$(TEMPLATE)
	$(CFN) validate-template --template-body file://$(TEMPLATE) $(USR-OPT)

create:$(TEMPLATE)
	$(CFN) create-stack --stack-name $(STACK-NAME) --template-body file://$(TEMPLATE) \
	--parameters ParameterKey=$(PARAM-KEY),ParameterValue=$(PARAM-VALUE) $(USR-OPT)

describe:$(TEMPLATE)
	$(CFN) describe-stacks --stack-name $(STACK-NAME) $(USR-OPT)

delete:
	$(CFN) delete-stack --stack-name $(STACK-NAME) $(USR-OPT)

clean:
	rm -f *~
