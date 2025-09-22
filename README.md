AWS COMMAND

aws elasticbeanstalk describe-environments --query "Environments[*].EnvironmentName" --output text --profile dishOnline | xargs

for i in `aws elasticbeanstalk describe-environments --query "Environments[*].EnvironmentName" --output text --profile dishOnline | xargs`
do
echo $i
done

aws elasticbeanstalk describe-environments --environment-names "Environment-name" --region us-east-1 --output json --profile <profile name>
