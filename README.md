# StatsdGrafana
Test Statsd with Grafana over Ubuntu

as root
nano /etc/apt/sources.list
deb https://packagecloud.io/grafana/testing/debian/ jessie main
curl https://packagecloud.io/gpg.key | apt-key add -

apt-get install grafana
	Reading package lists... Done
	Building dependency tree
	Reading state information... Done
	The following NEW packages will be installed:
	  grafana
	0 upgraded, 1 newly installed, 0 to remove and 72 not upgraded.
	Need to get 45.9 MB of archives.
	After this operation, 135 MB of additional disk space will be used.
	Get:1 https://packagecloud.io/grafana/stable/debian/ jessie/main grafana amd64 4.2.0 [45.9 MB]
	Fetched 45.9 MB in 2s (19.8 MB/s)
	Selecting previously unselected package grafana.
	(Reading database ... 41702 files and directories currently installed.)
	Preparing to unpack .../grafana_4.2.0_amd64.deb ...
	Unpacking grafana (4.2.0) ...
	Processing triggers for systemd (215-17+deb8u5) ...
	Setting up grafana (4.2.0) ...
	Adding system user `grafana' (UID 109) ...
	Adding new user `grafana' (UID 109) with group `grafana' ...
	Not creating home directory `/usr/share/grafana'.
### NOT starting on installation, please execute the following statements to configure grafana to start automatically using systemd
 sudo /bin/systemctl daemon-reload
 sudo /bin/systemctl enable grafana-server
### You can start grafana-server by executing
 sudo /bin/systemctl start grafana-server
Processing triggers for systemd (215-17+deb8u5) ...
## Install telegraf
 wget https://dl.influxdata.com/telegraf/releases/telegraf-1.2.1_linux_amd64.tar.gz
 tar xvfz telegraf-1.2.1_linux_amd64.tar.gz

 wget https://dl.influxdata.com/influxdb/releases/influxdb_1.2.2_amd64.deb
 dpkg -i influxdb_1.2.2_amd64.deb
	Selecting previously unselected package influxdb.
	(Reading database ... 46541 files and directories currently installed.)
	Preparing to unpack influxdb_1.2.2_amd64.deb ...
	Unpacking influxdb (1.2.2-1) ...
	Setting up influxdb (1.2.2-1) ...
	Created symlink from /etc/systemd/system/influxd.service to /lib/systemd/system/influxdb.service.
	Created symlink from /etc/systemd/system/multi-user.target.wants/influxdb.service to /lib/systemd/system/influxdb.service.
	Processing triggers for man-db (2.7.0.2-5) ...
/bin/systemctl enable /lib/systemd/system/influxdb.service
service influxdb start
service influxdb status
Getting started with Influxdb
 https://docs.influxdata.com/influxdb/v1.2/introduction/getting_started/


