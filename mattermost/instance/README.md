# Fetch ID(s) for Playbook
```
aws ec2 describe-security-groups --query SecurityGroups[*].[GroupName,GroupId] --output text
aws ec2 describe-subnets --query Subnets[*].[CidrBlock,SubnetId] --output text
aws ec2 describe-key-pairs --query KeyPairs[*].[KeyName] --output text
```

# Execution
```
# launch_centos7 - create an ec2 instance of the latest centos7 AMI
ansible-playbook centos7.yml --extra-vars \
"region=us-east-2 \
key_name=my_aws_key \
sgroup_id=sg-someid \
subnet_id=subnet-someid \
disk_gb=10 \
instance_type=t3a.small \
instance_name=mattermost"
```

# Connect
```
# Assuming DNS has been configured for the public IP.
ssh -i .ssh/my_aws_key centos@mm.chadg.net

# Install ansible/git
sudo yum install ansible git

# Clone the repo (to run the playbook)
git clone https://github.com/chadgeary/conference && cd conference/mattermost/
cat README.md
```
