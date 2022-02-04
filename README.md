# camunda-cloud-helm

The camunda-cloud helm mono-repo, contains and host all camunda-cloud related helm charts.

The charts can be accessed by adding the following HELM repo to your HELM setup:

```sh
helm repo add camunda-cloud https://helm.camunda.io
helm repo update
```

The charts are represented in the following image:
![HELM CHARTS](imgs/HelmChartImage.png)

What is inside the helm repo check the [index.yaml](https://helm.camunda.io/index.yaml) or the [github repository](https://github.com/camunda-community-hub/camunda-cloud-helm).

Follow [the instructions in the Zeebe docs](https://docs.zeebe.io/kubernetes/installing-helm.html) to install Zeebe to a K8s cluster using these charts.

## Installing Charts

You can install the Helm Chart by running:
```
helm install <YOUR HELM RELEASE NAME> camunda-cloud/ccsm-helm
```

This command will install all Camunda Cloud Self Managed Components, that are provided by the `ccsm-helm` chart.

## Uninstalling Charts

You can remove these charts by running:

```
helm uninstall <YOUR HELM RELEASE NAME>
```

> Notice that all the services and pods will be deleted, but not the Persistence Volume Claims which are used to hold the storage for the data generated by the cluster and ElasticSearch. In order to free up the storage you need to manually delete all the Persistent Volume Claims. 

You can do this by running:

```
kubectl get pvc
```

Then delete the ones that you don't want to keep:

```
kubectl delete pvc <PVC ids here>
```

Or delete the related kubernetes namespace, which contains the resources.

## Issues

Please create [new issues](https://github.com/camunda-community-hub/camunda-cloud-helm) if you find problems with these charts. This repository is hosted using GitHub Pages and the source code repository can be found here: [https://github.com/camunda-community-hub/camunda-cloud-helm](https://github.com/camunda-community-hub/camunda-cloud-helm)
