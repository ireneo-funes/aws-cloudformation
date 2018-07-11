# CloudFormation command
CFN=aws cloudformation
# CloudFormation option. Only use for multiple AWS accounts.
CFN-OPT=
#CFN-OPT=--profile=Alice --region=eu-west-1 --output=json
# template file in YAML format
TEMPLATE=s3-no-public-access.yaml
# the CFN template takes one parameter
PARAM-KEY=S3BucketName
# this is the valuef of the parameter
PARAM-VALUE=(Your Bucket Name goes here)
# stack name is set to param-value
STACK-NAME=$(PARAM-VALUE)

all:create

validate:$(TEMPLATE)
	$(CFN) validate-template --template-body file://$(TEMPLATE) $(CFN-OPT)

create:$(TEMPLATE)
	$(CFN) create-stack --stack-name $(STACK-NAME) --template-body file://$(TEMPLATE) \
	--parameters ParameterKey=$(PARAM-KEY),ParameterValue=$(PARAM-VALUE) $(CFN-OPT)

delete:
	$(CFN) delete-stack --stack-name $(STACK-NAME) $(CFN-OPT)

clean:
	rm -f *~
