# weblogic-monitoring-jmx-exporter
Weblogic Server Monitoring Using Prometheus JMX Exporter

## To use this configuration

First, clone this repository.

Mention the configuration to your jmx-exporter java agent like as follows:

`JAVA_OPTIONS="${JAVA_OPTIONS} -javaagent:/path/to/agent/jmx_prometheus_javaagent-0.20.0.jar=<port>:/path/to/config/weblogic-jmx-config.yaml"`

The Metrics will be exposed at `<your_server_url:<jmx_exprter_port>/metrics`

## Prometheus config to fetch the metrics to prometheus:

```
  - job_name: "Job Name"

    static_configs:
      - targets: ["managed_server_host:<jmx_exporter_port>", "managed_server2_host:<jmx_exporter_port>"]
        labels:
          domain: "domain_name"
```

The Grafana Dashboard has been added and updated. Please follow the instructions above and then import the dashboard from here to get the results correctly.
