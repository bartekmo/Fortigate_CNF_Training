## Fortigate CNF lab

## 1. Verify access
### AWS Console login
```
account_id / studentcnp / <see your instructor>
```
### FortiCloud / FortigateCNF access
```
student<xx>@kubiosec.tech / <see your instructor>
```

## 2. Prepare a LAB environment
### Cloud9 AWS environment
Use region `eu-west-1` (ireland) <br>
Create an AWS Cloud9 instance.

### Create an AWS access key and secret
Login the AWS console and create an **access key** and **secret** under the IAM user `studentcnp`<br>
Note the access key and secret.

### Subscribe to AWS Marketplace images
Subsribe and accept terms for marketplace images below.
**Ubuntu-Jammy**
`https://aws.amazon.com/marketplace/pp?sku=47xbqns9xujfkkjt189a13aqe`

**Ubuntu**

'https://aws.amazon.com/marketplace/pp/prodview-o5bowpuwmx3ng'

**FortiAnalyzer**

'https://aws.amazon.com/marketplace/pp/prodview-6dt7z5twj7t7a?sr=0-1&ref_=beagle&applicationId=AWSMPContessa'

### Clone the lab repository to Cloud9 instance 
Clone following repo in `/environment` in your Cloud9 env
```
git clone https://github.com/40net-cloud/fortigate-cnf-sse-workshop.git
```

## LAB 1: Deploy a FortiGate CNF playground for intra-subnet / single VPC scenario
See [lab1](./lab1.md)

## LAB 2: Deploy a FortiGate CNF playground for Transit Gateway (TGW) use-case
See [lab2](./lab2.md)

### CLEAN-UP 
At the end of our session: 
- Remove the endpoints form your TF `variables.tf`
- Re-apply your Terraform
- Destroy your Terraform infrastructure
- Remove all Fortigate CNF instances from the Fortigate CNF UI
- Remove all registered accounts from the Fortigate CNF UI
- Remove Cloudformation `FortinetFWaaSCrossAccountSetup` from AWS region `Oregon`
- Remove the access key and secret (NOT the IAM user !!)
- Remove your Cloud9 instance

Thanks, the next student will thank you as well as the instructor who knows your name ;-)
