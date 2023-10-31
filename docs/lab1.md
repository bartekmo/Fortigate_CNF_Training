# LAB 1: intra-subnet single vpc use case

## Deploy the environment
Inside cloned repo, access the folder below:
```
cd ./fortigate-cnf-sse-workshop/terraform-single-vpc
```
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

## Deploy FortiGate CNF
- Install / verify cross account setup
- Deploy FortiGate CNF and GWLB endpoints
- Test connectivity
- Update the "variables.tf" using GWLBe name (not the ID) and re-apply Terraform.
- Test connectivity

## Things to try
- ex. allow traffic to port 8080 and block 8090
- create a dynamic address group
- checkout the routing
- ...

## Cleanup for next lab
- Remove GWLBe name value from TF `variables.tf` and re-apply TF
- Remove GWLB endpoint form FortiGate CNF UI
- Destroy playground


