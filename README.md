![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat&logo=microsoftazure&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat&logo=ansible&logoColor=white)
![DVWA](https://img.shields.io/badge/DVWA-FF6600?style=flat)

# Secure Cloud Infrastructure Deployment on Microsoft Azure

## Introduction

In this project, I designed and implemented a secure, cloud-based web application infrastructure using Microsoft Azure. The primary objective was to create a resilient and secure environment that demonstrates best practices in cloud security, load balancing, and redundancy. This project showcases practical knowledge in cloud computing, network security, automation using Ansible, and containerization with Docker.

## Table of Contents

- [Project Overview](#project-overview)
  - [Objectives](#objectives)
  - [Tools and Technologies](#tools-and-technologies)
- [Architecture Diagram](#architecture-diagram)
- [Results and Findings](#results-and-findings)
- [Skills Demonstrated](#skills-demonstrated)
- [Conclusion and Reflections](#conclusion-and-reflections)

## Project Overview

### Objectives

- **Design a Secure Virtual Network**: Establish a virtual network within Azure, segmented into subnets and secured with Network Security Groups (NSGs).
- **Implement a Jump Box for Secure Access**: Deploy a Jump Box to manage access to the virtual machines securely.
- **Deploy Web Servers with Docker Containers**: Use Docker to deploy web servers running the Damn Vulnerable Web Application (DVWA).
- **Automate Deployment with Ansible**: Leverage Ansible for automating the configuration and deployment of VMs and Docker containers.
- **Set Up Load Balancing for High Availability**: Configure an Azure Load Balancer to distribute traffic and ensure availability.
- **Configure Network Security**: Implement NSGs and firewalls to protect the infrastructure.
- **Test Redundancy and Failover Capabilities**: Validate the system's ability to handle failures gracefully.
- **Conduct Security Assessments**: Perform penetration testing and vulnerability assessments.

### Tools and Technologies

- Microsoft Azure
- Ansible
- Docker
- LEMP Stack (Linux, Nginx, MariaDB, PHP)
- Jump Box
- Network Security Groups (NSGs)
- Azure Load Balancer
- Damn Vulnerable Web Application (DVWA)

For a detailed project report, please refer to the [Project Report](Azure_Project_Report.pdf).

## Architecture Diagram

![Network Architecture Diagram](Network_Diagram.png)

*The diagram illustrates the Azure Virtual Network, subnets, Jump Box, web servers, load balancer, and their interconnections.*

## Results and Findings

- **High Availability and Redundancy**: The implementation of an Azure Load Balancer alongside multiple web servers ensured continuous availability of the web application. Even during simulated failures, the load balancer successfully redirected traffic to healthy servers, demonstrating effective redundancy and failover capabilities.

- **Enhanced Security Posture**: By employing Network Security Groups (NSGs) and a Jump Box, the network was secured against unauthorized access. The Jump Box acted as a secure gateway, limiting exposure of the virtual machines to the internet. NSGs enforced strict traffic rules, reducing the attack surface and protecting the infrastructure from potential threats.

- **Automation and Efficiency**: Utilizing Ansible for automation streamlined the deployment and configuration processes. This approach minimized manual errors and ensured consistency across the environment, allowing for rapid scaling and easy replication of the infrastructure.

- **Successful Security Testing**: Penetration testing and vulnerability assessments were conducted to evaluate the security of the setup. The tests confirmed that the implemented security measures effectively protected the infrastructure against common threats, validating the robustness of the security configurations.

## Skills Demonstrated

- Cloud Infrastructure Design and Deployment (Azure)
- Network Security Group (NSG) Configuration
- Infrastructure Automation with Ansible
- Docker Container Deployment and Management
- Load Balancing and High Availability Architecture
- Security Assessment and Penetration Testing
- Defense-in-Depth Strategy Implementation

## Conclusion and Reflections

This project was a comprehensive exercise in designing and deploying a secure, scalable, and highly available web application infrastructure on Microsoft Azure. It reinforced my understanding of cloud security principles and highlighted the critical role of automation in modern IT environments. Implementing robust security measures, such as Network Security Groups and a Jump Box, emphasized the necessity of defense-in-depth strategies. The experience also underscored the value of redundancy and load balancing in achieving high availability. Overall, this project enhanced my skills in cloud computing, network security, and automation, aligning well with the requirements of a cybersecurity professional.
