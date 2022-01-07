# Prometheus-using-ansibleroles

Prometheus, Grafana, and Node Exporters are commonly used together to monitor system-level application insights. These tools specifically provide node and container statistics, which allow developers to analyse real-time metrics of containers and nodes. Prometheus Node Exporter can more specifically be used to get node metrics and system-level insights.

### What is Prometheus Node Exporter?

A Prometheus Exporter can fetch statistics from an application in the format used by that system (i.e. XML), convert those statistics into metrics that Prometheus can utilize, and then expose them on a Prometheus-friendly URL. There is a vast library of applications that can export metrics from third parties and transform them into  Prometheus metrics; that list can be found here.

## Requirements

- Install Ansible on your machine (ansible master).
- Creating roles using Ansible-galaxy
- Ec2 instances for node-exporter, prometheus and grafana.

## Sample structure

Prometheus and Grafana is a monitoring stack to store and visualize time series data. Prometheus collects and stores metrics. Grafana provides a browser based interface to analyze and visualize data.
The dashboard contains any numbers of widgets to display metrics and resulting key performance indicators, for example “Performance as handled requests per second” or “Utilization as percentage of used CPU and memory resources”. Monitoring metrics leads to a better understanding of your computing environment and better decision making.


![image](https://github.com/Ismailpb/prometheus-using-ansibleroles/blob/d257f4976399d157520f5d3ebbaa67837c2960f8/Screenshot%20from%202022-01-08%2001-34-49.png)

In this project I have used 4 ec2 instances  and for node-exporter I have taken 3 instances and the remaining for monitoring server in which we will be installing prometheus(port:9090) and Grafana(port:3000) application.


## Variables Declaration

```
node_url: "https://github.com/prometheus/node_exporter/releases/download/v1.3.1/node_exporter-1.3.1.linux-amd64.tar.gz"
version: "1.3.1.linux-amd64"
prom_url: "https://github.com/prometheus/prometheus/releases/download/v2.32.1/prometheus-2.32.1.linux-amd64.tar.gz"
version_prom: "2.32.1.linux-amd64"
node_ip1: "172.31.45.45"
node_ip2: "172.31.41.248"
node_ip3: "172.31.33.212"
```

## Installation

1.Here we are going to create 3 roles for the project using the below command

```
ansible-galaxy init node-exporter
ansible-galaxy init prometheus
ansible-galaxy init grafana
```

2.Once the roles were created, we need to pass the values to the roles mentioned in the config file.

Mostly we are using the below folders mentioned under the roles to pass the values.

 - tasks
 
 - variables
 
 - files
    
 - templates

 - handlers

3. Since the values were moved to , you can run the playbooks using the command
```
ansible-playbook -i hosts install-node-exporter.yml
ansible-playbook -i hosts install-prometheus-grafana.yml
```

## Results

#### Node Exporter

![image](https://github.com/Ismailpb/prometheus-using-ansibleroles/blob/793426187ab00496abef8011f92e596969bac971/Untitled%20Project.png)

#### Prometheus

![image](https://github.com/Ismailpb/prometheus-using-ansibleroles/blob/3b5ec146b2a88cd0124ec78e0ae065e64f981e93/Untitled%20Project(2).png)

#### Grafana

![image](https://github.com/Ismailpb/prometheus-using-ansibleroles/blob/c0980940c891a8353448c6dede77158921a06ca3/Untitled%20Project(3).png)
