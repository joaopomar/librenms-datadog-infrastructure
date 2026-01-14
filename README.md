# Hybrid Network Monitoring System with LibreNMS

## Context
Project developed for the **Network Management** (Gestão de Redes) course at the **Coimbra Institute of Engineering (ISEC)**, academic year 2025/2026.

## Project Goal
The objective was to implement a robust **hybrid monitoring infrastructure** to analyze network availability and performance. The system combines an On-Premise solution (**LibreNMS**) with a SaaS platform (**Datadog**) to ensure redundancy and proactive management.

## System Architecture

The infrastructure was simulated using **GNS3** and consists of two main segments:
* **Management Network (192.168.200.0/24):** Hosts the LibreNMS server.
* **Client Network (192.168.102.0/24):** Hosts the Web Clients and end-devices.

### Key Components
1.  **LibreNMS (Primary Monitoring):**
    * Installed on an Ubuntu Server with a LEMP stack (Linux, Nginx, MariaDB, PHP).
    * Uses **SNMP** for active polling and **LLDP** for automatic network mapping.
    * Centralizes **Syslogs** from Cisco routers and Linux servers.
2.  **Datadog (Secondary Monitoring):**
    * Cloud-based agent providing redundancy and external availability checks.
3.  **Cisco Equipment:**
    * **Router (R1):** Configured with NAT Overload and Syslog forwarding[cite: 243, 420].
    * **Switch (SW-01 - Cisco IOU):** Managed switch with SNMP and LLDP enabled for Layer 2 visibility.
4.  **Automation:**
    * **Ansible** playbooks were used to automate the deployment and configuration of SNMP agents across client machines.

## Features Implemented
* **Service Monitoring:** Nginx (via stub_status) and MariaDB (queries/traffic).
* **Alerting:** Disk usage warnings and connection status.
* **Visual Topology:** Automatic network maps generated via LLDP discovery.

## Authors
* **João Pedro Vila Pomar** 
* **Rodolfo Miguel de Sousa Belchior Brás Oliveira**  
