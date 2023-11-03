# LAB 2: transit gateway centralised inspection use-case

## Deploy the environment
Inside the cloned repo:
```
cd ./fortigate-cnf-sse-workshop/terraform-tgw
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
Access your Jumpbox
```
ssh -i ./key.pem ubuntu@<jumpbox>
```
You can use this key to access all the other hosts in the labs. Simply copy the key (SCP) and set the correct permissions.

## Deploy FortiGate CNF
- Install / verify cross account setup
- Deploy FortiGate CNF and GWLB endpoints
- Update the "variables.tf" using GWLBe name (not the ID)
- Re-apply Terraform with **a valid FortiFlex token.** This FortiFlex token will activate license of FortiAnalyzer-VM.
- Test connectivity

## Create a policy set
- Test the routing

## Clean-up
See [Home](./readme.md)
