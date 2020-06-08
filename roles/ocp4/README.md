Install CNV on PSI
=========

Requirements
------------
Before executing ths ansible role, you need to follow [this guide](https://docs.engineering.redhat.com/display/HSSP/PnT+Resource+Request+Workflow+including+PSI) to request a Red Hat PSI project. To fit one ocp4 cluster in your osp project, `tier 6` is enough. 

Obtain your [pull secret](https://cloud.redhat.com/openshift/install/pull-secret) and put it in this repo's root folder with filename `.ocp4_pull_secret`. [vars file](https://github.com/mali-chainzee/OpenShift-Provisioner/tree/master/roles/ocp4/vars) will look for this when generating install-config

Usage
------------
Ansible `tags` are used for different stages of cluster intallation. 
`ansible-playbook playbooks/create_cluster.yml --tags=<options>` 

`--tags=install` creates a cluster with cnv<br/>
`--tags=config -e cluster_name=<cluster_name>` does post install works on existing cluster<br/>
`--tags=cnv -e cluster_name=<cluster_name>` installs cnv on your existing ocp4 cluster<br/>
`--tags=destroy` destroys cluster and recycles openstack resources<br/>

Role Variables
--------------
Note: Modify ocp4_version if you want to install a different cluster version. New version won't conflict with previous installed versions of ocp4 cluster, but  
```
base_domain: #defalult example.com
cluster_name: #default <kerboros username>
ocp4_version: #default stable
ocp4_full_version: #default stable
```

