# CloudFormation command
CFN=aws cloudformation
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
	$(CFN) validate-template --template-body file://$(TEMPLATE)

create:$(TEMPLATE)
	$(CFN) create-stack --stack-name $(STACK-NAME) --template-body file://$(TEMPLATE) \
	--parameters ParameterKey=$(PARAM-KEY),ParameterValue=$(PARAM-VALUE)

delete:$(TEMPLATE)
	$(CFN) delete-stack --stack-name $(STACK-NAME)

clean:
	rm -f *~
