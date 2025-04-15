# PrometheusTargetDown

## Meaning

The alert means that one or more prometheus scrape targets are down.
Prometheus works by sending an HTTP GET request to all of its “targets” every 60 seconds. 
## Impact

Metrics from a particular target cannot be scraped as such there is no data for this target in Prometheus and alerting can be hindered.

## Diagnosis

The alert indicates from which service/node prometheus is unable to scrape
You can find information to identify it under the `host` label.
If the service/server appears to be running fine, a common cause could be a misconfigured firewall, or an exporter service that is stopped.

LOCALHOST might indicate that the exporter is running on the Prometheus server itself.

```console
 - alertname = PrometheusTargetDown
...
 - host = SomeHost:1234
```

Following promQL can be used to check the trend over time.

```console
up == 0 
```
## Mitigation

Mitigation depends on the error reported by prometheus and there is no generic solution.

