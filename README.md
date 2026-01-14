# Hybrid Network Monitoring System with LibreNMS

## Context
[cite_start]Project developed for the **Network Management** (Gestão de Redes) course at the **Coimbra Institute of Engineering (ISEC)**, academic year 2025/2026[cite: 161, 162, 165].

## Project Goal
The objective was to implement a robust **hybrid monitoring infrastructure** to analyze network availability and performance. [cite_start]The system combines an On-Premise solution (**LibreNMS**) with a SaaS platform (**Datadog**) to ensure redundancy and proactive management[cite: 207, 208, 209].

## System Architecture

The infrastructure was simulated using **GNS3** and consists of two main segments:
* [cite_start]**Management Network (192.168.200.0/24):** Hosts the LibreNMS server[cite: 218].
* [cite_start]**Client Network (192.168.102.0/24):** Hosts the Web Clients and end-devices[cite: 219].

### Key Components
1.  **LibreNMS (Primary Monitoring):**
    * [cite_start]Installed on an Ubuntu Server with a LEMP stack (Linux, Nginx, MariaDB, PHP)[cite: 283].
    * [cite_start]Uses **SNMP** for active polling and **LLDP** for automatic network mapping[cite: 416, 418].
    * [cite_start]Centralizes **Syslogs** from Cisco routers and Linux servers[cite: 363].
2.  **Datadog (Secondary Monitoring):**
    * [cite_start]Cloud-based agent providing redundancy and external availability checks[cite: 333, 338].
3.  **Cisco Equipment:**
    * [cite_start]**Router (R1):** Configured with NAT Overload and Syslog forwarding[cite: 243, 420].
    * [cite_start]**Switch (SW-01 - Cisco IOU):** Managed switch with SNMP and LLDP enabled for Layer 2 visibility[cite: 254, 255].
4.  **Automation:**
    * [cite_start]**Ansible** playbooks were used to automate the deployment and configuration of SNMP agents across client machines[cite: 373].

## Features Implemented
* [cite_start]**Service Monitoring:** Nginx (via stub_status) and MariaDB (queries/traffic)[cite: 354, 357].
* [cite_start]**Alerting:** Disk usage warnings and connection status[cite: 621].
* [cite_start]**Visual Topology:** Automatic network maps generated via LLDP discovery[cite: 418].

## Authors
* [cite_start]**João Pedro Vila Pomar** (a2023140947@isec.pt) [cite: 159]
* [cite_start]**Rodolfo Miguel de Sousa Belchior Brás Oliveira** (a2023155660@isec.pt) [cite: 160]
