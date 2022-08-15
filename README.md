# IBM Workshop Guide for **ACE on CP4I**

## Overview  

<!--- cSpell:ignore gitorg YAMLs -->

The guide includes an end to end workflow for IBM ACE on Cloud.

To be more specific, the following items are included:

-   ACE installation
-   ACE Dashboard installation
-   ACE Integration Server

### Lab 1 - ACE End to End

1. Modify  multi-tenancy-gitops/0-bootstrap/single-cluster/2-services/kustomization.yaml. Uncomment line 
    - argocd/operators/ibm-ace-operator.yaml

2. Install Dashboard
    - Login to OCP, find the IBM App Connect under Installed Operators within tools. 
    - Click on Create Dashboard. 
    - Accept License. 
    - Storage set to ephemeral
    - Create

3. Download the .bar file
```
https://github.com/filemancp4i/ibmace/blob/main/acedemo.bar
```

4. Open the url for the Dashboard Server. Two options. Same result
    - Go to cpd home page.
    - Go to OCP route page, find the dashboard url.

5. Create integration server
    - Create Server on the Dashboard
    - QuickStart
    - Upload .bar file to ACE Dashboard
    - Next
    - Create

6. Wait until Integration becomes available. 
    - find the url to the integration server
    - integration server url + /transformxmltojson
    - test with Postman
