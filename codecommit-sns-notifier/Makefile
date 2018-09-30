# CloudFormation command
CFN=aws cloudformation
# Used only for multiple AWS profiles
USER-OPT=
#USER-OPT=--profile=Alice --region=eu-west-1 --output=json
# Used only when you created IAM resources with custom names 
IAM-OPT=--capabilities CAPABILITY_NAMED_IAM
# template file in YAML format
TEMPLATE=codecommit-notifier.yaml

# CloudFormation template takes one parameter
# Web Hook URL for Slack
PARAM-KEY=WebHookURL
PARAM-VAL=(Your Slack Web Hook URL goes here)
# stack name is set to param-value
STACK-NAME=$(Your stack name goes here)

all:create

validate:$(TEMPLATE)
	$(CFN) validate-template --template-body file://$(TEMPLATE)

update:$(TEMPLATE)
	$(CFN) update-stack --stack-name $(STACK-NAME) --template-body file://$(TEMPLATE) \
	--parameters ParameterKey=$(PARAM-KEY),ParameterValue=$(PARAM-VAL) $(USER-OPT) $(IAM-OPT)

create:$(TEMPLATE)
	$(CFN) create-stack --stack-name $(STACK-NAME) --template-body file://$(TEMPLATE) \
	--parameters ParameterKey=$(PARAM-KEY),ParameterValue=$(PARAM-VAL) $(USER-OPT) $(IAM-OPT)

delete:
	$(CFN) delete-stack --stack-name $(STACK-NAME) $(USER-OPT)

clean:
	rm -f *~
