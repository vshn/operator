## TriggerMesh Operator

This is an Operator to install TriggerMesh
This does not install Knative and Istio

## Pre-requisites

### Access to the Container Images

For now the TriggerMesh container images need a Kubernetes ImagePullSecret to be downloaded. Contact us to get the credentials and then create a secret:

```
kubectl create secret docker-registry triggermesh-json-key \
--docker-server=gcr.io \
--docker-username=_json_key \
--docker-password="$(cat ~/triggermeshy-key.json)" \
--docker-email=any@valid.email
```

### Auth0

TriggerMesh uses [Auth0](https://auth0.com/) for Authentication. You need to create a Auth0 application before using this operator.

## Usage

Create the CRD:

```
kubectl create -f https://raw.githubusercontent.com/triggermesh/operator/master/deploy/crds/app_v1alpha1_triggermesh_crd.yaml
```

Deploy the Operator in your k8s cluster:

```
kubectl create -f deploy/service_account.yaml
kubectl create -f deploy/role.yaml
kubectl create -f deploy/role_binding.yaml
kubectl create -f deploy/operator.yaml
```

### Deploy TriggerMesh

You need to write a custom resource object and apply it. For example:

```
apiVersion: app.triggermesh.io/v1alpha1
kind: TriggerMesh
metadata:
  name: example-triggermesh
spec:
  # Default values copied from <project_dir>/helm-charts/triggermesh/values.yaml
...
```

And apply it with:

```
kubectl apply -f tm.yaml
```

Enjoy TriggerMesh !

## Development

You can build the operator yourself with `operator-sdk`:

```
operator-sdk build gcr.io/triggermesh/operator:0.0.1
docker push gcr.io/triggermesh/operator:0.0.1
```

> Note that our CI builds the operator on every commit, hence `gcr.io/triggermesh/operator:latest` is always the latest revision

## Sponsor

This work is made possible by a partnership between TriggerMesh, Inc and [VSHN, the DevOps Company](https://vshn.ch/), the developers of the Swiss Container Platform [APPUiO](https://www.appuio.ch/)

## Support

This is heavily **Work In Progress** We would love your feedback on this Operator so don't hesitate to let us know what is wrong and how we could improve it, just file an [issue](https://github.com/triggermesh/aktion/issues/new)

## Code of Conduct

This operator is by no means part of [CNCF](https://www.cncf.io/) but we abide by its [code of conduct](https://github.com/cncf/foundation/blob/master/code-of-conduct.md)

