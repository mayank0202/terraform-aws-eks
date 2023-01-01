# terraform-aws-eks
Terraform module to create an Elastic Kubernetes (EKS) cluster and associated resources

- [EKS Reference Architecture](https://github.com/clowdhaus/eks-reference-architecture)

## Available Features

- AWS EKS Cluster Addons
- AWS EKS Identity Provider Configuration
- [AWS EKS on Outposts support](https://aws.amazon.com/blogs/aws/deploy-your-amazon-eks-clusters-locally-on-aws-outposts/)
- All [node types](https://docs.aws.amazon.com/eks/latest/userguide/eks-compute.html) are supported:
  - [EKS Managed Node Group](https://docs.aws.amazon.com/eks/latest/userguide/managed-node-groups.html)
  - [Self Managed Node Group](https://docs.aws.amazon.com/eks/latest/userguide/worker.html)
  - [Fargate Profile](https://docs.aws.amazon.com/eks/latest/userguide/fargate.html)
- Support for creating Karpenter related AWS infrastructure resources (e.g. IAM roles, SQS queue, EventBridge rules, etc.)
- Support for custom AMI, custom launch template, and custom user data including custom user data template
- Support for Amazon Linux 2 EKS Optimized AMI and Bottlerocket nodes
  - Windows based node support is limited to a default user data template that is provided due to the lack of Windows support and manual steps required to provision Windows based EKS nodes
- Support for module created security group, bring your own security groups, as well as adding additional security group rules to the module created security group(s)
- Support for creating node groups/profiles separate from the cluster through the use of sub-modules (same as what is used by root module)
- Support for node group/profile "default" settings - useful for when creating multiple node groups/Fargate profiles where you want to set a common set of configurations once, and then individually control only select features on certain node groups/profiles
