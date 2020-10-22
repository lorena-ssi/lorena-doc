# Installation

## Connect to the Kubernetes cluster using kubectl

```bash
kubectl config use-context OUR_KUBERNETES_CONTEXT;
```

## Configure the Lorena Helm repository 

```bash

# Add the Lorena Helm repository
$ helm repo add lorena https://lorena-helm-charts.storage.googleapis.com

# Ensure that the repo exists
$ helm repo list
lorena-helm-charts    https://lorena-helm-charts.storage.googleapis.com

# Update the repo to get the last Charts versions
$ helm repo update

```

# Run the Idspace

## Create your Helm values file

Copy the output of the command below into a values YAML file

```bash

$ helm show values lorena/lorena-idspace > values.yaml

```

Output example:

```
# Default values for lorena Chart.
# This is a YAML-formatted file.
# Declaring variables to be passed into Lorena templates.

Namespace: idspace-demo

StatefulSet:
  Labels: 
    project: Lorena
    tech: Idspace
  Image:
    Repository: eu.gcr.io/caelumlabs-hub01/nodejs/lorena-idspace
    # Overrides the image tag whose default is the chart appVersion.
    Tag: test_latest
    PullPolicy: IfNotPresent
    # A Kubernetes persistent storage class is required and 
    # should be already deployed on your cluster
    # Recommendations for the Storage Class definition:
    # enable allowVolumeExpansion
    # use SSD storage
  VolumeClaimTemplates:
    StorageClassName: gke-ssd
    ResourcesRequestStorage: 4Gi

#  Replicas: 1
#  updateStrategy: "RollingUpdate"
#  serviceName: is the Release Name

################################
# echo -n "Put the string to encrypt" |base64 -w 0
# Secrets:
#   IdspacePassword: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
#   LorenaNetwork: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
#   LorenaDomain: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
#   SubstrateSeed: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX 
#   SengridApiKey: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

```

## Customize your node ensuring these values are setted into values file:

- **StatefulSet:Image:Repository**
  - Description: The Docker Registry URI and Docker Image Name that provides the Livinglab Docker image to deploy. This one is managed and maintained by CaelumLabs 
  - Value to set: `eu.gcr.io/caelumlabs-hub01/substrate-apps/substrate-v2-livinglab`

- **StatefulSet:Image:Tag**
  - Description: The Docker image version to deploy  
  - Value to set: `latest`

- **StatefulSet:VolumeClaimTemplates:StorageClassName**
  - Description: The Storage Provider Class for your Kubernetes cluster 
  - Value to set: `your Kubernetes Storage Class Name`

- **StatefulSet:VolumeClaimTemplates:ResourcesRequestStorage**
  - Description: The Substrate data disk size for your node  
  - Value to set: `your disk size`

## Deploy the Idspace node

*Note: Please, change these string on the commands below by your custom value*

- yourHelmDeploymentName
- namespaceWhereReleaseInfoIsSavedAndNodeDeployed
- yourValuesFile

### First of all with `dry-run` mode to validate the Helm Chart and the values you are setted

```bash
# Dry run mode
helm upgrade yourHelmDeploymentName lorena/lorena-idspace --install --wait --atomic --namespace namespaceWhereReleaseInfoIsSavedAndNodeDeployed --create-namespace -f yourValuesFile --dry-run
```

### Deploy
```bash
# Deploy the node
helm upgrade yourHelmDeploymentName lorena/lorena-idspace --install --wait --atomic --namespace namespaceWhereReleaseInfoIsSavedAndNodeDeployed --create-namespace -f yourValuesFile 
```

# Upgrade the Idspace node version (helm chart version):

## Update the Lorena Helm repository and get the last version available

```bash

# Update the repo to get the last Charts versions
$ helm repo update

```

## Get the last version available from the Lorena Repository

```bash

# Show the last version availble
$ helm show chart lorena/lorena-idspace
apiVersion: v2
appVersion: 1.22.2-beta
description: A Lorena Hub Helm chart for Kubernetes
name: lorena-idspace
type: application
version: 0.1.1

```

## Upgrade the node

*Note: Please, change these string on the commands below by your custom value*

- yourHelmDeploymentName
- namespaceWhereReleaseInfoIsSavedAndNodeDeployed
- yourValuesFile

### First of all with `dry-run` mode to validate the Helm Chart and the values you are setted

```bash
# Dry run mode
helm upgrade yourHelmDeploymentName lorena/lorena-idspace --install --wait --atomic --namespace namespaceWhereReleaseInfoIsSavedAndNodeDeployed --version helmChartVersionToDeploy -f yourValuesFile --dry-run
```

### Deploy
```bash
# Deploy the node
helm upgrade yourHelmDeploymentName lorena/lorena-idspace --install --wait --atomic --namespace namespaceWhereReleaseInfoIsSavedAndNodeDeployed --version helmChartVersionToDeploy -f yourValuesFile
```