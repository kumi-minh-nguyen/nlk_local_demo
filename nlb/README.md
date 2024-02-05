# Installation NLB with NGINX+, Ansible and Vagrant

## Preparation

- You must copy your nginx-repo.crt and nginx-repo.key (Nginx+) here before install.

  - Copy `nginx-repo.crt` and `nginx-repo.key` to nlb folder

- You may edit the below file to match with your configuration:

  - Update `LBIP1` and `LBIP2` in playbook and inventory file (playbook.yml && hosts)

## Provisioning

- Bring up the VM by command below:

`vagrant up`

- During the VM provisioning, ansible will trigger the playbook for the host.

- In case you want to run the playbook manually

`ansible-playbook playbook.yaml -i hosts`

## Verify

- You can access the below url once vm up:

  - `http://<LBIP>:9090`

  - `ssh -i id_rsa_lab vagrant@< LBIP >`
