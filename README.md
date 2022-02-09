# Helm Charts

The following Helm Charts are available:

- [wemogy Identity](https://github.com/wemogy/identity/tree/main/env/helm)
- [wemogy Authorization](https://github.com/wemogy/authorization/tree/main/env/helm/authorization)
- [wemogy RealTime](https://github.com/wemogy/realtime/tree/main/env/helm/realtime)

## How to use

Add the repository to your Helm repos.

```bash
helm repo add wemogy https://wemogy.github.io/helm/charts
```

Create an Image Pull Secret in the Namespace you want to deploy to. You can get the credential for your Pull Secret from wemogy.

```bash
kubectl create secret docker-registry wemogy-pull-secret \
  --docker-username=<USERNAME> \
  --docker-password=<PASSWORD> \
  --docker-server wemogycloudacr.azurecr.io
```

Install the Helm Chart.

```bash
helm install <YOUR_RELEASE_NAME> wemogy/<CHART_NAME> \
  --version <VERSION> \
  --values <VALUES> \
  --wait
```
