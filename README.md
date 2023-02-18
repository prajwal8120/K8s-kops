# AWS-EKS-kops
## kops Cluster creation
### Prequisites

```sh
kops create cluster --name=kubevpro.groophy.in \ 
--state=s3://vprofile-kop-states --zones=us-east-2a,us-east-2b \ 
--node-count=2 --node-size=t3.small --master-size=t3.medium --dns-zone=kubevpro.groophy.in \ 
--node-volume-size=8 --master-volume-size=8
```