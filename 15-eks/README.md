# https://docs.aws.amazon.com/pt_br/eks/latest/userguide/what-is-eks.html

# https://docs.aws.amazon.com/pt_br/cli/latest/userguide/getting-started-install.html
- aws configure
- aws ec2 create-key-pair --key-name eks-key --key-type rsa --key-format pem --query "KeyMaterial" --output text > eks-key.pem
- eksctl create cluster -f 01-eks-cluster.yaml
- eksctl delete cluster -f 01-eks-cluster.yaml

# https://eksctl.io/

# https://docs.aws.amazon.com/pt_br/eks/latest/userguide/sample-deployment.html

