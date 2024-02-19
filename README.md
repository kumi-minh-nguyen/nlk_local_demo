# Installation NLK, NLB, K8s with Ansible and Vagrant

- Current set up is running in MacOS M1/M2, VM provision is Ubuntu 20.x ARM, K8S 1.28, VM Fusion

- Reference documents:

  - `https://github.com/nginxinc/nginx-loadbalancer-kubernetes`

  - `https://github.com/nginxinc/kubernetes-ingress`

- 2 VMs Ubuntu 20.04.6 LTS as Nginx Load Balancer.

- 2 VMs Ubuntu 20.04.6 LTS with K8S install.

- You must have nginx+ license to download nginx+ image

- Go to `nlb` and `cluster`, check out README file in each folder for further instructions to set up 2 NLB and 2 K8s clusters with NLK using the provided Ansible playbooks provided.
