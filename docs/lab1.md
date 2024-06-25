# LAB-1: Intra-subnet Single VPC Use Case

## 1.1 Deploy the environment

Install Terraform using bash CLI screen

```
wget https://releases.hashicorp.com/terraform/1.3.5/terraform_1.3.5_linux_amd64.zip
unzip terraform_1.3.5_linux_amd64.zip
sudo mv terraform /usr/local/bin/
```


Inside cloned repo, access the folder below:

```
cd ./fortigate-cnf-sse-workshop/terraform-single-vpc
```

Execute terraform apply to create test environment including FortiAnalyzer-VM and test EC2s.

```
terraform init
terraform apply
```
Extract the private SSH key
```
terraform output -raw private_key >key.pem
chmod 400 key.pem
```
Access to Jumpbox, so we can access test EC2s
```
ssh -i ./key.pem ubuntu@<jumpbox>
```
You can use this key to access all the other hosts in the labs. Simply copy the key (SCP) and set the correct permissions.

## 1.2 Deploy FortiGate CNF

- Install / verify cross account setup </br>
  **Hint:** "us-east1" AWS region should be selected before deploying onboarding Cloudformation script.
- Deploy FortiGate CNF and GWLB endpoint(s)
- Test connectivity
- Update the "variables.tf" using GWLBe name *(not the ID e.g. prod-c3144-s3522-endpoint-subnet-xyz)*
- Re-apply Terraform
- Activate FortiAnalyzer license using FortiFlex token 
- Test connectivity

## 1.3 Things to try
- ex. allow traffic to port 8080 and block 8090
- create a dynamic address group
- checkout the routing
- ...

## 1.4 Clean-up for next lab
- Remove GWLBe name value from TF `variables.tf` and re-apply TF
- Remove GWLB endpoint form FortiGate CNF UI
- Destroy playground
