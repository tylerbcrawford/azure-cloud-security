![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat&logo=microsoftazure&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat&logo=ansible&logoColor=white)
![DVWA](https://img.shields.io/badge/DVWA-FF6600?style=flat)

# Azure Cloud Security Lab

Secure web application deployment on Azure — virtual network, Docker containers, Ansible provisioning, and load balancing. UofT cybersecurity program (2024).

## What I Built

A multi-VM setup on Azure running DVWA (Damn Vulnerable Web Application) behind a load balancer, managed through a gateway VM:

- **Virtual network** (`10.0.0.0/16`) with a subnet (`10.0.0.0/24`) and NSG rules locking down traffic to only what's needed — SSH from my workstation to the gateway, HTTP from the load balancer to the web VMs, and nothing else
- **Gateway VM (`RedTeamSecGW`)** as the single entry point. All VM management goes through it, so the web servers never need direct SSH exposure to the internet
- **Two web servers (`RedTeamWeb1`, `RedTeamWeb2`)** running DVWA in Docker containers, provisioned from the gateway. The gateway is labeled Ansible + Docker on the network diagram; the playbooks themselves are not included in this repo
- **Azure Load Balancer** distributing traffic across the web VMs with health probes. I tested failover by stopping the container on one VM and confirmed traffic rerouted to the healthy VM

## Architecture

![Network Architecture Diagram](Network_Diagram.png)

The network diagram shows the full topology — resource group, virtual network and subnet, NSG, NAT, the `RedTeamSecGW` gateway, the two DVWA web VMs, and the Azure Load Balancer backend pool.

## What I Learned

The provisioning piece was the most valuable part for me. Configuring the web VMs by hand would have been slow and easy to get wrong, so managing them from the gateway with Ansible and Docker meant I could rebuild the environment from a known state. That's basically how I approach my homelab now, with Docker Compose in place of Ansible.

## Companion Technical Brief

The repo also includes an Azure cloud-security technical brief from the same program. It documents a separate exercise: hardening an Azure-hosted web application. It covers WAF custom rules (including the SQL-injection managed rule and geo-blocking), SSL/TLS certificate binding and validity, and the role of an Azure Key Vault for keys, secrets, and certificates: **[Azure Project Report (PDF)](Azure_Project_Report.pdf)**

## Tools

Microsoft Azure, Ansible, Docker, DVWA, NSGs, Azure Load Balancer, Azure WAF, Azure Key Vault

## Context

Cloud security project for UofT's cybersecurity certificate program.
