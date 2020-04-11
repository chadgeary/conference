# Fetch ID(s) for Playbook
```
aws ec2 describe-security-groups --query SecurityGroups[*].[GroupName,GroupId] --output text
aws ec2 describe-subnets --query Subnets[*].[CidrBlock,SubnetId] --output text
aws ec2 describe-key-pairs --query KeyPairs[*].[KeyName] --output text
```

# Execution
```
# launch_ubuntu1604 - create an ec2 instance of the latest ubuntu1604 AMI
ansible-playbook launch_ubuntu1604.yml --extra-vars \
"region=us-east-2 \
key_name=my_aws_key \
sgroup_id=sg-someid \
subnet_id=subnet-someid \
disk_gb=30 \
instance_type=t3a.large \
instance_name=bigbluebutton"
```

# Connect
```
# Assuming DNS has been configured for the public IP.
ssh -i .ssh/my_aws_key ubuntu@bbb.chadg.net

# Install ansible/git
sudo apt update && sudo apt install ansible git

# Clone the repo (to run the playbook)
git clone https://github.com/chadgeary/conference && cd conference/bigbluebutton/
cat README.md
```
