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
wget https://raw.githubusercontent.com/filemancp4i/ibmace/main/demo.bar
```

4. Upload .bar file to ACE Dashboard and create integration server

5. Test with PostMan
