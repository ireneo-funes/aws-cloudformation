# CloudFormation command
CFN=aws cloudformation
# template file in YAML format
TEMPLATE=s3-no-public-access.yaml
# set stack name for easy identification
STACK-NAME= # stack-name-goes-here

# template option
TMP-OPT=--template-body file://$(TEMPLATE)
# stack name option
STK-OPT=--stack-name $(STACK-NAME)
# add tags for resource managment
TAG-OPT=--tags Key=project,Value=$(STACK-NAME)
# User option. Only use for multiple AWS accounts.
USR-OPT=
#USR-OPT=--profile=Alice

all:create

validate:$(TEMPLATE)
	$(CFN) validate-template $(TMP-OPT) $(CFN-OPT)

create:$(TEMPLATE)
	$(CFN) create-stack $(STK-OPT) $(TMP-OPT) $(USR-OPT) $(TAG-OPT)

describe:$(TEMPLATE)
	$(CFN) describe-stacks $(STK-OPT) $(USR-OPT)

delete:
	$(CFN) delete-stack $(STK-OPT) $(USR-OPT)

clean:
	rm -f *~
