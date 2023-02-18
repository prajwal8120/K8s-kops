# AWS-EKS-kops
## kops Cluster creation
### Prequisites

1. Create a Domain for Kubernetes DNS records.
1. Create a linux VM and Setup.
   - kops, kubectl, ssh keys, awscli
1. Login to AWS Account and Setup.
   - S3 Bucket, IAM User for AWSCLI, Route53 Hosted Zone

## Installations 

### _kubectl on Linux VM_

[source:kubectl](https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html) (Refer this document for Insatallation)


```sh
kops create cluster --name=kubevpro.groophy.in \ 
--state=s3://vprofile-kop-states --zones=us-east-2a,us-east-2b \ 
--node-count=2 --node-size=t3.small --master-size=t3.medium --dns-zone=kubevpro.groophy.in \ 
--node-volume-size=8 --master-volume-size=8
```