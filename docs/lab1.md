## LAB 1

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
