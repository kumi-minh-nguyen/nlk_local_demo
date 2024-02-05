# Installation NLB with NGINX+, Ansible and Vagrant

## Preparation

- You may edit the below file to match with your configuration:

  - Update `K8S1IP` and `K8S2IP` in playbook and inventory file (playbook.yml && hosts)

  - Modify the network range in Vagrant file to match with your network if you use vagrant as well.

  - Update image of cafe deployment under nlk/cluster/cafe-demo/cafe.yaml

    - You can rebuild the image for tea and coffee using Dockerfile under `nlk/docker`

    - Mac M1 (ARM): `ducthanh1989/nginx-tea-arm:latest`

    - Others: `nginxinc/ingress-demo`

  - Update image of nlk deployment under nlk/cluster/nlk/deployment.yaml

    - You can rebuild the image for nlk follow the reference `https://github.com/nginxinc/nginx-loadbalancer-kubernetes`

    - Mac M1 (ARM): `ducthanh1989/nginx-loadbalancer-k8s-arm`

    - Others: `ghcr.io/nginxinc/nginx-loadbalancer-kubernetes:latest`

## Provisioning

- Bring up the VM by command below:

`vagrant up`

- During the VM provisioning, ansible will trigger the playbook for the host.

- In case you want to run the playbook manually

`ansible-playbook playbook.yaml -i hosts`

## Verify

- You should be able to access access the below url once vm up:

  - `ssh -i id_rsa_lab vagrant@< K8S1IP >`

  - Verify all k8s pods running

- Access prometheus:

  - `http://<K8S1IP>:9090`

- Access grafana:

  - `http://<K8S1IP>:3000`  with credential: admin/admin
