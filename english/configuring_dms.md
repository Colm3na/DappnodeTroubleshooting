# Configuring Dms Package
The main objetive of this guide is setting a monitoring system for our DAppNode.

## Installation of the Dappnode Exporter package

In order to install Dappnode Exporter package, you should write in the searching bar of the DAppStore:

~~~
exporter
~~~

It will show the next package: 

![Node-exporter package](../img/node_exporter_1.png "Searching the node-exporter package")

We have to click on the package called Dappnode exported. And press the INSTALL button.

![Installing Node-exporter package](../img/node_exporter_2.png " ")

If all goes well, you will see something like the next image: 

![Node-Exporter installed](../img/node_exporter_3.png " ")

In order to check that is well installed, and show what we have installed in our dappnode, click the "Node_exporter" link, which is above of the word Status.

A new blank window will appear with a link called "Metrics", click on it and you will see something similar to:

~~~
# HELP go_gc_duration_seconds A summary of the pause duration of garbage collection cycles.
# TYPE go_gc_duration_seconds summary
go_gc_duration_seconds{quantile="0"} 8.902e-06
go_gc_duration_seconds{quantile="0.25"} 3.43e-05
go_gc_duration_seconds{quantile="0.5"} 0.000147245
go_gc_duration_seconds{quantile="0.75"} 0.000279352
go_gc_duration_seconds{quantile="1"} 0.001784388
go_gc_duration_seconds_sum 0.014444746
go_gc_duration_seconds_count 79
# HELP go_goroutines Number of goroutines that currently exist.
# TYPE go_goroutines gauge
go_goroutines 8
# HELP go_info Information about the Go environment.
# TYPE go_info gauge
go_info{version="go1.14.6"} 1
# HELP go_memstats_alloc_bytes Number of bytes allocated and still in use.
# TYPE go_memstats_alloc_bytes gauge
go_memstats_alloc_bytes 2.561768e+06
# HELP go_memstats_alloc_bytes_total Total number of bytes allocated, even if freed.
# TYPE go_memstats_alloc_bytes_total counter
...
~~~

### What is this?

They are parameters what are being recopilated by the package which we have just installed, and this package is exposing it, because on this way we can use a "tool" like grafana to collect them and monitoring the state of our machine.

The next step, it is installing the Dms package in our DappNode.( This Dms package contains that grafana tool that I mentioned before)

## Installing the Dms package

Search in the navigation bar of the DAppStore:

![Metrics's package](../img/configuring_dms_1.png "Searching the package Dms")

Click on it and press the INSTALL button:

![Installing the package](../img/configuring_dms_2.png " ")

Once the installation process is finished, it will appear the next window:

![Dms's package installed](../img/configuring_dms_3.png " ")

In this configuration window of the Dms package, we have several options:
* **Homepage**: This link will redirect us to the github repository of dappnode's pakage, https://github.com/dappnode/DMS#readme.
*  **Ui**: Redirect to the Web User Interface of Grafana. Specifically, to the dashboard section, it is where we can see a list with all our monitoring panels.
*  **Grafana**: Redirect to the main page of grafana.
*  **Prometheus-Targets**: Redirect to "the other side" of prometheus, when we installed the package "Node-exporter" we installed a prometheus server that exposes the metrics of our dappnode, so here we use a prometheus client to ask that metrics and process them.
*  **Manager-Status**: Show the dockers we are monitoring. All of them are collected in the dashboard "dappnode-exporter dashboard".

After explain a bit what options we had, select the option **Ui**. The next window will appear:

![Dashboards en grafana](../img/configuring_dms_4.png " ")

Clicking on the dappnode-exporter dashboards appears 2 options:

* **Docker**: They are the system metrics, or software metrics,i.e.,it shows how many of the machine's resources is using every package of our dappnode.
*  **Host**: They are the "hardware metrics", for example: ram usage, free disk space, network usage, etc. General metrics of our machine.

If we click in some of this option, you will se something like:

![dashboard docker](../img/configuring_dms_5.png " ")

So this is all for now, you would have finished of installed the monitoring system of your dappnode.

This a little guide for people that never used programs like this.

Some of the most interesting and usefull thinks that ou can do with grafana is add alerts(telegram messages,emails, etc) in the case your dappnode has problem.

I hope this guide will be usefull for some people. 

PD: English is not my first language, sorry if I commited gramar mistakes or something is not well explained. If you have some suggestions, i am glad to read them. 