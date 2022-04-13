### About

This NCache Grafana app plugin provides a set of dashboards that allows a user to monitor NCache counters.
NCache's app plugin uses Prometheus as datasource.

### Dashboards

 * Cache
 * Client
 * Bridge

### Setup instructions


To Setup Grafana for NCache monitoring you have to follow the following steps:

	 * Add Prometheus as Datasource
	 * Import Dashboards

#### Add Prometheus as Datasource

Prometheus is one of the officialy supported datasources for Grafana.
Add Prometheus as datasource and name it 'Prometheus' because the default counters rely on datasource named Prometheus.

#### Import dashboards

After Enabling NCache's plugin goto Plugin Config and then goto Dashboards page.
Import required dashboards from this page.

#### Prometheus configuration

Add all those nodes as targets for which you want to monitor NCache counters.
For example, if you want to monitor `192.168.1.7` the config file will look like this:

    scrape_configs:

     - job_name: 'NCache'

		# metrics_path defaults to '/metrics'
		# scheme defaults to 'http'.

		static_configs:
		- targets: ['192.168.1.7:8255']


##### v1.0.0
- Preview version.
