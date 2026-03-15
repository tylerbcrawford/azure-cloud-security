![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat&logo=microsoftazure&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat&logo=ansible&logoColor=white)
![DVWA](https://img.shields.io/badge/DVWA-FF6600?style=flat)

# Azure Cloud Security Lab

Secure web application deployment on Azure — virtual network, Docker containers, Ansible automation, and load balancing. UofT cybersecurity program (2024).

## What I Built

A multi-VM setup on Azure running DVWA (Damn Vulnerable Web Application) behind a load balancer, managed through a Jump Box:

- **Virtual network** segmented into subnets with NSG rules locking down traffic to only what's needed — SSH from my IP to the Jump Box, HTTP from the load balancer to the web VMs, and nothing else
- **Jump Box** as the single entry point. All VM management goes through it, so the web servers never need direct SSH exposure to the internet
- **3 web servers** running DVWA in Docker containers, deployed and configured identically via Ansible playbooks from the Jump Box
- **Azure Load Balancer** distributing traffic across the web VMs with health probes — I tested failover by stopping containers on individual VMs and confirmed traffic rerouted within seconds

## Architecture

![Network Architecture Diagram](Network_Diagram.png)

The network diagram shows the full topology — virtual network, subnets, NSG rules, Jump Box, web server pool, and load balancer configuration.

## What I Learned

The Ansible piece was the most valuable part for me. Manually configuring 3 identical VMs would have been tedious and error-prone — writing the playbook took longer upfront but meant I could tear down and rebuild the entire environment in minutes. That's basically how I approach my homelab now, just with Docker Compose instead of Ansible.

## Tools

Microsoft Azure, Ansible, Docker, DVWA, NSGs, Azure Load Balancer

## Report

Full project report with configuration details and security assessment: **[Azure Project Report (PDF)](Azure_Project_Report.pdf)**

## Context

Cloud security project for UofT's cybersecurity certificate program.
