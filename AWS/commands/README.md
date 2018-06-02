### How to setup AWS-CLI?
- Have an AWS account
- Install AWS-Cli bundle
- Type: `aws configure`. Fill it out (TIP: use `aws configure --profile <profile-name>` to create a profile)
### How to create SSH access keys to EC2 instances.
```
	aws ec2 create-key-pair --key-name <key-name> --query 'KeyMaterial' --output text > ~/.ssh/<key-name>.pem
	
	chmod 400 ~/.ssh/<key-name>.pem
	
	aws ec2 describe-key-pairs --key-name <key-name>
```
### How to create a Security Group?
```
aws ec2 create-security-group --group-name <group-name> --description <description>
```
After that you will receive the ID of the security-group <security-group-id>.

### How to add rules to enable traffic on ports 22 and 80
```
aws ec2 authorize-security-group-ingress --group-id <security-group-id> --protocol tcp --port 22 --cidr 0.0.0.0/0 
aws ec2 authorize-security-group-ingress --group-id <security-group-id> --protocol tcp --port 80 --cidr 0.0.0.0/0
```
### How to create IAM roles?
TODO
### How can I get a description of the regions? 
```
aws ec2 describe-regions
```
### How to describe availability-zones in a specific region?
```
aws ec2 describe-availability-zones --region <region-name>
```
