# kubile
Kubile is an Ansible playbook that sets up instances of your choosing with Kubernetes. 

It's a simple Ansible setup that automatically configures docker and k8s on the instances (masters and workers) you specify under `/inventories/staging/hosts`.
The playbooks will also initialize the cluster and join the worker nodes for you.

**NOTES**:
- make sure to change the `remote_user` fields to your actual user name
- I don't use root unless I absolutely have to, so I suggest making a user with set permissions. I escalate Ansible permission when needed
- you will notice the k8s version is 15. That's because the latest version was causing so many issues with swap and the docker daemon and I needed to write this quick for my work. Luckily, v15 fit our needs
- `ansible.cfg` has `host_key_checking = False`, which is ill-advised but I had complete control over the enrivornment and the hosts and I didn't want Ansible to keep prompting me for fingerprint approval (killed the whole automation vibe for me), so I turned it off. Comment it out if you want it to check
- the dir structure you are seeing is a brilliant ansible generator tool I use to automatically set up an Ansible dir structure in line with Ansible's recommendation. Source: https://github.com/kkirsche/ansible-generator
