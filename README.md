## 🚀&nbsp; List of AWS CLI Command

The AWS CLI is a handy and extremely powerful tool for managing resources on AWS from a local shell. In this post we will walk through the process of setting up the AWS CLI on a Linux Machine ( I use the Linux Subsystem on Windows which gives me an Ubuntu bash). Then we begin using the AWS CLI to perform administrative tasks on the environment.

### Download AWS CLI
```shell
sudo apt-get install awscli
```
### Configure your AWS
```shell
aws configure
```
Here you need to specify:
- Your access Key ID (refer the the csv file you downloaded)
- Your Secret Access Key (refer the the csv file you downloaded)
- Your preferred default region code (for example, us-east-1). Choose a region that is closest to you for now.
- Default output format. Choose json


### AWS S3 Command

List buckets:
```shell
aws s3 ls
```

List buckets content:
```shell
aws s3 ls s3://<bucket>
```

Make bucket:
```shell
aws s3 mb s3://<bucket>
```

Remove empty bucket:
```shell
aws s3 rb s3://<bucket>
```

Sync objects:
```shell
aws s3 sync <local> s3://bucket
```

Copy to bucket:
```shell
aws s3 cp <object> s3://bucket
```

Copy from bucket:
```shell
aws s3 cp s3://<bucket>/<object> <destination>
```

Move object:
```shell
aws s3 mv s3://<bucket>/<object> <destination> 
```

Remove object:
```shell
aws s3 rm s3://<bucket>/<object>
```

Sync object between bucket/directories:
```shell
aws s3 sync <local> s3://bucket
```


### AWS EC2 Command

Create instance:
```shell
aws ec2 run-instances --image-id<ID> --instance-type<TYPE> --key-name<KEY> --security-groups<SG> --count<#>
```

Start instance:
```shell
aws ec2 start-instances --instance-ids<ID>
```

Stop instance:
```shell
aws ec2 stop-instances --instance-ids<ID>
```

Reboot instance:
```shell
aws ec2 reboot-instances --instance-ids<ID>
```

Terminate instance:
```shell
aws ec2 terminate-instances --instance-ids<ID>
```

Create image from Instance:
```shell
aws ec2 create-image --instance-id<ID> --name<NAME> --description<DESCRIPTION>
```

View image information:
```shell
aws ec2 describe-images --image-ids<ID>
```

Attach Volume to Instance:
```shell
aws ec2 attach-volume --volume-id<VID> --instance-id<IID> --device<DEVICE>
```

Detach Volume from instance:
```shell
aws ec2 detach-volume --volume-id<ID>
```

