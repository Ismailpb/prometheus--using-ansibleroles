# Prometheus-using-ansibleroles

Prometheus, Grafana, and Node Exporters are commonly used together to monitor system-level application insights. These tools specifically provide node and container statistics, which allow developers to analyse real-time metrics of containers and nodes. Prometheus Node Exporter can more specifically be used to get node metrics and system-level insights.

### What is Prometheus Node Exporter?

A Prometheus Exporter can fetch statistics from an application in the format used by that system (i.e. XML), convert those statistics into metrics that Prometheus can utilize, and then expose them on a Prometheus-friendly URL. There is a vast library of applications that can export metrics from third parties and transform them into  Prometheus metrics; that list can be found here.

