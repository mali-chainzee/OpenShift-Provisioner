# CNV provisioner on PSI
This repo contains playbooks for deploying CNV environment on PNT Shared Insfrastructure, which is managed with OpenStack. 

## Workflow
![workflow](docs/workflow.png)
1. Create a instance to serve as bastion node. `openshift-install` will run here
2. ansible_connection: ssh. host: bastion. Install dependencies on bation node for OCP4 installation  
3. ansible_connection: ssh. host: bastion. Create floating ip, Generate install-config, run openshift-install.  

## Usage
For instructions on cluser creation, please refer to [roles/ocp4](https://github.com/mali-chainzee/OpenShift-Provisioner/tree/master/roles/ocp4)  