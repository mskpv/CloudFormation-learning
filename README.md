AWS COMMAND

aws elasticbeanstalk describe-environments --query "Environments[*].EnvironmentName" --output text --profile dishOnline | xargs

for i in `aws elasticbeanstalk describe-environments --query "Environments[*].EnvironmentName" --output text --profile dishOnline | xargs`
do
echo $i
done
