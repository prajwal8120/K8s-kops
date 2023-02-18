# K8s-kops
## kops Cluster creation
### Prequisites

1. Create a Domain for Kubernetes DNS records.
1. Create a linux VM and Setup.
   - awscli, ssh keys, kubectl, kops
1. Login to AWS Account and Setup.
   - S3 Bucket, IAM User for AWSCLI, Route53 Hosted Zone

## Installations 

1. ### _Install AWS ClI on VM_
   [source:AWS_CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) (_Refer this document for Insatallation_)

2. ### _SSH Key gen_
```sh
ssh-keygen
```
3. ### _kubectl on Linux VM_

   [source:kubectl](https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html) (_Refer this document for Installation_)

```sh
curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.24.10/2023-01-30/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv kubectl /usr/local/bin/
kubectl --version
```
4. ### _kops_creation_

[source:kops](https://kubernetes.io/docs/setup/production-environment/tools/kops/) (_refer this document for kops installation_)








```sh
kops create cluster --name=kubevpro.groophy.in \ 
--state=s3://vprofile-kop-states --zones=us-east-2a,us-east-2b \ 
--node-count=2 --node-size=t3.small --master-size=t3.medium --dns-zone=kubevpro.groophy.in \ 
--node-volume-size=8 --master-volume-size=8
```