### aws-cli
* get latest Amazon Linux AMIs:
```
aws --output text ec2 describe-images --owners amazon --filters  "Name=name,Values=amzn-ami-hvm-*-x86_64-gp2" --query 'Images[].[CreationDate,Name,ImageId]' | sort -r
```

* get AutoScaling group instance ids list:
```
aws autoscaling --output text describe-auto-scaling-groups --auto-scaling-group-names <ASG_NAME> --query AutoScalingGroups[].Instances[].InstanceId
```
