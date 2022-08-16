# IBM Workshop Guide for **ACE on CP4I**

## Overview  

<!--- cSpell:ignore gitorg YAMLs -->

The guide includes an end to end workflow for IBM ACE on Cloud.

To be more specific, the following items are included:

-   ACE installation/Upgrade
-   ACE Dashboard installation
-   ACE Integration Server

### Lab 1 - ACE End to End

1. Modify  multi-tenancy-gitops/0-bootstrap/single-cluster/2-services/kustomization.yaml. 
    - Uncomment line argocd/operators/ibm-ace-operator.yaml
2. Modify multi-tenancy-gitops/0-bootstrap/single-cluster/2-services/argocd/operators/ibm-ace-operator.yaml. 
    - channel to v 2.0. (line 27)
    - Wait
3. Wait ArgoCD to sync or go to ArgoCD to force refresh/sync immediately.
    - Wait
4. Install Dashboard
    - Login to OCP, find the IBM App Connect under Installed Operators within tools. 
    - Click on Create Dashboard. 
    - Accept License. 
    - Storage set to ephemeral (or persistent-claim then set class to ibmc-file-gold-gid)
    - Create
    - Wait

5. Download the .bar file
```
https://github.com/filemancp4i/ibmace/blob/main/acedemo.bar
```

6. Open the url for the Dashboard Server. Two options. Same result
    - Go to CPD home page, click on Dashboard url
    - Go to OCP route page, find the dashboard url.

5. Create integration server
    - Create Server on the Dashboard
    - QuickStart
    - Upload .bar file to ACE Dashboard
    - Next
    - Create
    - Wait

6. When Integration becomes available, test
    - Find the url to the integration server from OCP route page
    - Integration server url + /transformxmltojson
    - Test with Postman
