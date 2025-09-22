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
  --output text --profile dishOnline
