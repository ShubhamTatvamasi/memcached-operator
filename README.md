# memcached-operator

Initalize operator:
```bash
operator-sdk init \
  --domain shubhamtatvamasi.com \
  --repo github.com/ShubhamTatvamasi/memcached-operator
```

Create API:
```bash
operator-sdk create api \
  --group cache \
  --version v1alpha1 \
  --kind Memcached
```

Generate CRD:
```bash
make generate
```

Generate webhooks:
```bash
make manifests
```

Set the operator image name:
```bash
export IMG=shubhamtatvamasi/memcached-operator:0.0.1
```

Build and push operator docker image:
```bash
make docker-build docker-push IMG=${IMG}
```

Deploy operator:
```bash
make deploy IMG=${IMG}
```

Install Custom Resource:
```bash
kubectl apply -f config/samples/cache_v1alpha1_memcached.yaml
```
