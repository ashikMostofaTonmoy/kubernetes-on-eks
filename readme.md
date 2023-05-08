# Kubernetes On AWS (EKS)

## prepare cli and kubectl

To create cluster in aws with `cli`.

```sh
eksctl create cluster --name inneed-cluster --version 1.26 --region ap-south-1 --nodegroup-name linux-nodes --node-type t2.small --nodes 2
```

If you want to connect to an existing cluster.

1. Install `aws cli`
2. Configure `aws cli` using. you'll need `access key`

```sh
aws configure
```

4. Check the current identity to verify that you’re using the correct credentials that have permissions for the Amazon EKS cluster:

```sh
aws sts get-caller-identity
```

5. Create / update the kubeconfig entry for your cluster

```sh
aws eks --region <region-code> update-kubeconfig --name <cluster_name>

aws eks --region ap-south-1 update-kubeconfig --name dev-cluster
```


