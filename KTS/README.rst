===============================
Kibana 4 Templates for Suricata
===============================

Templates/Dashboards for Kibana 4 to use with Suricata IDPS and the ELK stack

This repository provides 11 templates for the Kibana 4.4 and Elasticsearch 2.x
for use with Suricata IDS/IPS - Intrusion Detection and Prevention System.

These dashboards are for use with Suricata and ELK - Elasticsearch, Logstash, 
Kibana and comprise of more than 140 visualizations and 11 searches.

The dashboards are:

 - ALL  
 - ALERTS 
 - DNS  
 - FILE Transactions  
 - FLOW  
 - HTTP  
 - SMTP
 - SSH  
 - TLS
 - VLAN
 - STATS

How to use
==========

::

     apt-get install git-core
     git clone https://github.com/StamusNetworks/KTS.git
     cd KTS
     
Kibana 4.4.x needs to be patched in order to load the templates.
If you have installed Kibana in ``/opt/kibana`` for example: ::

 patch -p1 -d /opt/kibana/  < full/path/to/KTS/patches/kibana-integer.patch
 patch -p1 -d /opt/kibana/  < full/path/to//KTS/patches/timelion-integer.patch

**NOTE:**  The loading of the dashboards will ***delete and replace*** any previously exiting templates/visualizations. !!!

Load the dashboards: ::

 ./load.sh

Open the dashboards in Kibana

 - Open your Kibana web interface (ip.ip.ip.ip:5601), select default index
 - Right upper corner, Load -> Choose the desired dashboard
 - Load the desired template(s)

**NOTE:**  
In order to use the full HTTP logging dashboard template you need to set up Suricata as
explained here - http://www.pevma.blogspot.se/2014/06/http-header-fields-extended-logging.html  

**NOTE:**  
If the traffic you are inspecting contains vlans - in order to use the VLAN template, make sure you have enabled vlan tracking in ``suricata.yaml`` -

     vlan:
       use-for-tracking: true

**NOTE:**  
For best user experience use with 1680 x 1050 screen resolution!!  

Do not hesitate to test,feedback and contribute !
