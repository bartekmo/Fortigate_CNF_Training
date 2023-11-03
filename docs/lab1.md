# LAB-1: Intra-subnet Single VPC Use Case

## 1.1 Deploy the environment

Inside cloned repo, access the folder below:

```
cd ./fortigate-cnf-sse-workshop/terraform-single-vpc
```

For first deployment of the lab, use a random FortiFlex token ID, because we will do another "terraform apply" in later stage.

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

- Install / verify cross account setup
- Deploy FortiGate CNF and GWLB endpoints
- Test connectivity
- Update the "variables.tf" using GWLBe name (not the ID)
- Re-apply Terraform with **a valid FortiFlex token.** This FortiFlex token will activate license of FortiAnalyzer-VM. 
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
