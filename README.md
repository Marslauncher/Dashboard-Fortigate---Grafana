Fortigate 40F Dashboard for Grafana
This repository contains an advanced dashboard for monitoring Fortigate 40F firewalls using Zabbix. The dashboard was designed to provide a clear view of both hardware and the health of internet links (SD-WAN) and VPN tunnels.

<img width="1910" height="1040" alt="image" src="https://github.com/user-attachments/assets/258af2f5-2222-4320-bdc2-5e8dd9d3bf0e" />

What is being monitored?
The dashboard is divided into strategic sections to make network administration easier:

Visual Identity & Status: Custom header and visual representation of the physical ports of the Fortigate 40F.

Hardware Resources:

CPU usage (with dynamic ECharts graph).

RAM memory usage.

System uptime.

Connectivity & SD-WAN:

Real-time ICMP latency for multiple links (e.g. Starlink, Valenet).

Connectivity status history.

Interface traffic (Download/Upload) detailed by link.

VPN Tunnels: Monitoring of Site-to-Site tunnel status (Online/Offline).

Network Health: Detection of packet errors on specific interfaces (Inbound/Outbound errors).

Prerequisites

To make the dashboard work correctly, you will need:

Zabbix Server with the Fortigate 40F already added via SNMP (using standard Fortinet templates).

Grafana plugins:

Zabbix Data Source

ECharts Panel (used in the CPU graph)

Business Text (optional) (for the HTML header)

How to Install (Step by Step)
Download the JSON file: Download the Fortigate-40F.json file available in this repository.

In your Grafana:

Go to Dashboards -> New -> Import.

Click Upload JSON file and select the downloaded file.

Data Source Configuration:

On the import screen, Grafana will ask you to select a data source. Choose your Zabbix Data Source.

Make sure the names of the Hosts and Groups in your Zabbix match the dashboard filters (or adjust the filters after importing).

Final Adjustments:

If the interface graphs appear empty, check whether the interface names in your Fortigate match the metrics (e.g. lan3, wan1).

Contributions
Feel free to open an Issue if you find a bug or submit a Pull Request with improvements. Feedback on new SD-WAN panels or firewall rules is very welcome!
