# OpenShift-Provisioner
Ansible playbooks for installing OpenShift cluster on OpenStack
## Workflow
![workflow](docs/workflow.png)
1. ansible_host: local. Connect to OSP, Create a instance to serve as bastion node
2. ansible_connection: ssh. host: bastion. Install dependencies on bation node for OCP4 installation  
3. ansible_connection: ssh. host: bastion. Create floating ip, Generate install-config, run openshift-install.  
4. ansible_connection: ssh. host: bastion. Set up external load balancer and dns