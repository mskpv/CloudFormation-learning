https://github.com/aws-samples/startup-kit-templates/blob/master/templates/elastic-beanstalk.cfn.yml
AWS COMMAND

aws elasticbeanstalk describe-environments --query "Environments[*].EnvironmentName" --output text --profile dishOnline | xargs

for i in `aws elasticbeanstalk describe-environments --query "Environments[*].EnvironmentName" --output text --profile dishOnline | xargs`
do
echo $i
done

aws elasticbeanstalk describe-environments --environment-names "Environment-name" --region us-east-1 --output json --profile <profile name>

aws elasticbeanstalk describe-configuration-settings \
  --application-name "Application-name" \
  --environment-name "Environment-name" \
  --region us-east-1 \
  --query 'ConfigurationSettings[0].OptionSettings[?Namespace==`aws:elasticbeanstalk:application:environment`].[OptionName,Value]' \
  --output text --profile awsOnline


#############################################################################################################
# List all EC2 instances
aws ec2 describe-instances

# List instances with specific output format
aws ec2 describe-instances --output table

# List running instances only
aws ec2 describe-instances --filters "Name=instance-state-name,Values=running"

# List instances with custom output
aws ec2 describe-instances --query 'Reservations[*].Instances[*].[InstanceId,InstanceType,State.Name,Tags[?Key==`Name`].Value|[0]]' --output table
