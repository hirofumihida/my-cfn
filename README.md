# my-cfn
## command list

01 aws ec2 describe-instances --filter "Name=instance-state-name,Values=running"
02 vim cloudformation-study.json
03 aws cloudformation create-stack --stack-name create-ec2-001 --template-body file://cloudformation-study.json
05 aws ec2 describe-instances --filter "Name=instance-state-name,Values=running" | jq '.Reservations[].Instances[].Tags'
06 aws cloudformation describe-stack-events --stack-name create-ec2-001 | jq '.StackEvents[].ResourceStatus'
07 aws ec2 describe-instances --filter "Name=instance-state-name,Values=running" | jq '.Reservations[].Instances[].NetworkInterfaces[].Association["PublicDnsName"]'
08 ssh -i ~/.ssh/aws-tokyo-default001.pem ec2-user@<public dnsname>
09 vim cloudformation-study.json
10 git status
11 git add .
12 git commit -m "change instance type"
13 git push -u origin master
14 aws cloudformation update-stack --stack-name create-ec2-001 --template-body file://cloudformation-study.json
15 aws cloudformation describe-stack-events --stack-name create-ec2-001 | jq '.StackEvents[].ResourceStatus' | head -3
16 aws cloudformation delete-stack --stack-name create-ec2-001
17 aws cloudformation describe-stack-events --stack-name create-ec2-001 | jq '.StackEvents[].ResourceStatus' | head -3
