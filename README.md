# kubile
Kubile is an Ansible playbook that sets up instances of your choosing with Kubernetes. 

It's a simple Ansible setup that automatically configures docker and k8s on the instances (masters and workers) you specify under `/inventories/staging/hosts`.
The playbooks will also initialize the cluster and join the worker nodes for you.
