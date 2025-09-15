AWS COMMAND

aws elasticbeanstalk describe-environments --query "Environments[*].EnvironmentName" --output text --profile dishOnline | xargs
