# MLFlow on Kubeflow

Works with a service namespace `mlflow-service` in the `kubeflow` namespace
```yaml
# add these annotations to the deployment for the sidecar and install all the manifest
# in this path
...
spec:
  template:
    metadata:
      annotations:
        sidecar.istio.io/userVolume: '[{"name":"lua-libs","configMap":{"name":"lua.lib"}}]'
        sidecar.istio.io/userVolumeMount: '[{"name":"lua-libs","mountPath":"/tmp/lib/lua"}]'
```
