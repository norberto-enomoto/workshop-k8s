# https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_enable_virtual.html#enable-virt-mfa-for-root

- MFA conta root
- User -> operation-1 -> adicionar Permission: AdministratorAccess (somente para o workshop)
- User -> operation-1 -> MFA e Access Keys
 
# https://docs.aws.amazon.com/pt_br/eks/latest/userguide/what-is-eks.html

# https://docs.aws.amazon.com/pt_br/cli/latest/userguide/getting-started-install.html
- aws configure

# Windows PowerShell
- aws ec2 create-key-pair --key-name eks-key --output text | out-file -encoding ascii -filepath eks-key.pem

# Mac ou Linux
- aws ec2 create-key-pair --key-name eks-key --output text > eks-key.pem

- eksctl create cluster -f 01-eks-cluster.yaml

- mostrar na console o CloudFormation
 

- eksctl utils update-cluster-logging --enable-types audit --approve --cluster eksctl-cluster
- eksctl utils update-cluster-logging --disable-types audit --approve --cluster eksctl-cluster
- eksctl delete cluster -f 01-eks-cluster.yaml

# https://eksctl.io/

# https://docs.aws.amazon.com/pt_br/eks/latest/userguide/sample-deployment.html

