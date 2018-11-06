# CloudFormation command
CFN=aws cloudformation
# template file in YAML format
TEMPLATE=cognito-backend.yaml
# set stack name for easy identification
STACK-NAME=(Stack name goes here)

# template option
TMP-OPT=--template-body file://$(TEMPLATE)
# stack name option
STK-OPT=--stack-name $(STACK-NAME)
# add tags for resource managment
TAG-OPT=--tags Key=project,Value=$(STACK-NAME)
# Used only when you created IAM resources with custom names
IAM-OPT=--capabilities CAPABILITY_NAMED_IAM
# User option. Only use for multiple AWS accounts.
USR-OPT=
#USR-OPT=--profile=Alice

all:create

validate:$(TEMPLATE)
	$(CFN) validate-template $(TMP-OPT) $(USR-OPT)

create:$(TEMPLATE)
	$(CFN) create-stack $(STK-OPT) $(TMP-OPT) $(USR-OPT) $(TAG-OPT) $(IAM-OPT)

update:$(TEMPLATE)
	$(CFN) update-stack $(STK-OPT) $(TMP-OPT) $(USR-OPT) $(TAG-OPT) $(IAM-OPT)

describe:$(TEMPLATE)
	$(CFN) describe-stacks $(STK-OPT) $(USR-OPT)

delete:
	$(CFN) delete-stack $(STK-OPT) $(USR-OPT)

clean:
	rm -f *~
