### aws-cli

* configure aws-cli with defaults, once you've done that it's not needed to specify --region and --output parameters
```bash
mkdir -p ~/.aws
echo [default] > ~/.aws/config
echo region=us-east >> ~/.aws/config
echo output=text >> ~/.aws/config
```
* get latest Amazon Linux AMIs:
```bash
aws ec2 describe-images --owners amazon --filters \
"Name=name,Values=amzn-ami-hvm-*-x86_64-gp2" --query 'Images[].[CreationDate,Name,ImageId]' | sort -r
```

* get AutoScaling group instance ids list:
```bash
aws autoscaling describe-auto-scaling-groups --auto-scaling-group-names <ASG_NAME> \
--query AutoScalingGroups[].Instances[].InstanceId
```
