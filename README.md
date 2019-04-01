## TriggerMesh Operator

This is an Operator to install TriggerMesh
This does not install Knative and Istio

### Access to the Container Images

For now the TriggerMesh container images need a Kubernetes ImagePullSecret to be downloaded. Contact us to get the credentials and then create a secret:

```
kubectl create secret docker-registry triggermesh-json-key \
--docker-server=gcr.io \
--docker-username=_json_key \
--docker-password="$(cat ~/triggermeshy-key.json)" \
--docker-email=any@valid.email
```

### Build

```
operator-sdk build gcr.io/triggermesh/operator:0.0.1
docker push gcr.io/triggermesh/operator:0.0.1
```

## Sponsor

This work is made possible by a partnership between TriggerMesh, Inc and [VSHN, the DevOps Company](https://vshn.ch/), the developers of the Swiss Container Platform [APPUiO](https://www.appuio.ch/)

## Support

This is heavily **Work In Progress** We would love your feedback on this Operator so don't hesitate to let us know what is wrong and how we could improve it, just file an [issue](https://github.com/triggermesh/aktion/issues/new)

## Code of Conduct

This operator is by no means part of [CNCF](https://www.cncf.io/) but we abide by its [code of conduct](https://github.com/cncf/foundation/blob/master/code-of-conduct.md)

