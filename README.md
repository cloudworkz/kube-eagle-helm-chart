# Kube Eagle Helm Chart

Helm chart for deployment of kube-eagle in Kubernetes.

## Installing helm chart

```bash
helm repo add kube-eagle https://raw.githubusercontent.com/google-cloud-tools/kube-eagle-helm-chart/master
helm repo update
helm install --name=kube-eagle kube-eagle/kube-eagle
```

## Chart configuration

| Parameter          | Description                                                       | Default |
| ------------------ | ----------------------------------------------------------------- | ------- |
| `rbac.create`      | Create and use role based access resources                        | true    |
| `telemetry.host`   | Host for prometheus server to to listen on                        | 0.0.0.0 |
| `telemetry.port`   | Port for prometheus server to listen on                           | 8080    |
| `metricsNamespace` | Prefix of exposed prometheus metrics                              | eagle   |
| `logLevel`         | Logger's log granularity (debug, info, warn, error, fatal, panic) | info    |
