# Kube Eagle Helm Chart

Helm chart for deployment of kube-eagle in Kubernetes.

## Installing helm chart

```bash
helm repo add kube-eagle https://raw.githubusercontent.com/google-cloud-tools/kube-eagle-helm-chart/master
helm repo update
helm install --name=kube-eagle kube-eagle/kube-eagle
```

## Chart configuration

| Parameter                         | Description                                                        | Default             |
| --------------------------------- | ------------------------------------------------------------------ | ------------------- |
| `rbac.create`                     | Create and use role based access resources                         | true                |
| `telemetry.host`                  | Host for prometheus server to to listen on                         | 0.0.0.0             |
| `telemetry.port`                  | Port for prometheus server to listen on                            | 8080                |
| `serviceMonitor.create`           | Whether or not to create a service monitor for prometheus operator | false               |
| `serviceMonitor.interval`         | Scrape interval for prometheus operator                            | 10s                 |
| `serviceMonitor.scrapeTimeout`    | Scrape timeout for prometheus operator                             | 10s                 |
| `serviceMonitor.releaseLabel`     | Release label being used for prometheus operator selector          | prometheus-operator |
| `serviceMonitor.additionalLabels` | Additional labels to add to the ServiceMonitor                     |                     |
| `metricsNamespace`                | Prefix of exposed prometheus metrics                               | eagle               |
| `logLevel`                        | Logger's log granularity (debug, info, warn, error, fatal, panic)  | info                |
