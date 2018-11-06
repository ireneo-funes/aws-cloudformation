# CloudFormation command
CFN=aws cloudformation
# template in YAML format
TEMPLATE=codecommit-notifier.yaml
# # set stack name for easy identification
STACK-NAME=$(Your stack name goes here)
# Web Hook URL for Slack
PARAM-KEY=WebHookURL
PARAM-VAL=(Your Slack Web Hook URL goes here)

# Used only for multiple AWS profiles
USER-OPT=
#USER-OPT=--profile=Alice --region=eu-west-1 --output=json
# Used only when you created IAM resources with custom names 
IAM-OPT=--capabilities CAPABILITY_NAMED_IAM

# template option
TMP-OPT=--template-body file://$(TEMPLATE)
# stack name option
STK-OPT=--stack-name $(STACK-NAME)
# add tags for resource managment
TAG-OPT=--tags Key=project,Value=$(STACK-NAME)
# parameter option
PARAM-OPT=--parameters ParameterKey=$(PARAM-KEY),ParameterValue=$(PARAM-VAL)

all:create

validate:$(TEMPLATE)
	$(CFN) validate-template $(TMP-OPT)

update:$(TEMPLATE)
	$(CFN) update-stack $(STK-OPT) $(TMP-OPT) $(TAG-OPT) $(PARAM-OPT) $(USER-OPT) $(IAM-OPT)

create:$(TEMPLATE)
	$(CFN) create-stack $(STK-OPT) $(TMP-OPT) $(TAG-OPT) $(PARAM-OPT) $(USER-OPT) $(IAM-OPT)

delete:
	$(CFN) delete-stack $(STK-OPT) $(USER-OPT)

clean:
	rm -f *~
