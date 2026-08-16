## AWS Loadbalancer Controller

# Prerequisites
1. Create the `AmazonEKSLoadBalancerControllerRole` and then create the policy to associate it with using `aws-loadbalancer-controller-role.json`
2. Create the `aws-load-balancer-controller` service account in the `kube-system namespace` and associate it with the arn of the role you created in Step 1
3. If using IRSA schema please makes sure that the trust policy permits the service account to assume the role, if not loadbalancer ensuring and target registration will fail

# Install Steps
1. Execute helm install
`helm install aws-load-balancer-controller eks/aws-load-balancer-controller \
  -n kube-system \
  --set clusterName=my-cluster \
  --set serviceAccount.create=false \
  --set serviceAccount.name=aws-load-balancer-controller`
2. Proceed to install `envoyproxy`