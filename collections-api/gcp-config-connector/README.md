### Config Connector Kubernetes manifests

Note: this is currently unused as the cluster does not have enough space

[Config Connector for GCP](https://cloud.google.com/config-connector/docs/how-to/install-upgrade-uninstall) allows
installing Service Account resources as regular Kubernetes manifests. 

See example: https://cloud.google.com/kubernetes-engine/docs/tutorials/authenticating-to-cloud-platform

This allows packaging up Service account credentials alongside the app being deployed.

In the current version of `collections-api`, access to Cloud Firestore through service account is required. This has been done following the above instructions for `GCP Console`.

1. Create Service Account of `datastore.user` in console. Download Key as JSON

2. Create Kubectl secret:

```
kubectl create secret generic firestore-key --from-file=key.json=/Users/david/moneycol-firestore-collections-api.json
```

The manifests included here are effective only if the `config-connector` addon is installed.

