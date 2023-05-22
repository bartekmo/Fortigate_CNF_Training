## Fortigate CNF lab

## 1. Verify access
### AWS Console
```
studentcnp / StudentCNPxx666
```
### Forticloud / FortigateCNF
```
student20@kubiosec.tech / Stud3ntCNP!
```

## 2. Prepare a LAB environment
### Create an ACCESSKEY ID / SECRET
Login the AWS console and access key and secret under the IAM user `studentcnp`<br>
Note the access key and secret.

### Cloud9 AWS environment
Use region `eu-west-1` (ireland) <br>
Create an AWS Cloud9 instance.

### Subscribe to the ubuntu-jammy
Goto `https://aws.amazon.com/marketplace/pp?sku=47xbqns9xujfkkjt189a13aqe` and subscribe and accept the terms.

## 3. Deploy a fortigatecnf playground for intra-subnet / single vpc
Clone folowing repo
```
git clone https://github.com/40net-cloud/fortigate-cnf-sse-workshop.git
```
Deploy the environment
```
terraform init
terraform apply
```
Extract the private SSH key
```
terraform output -raw private_key >key.pem
chmod 400 key.pem
```
Access your Jumpbox
```
ssh -i ./key.pem ubuntu@<jumpbox>
```
Test connectivity


## 4. Deploy fortigatecnf
### Install / verify cross account setup
xxxx
### Deploy fortigatecnf
xxxx
### Add a LB ??
xxxx
### Test connectivity
xxxx

## 5. Create a policy set
- ex. allow traffic to port 8080 and blcok 8090
- create a dynamic address group
- checkout the routing

## 6. remove the FortigateCNF  / playgroung

## 7. Deploy the terraform in intra-subnet / TGW envirnment

## Cleanup for the next session


