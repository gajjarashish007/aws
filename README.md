# AWS CLI
## EC2
### Describe all instance Name, publicip, status and type. 

```
 aws ec2 describe-instances --profile qa --query "Reservations[*].Instances[*].{PublicIP:PublicIpAddress,Type:InstanceType,Name:Tags[?Key=='Name']|[0].Value,Status:State.Name}"  --filters "Name=instance-state-name,Values=running" "Name=tag:Name,Values='*'"  --output table
```
![image](https://github.com/gajjarashish007/aws/assets/26319607/b0077518-3273-480e-9dfc-ff7700d48845)
### Describe all instance Name, InstanceType, PrivateIP, PublicIP,status,type and VPC ID etc

```
aws ec2 describe-instances 
--query "Reservations[*].Instances[*].{PublicIP:PublicIpAddress,PrivateIP:PrivateIpAddress,Name:Tags[?Key=='Name']|[0].Value,Type:InstanceType,Status:State.Name,VpcId:VpcId}" 
--filters Name=instance-state-name,Values=running 
--output table
```
![image](https://github.com/gajjarashish007/aws/assets/26319607/cc4a9275-e80a-4b55-9306-efae6ed507cc)

### describe all aws region
```
aws ec2 describe-instances --query "Reservations[*].Instances[*].{PublicIP:PublicIpAddress,PrivateIP:PrivateIpAddress,Name:Tags[?Key=='Name']|[0].Value,Type:InstanceType,Status:State.Name,VpcId:VpcId}" --filters Name=instance-state-name,Values=running --output table
```
![image](https://github.com/gajjarashish007/aws/assets/26319607/3191ea74-ecc1-4e93-801e-20c0ab945310)
