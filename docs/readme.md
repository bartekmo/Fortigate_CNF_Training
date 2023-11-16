## Fortigate CNF lab

## 1. Verify access

[Lab Access Credentials](https://fortinet.egnyte.com/dl/dgdmCdeeOO)

Password: Z4szWxfR

### 1.1 AWS Console login
```
account_id / studentxpert / <password will be shared during session>

```

[AWS Console Login](https://signin.aws.amazon.com/)

### 1.2 FortiCloud / FortigateCNF login
```
student<xx>@kubiosec.tech / <password will be shared during session>
```

[FortiGate CNF Login](https://fortigatecnf.com/admin-portal/authentication/login)

## 2. Prepare the lab environment

### 2.1 Cloud9 AWS environment
Use AWS region `eu-west-1` (Ireland) <br>
Create an AWS Cloud9 instance using AWS Cloud9 service.

### 2.2 Create an AWS access key and secret
Login the AWS console and create an **access key** and **secret** under the IAM user `studentxpert`<br>
Note the access key and secret for later usage.

### 2.3 Subscribe to following AWS Marketplace images

Click "Continue to Subscribe", then accept terms and conditions.

[Ubuntu-Jammy](https://aws.amazon.com/marketplace/pp?sku=47xbqns9xujfkkjt189a13aqe)\
[Ubuntu](https://aws.amazon.com/marketplace/pp/prodview-o5bowpuwmx3ng)\
[FortiAnalyzer](https://aws.amazon.com/marketplace/pp/prodview-6dt7z5twj7t7a?sr=0-1&ref_=beagle&applicationId=AWSMPContessa)

### 2.4 Clone the lab repository to Cloud9 instance 
Clone following repo in `/environment` in your Cloud9 env
```
git clone https://github.com/ozanoguz/fortigate-cnf-sse-workshop.git
```

## 3. Deploy lab environments

### 3.1 LAB-1: Deploy a FortiGate CNF playground for Intra-subnet / Single VPC scenario
See [lab1](./lab1.md)

### 3.2 LAB-2: Deploy a FortiGate CNF playground for Transit Gateway (TGW) use-case
See [lab2](./lab2.md)

## 4. CLEAN-UP 
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
