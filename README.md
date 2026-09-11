# fortinet-nse7-public-cloud-security-notes
Comprehensive community study guide, revision notes, hands-on lab scenarios, and study resources for the Fortinet Network Security Expert 7 (NSE 7) Public Cloud Security certification exam.
# Fortinet Network Security Expert 7: Public Cloud Security (NSE 7) Study Guide

Welcome to the ultimate community study guide for earning the **Fortinet Certified Network Security Expert 7 (NSE 7) – Public Cloud Security** credential (Exam Code: `NSE7_PBC-7.2`).

Whether you are a Cloud Security Engineer, Infrastructure Architect, or Network Security Specialist, this repository provides a structured roadmap to deploy, integrate, automate, and troubleshoot Fortinet security solutions across Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP).

---

## 📌 Certification Overview

The **NSE 7 Public Cloud Security** exam validates your ability to integrate Fortinet security solutions into multi-cloud environments, configure high-availability (HA) setups, implement auto-scaling, and secure public cloud workloads.

* **Exam Code:** NSE7_PBC-7.2
* **Exam Provider:** Pearson VUE / OnVUE Online
* **Question Count:** ~30–45 questions (Multiple Choice, Drag-and-Drop)
* **Passing Score:** Pass/Fail (Scored electronically; baseline pass score managed by Fortinet)
* **Duration:** 60 minutes
* **Prerequisites:** Active NSE 4 / NSE 5 / NSE 6 in the Cloud Security track (or equivalent prior credentials).
* **Validity:** Valid for 2 years upon passing.

---

## 🎯 Target Audience

- **Cloud Security Architects:** Engineers designing multi-cloud security topologies using FortiGate-VM and FortiCNAPP.
- **DevSecOps Engineers:** Technical leads automating public cloud firewall deployments using Terraform, CloudFormation, or ARM/Bicep templates.
- **Network & Systems Administrators:** Engineers responsible for managing SDN connectors, transit hubs, and cloud routing tables.

---

## 📊 Exam Objectives & Domain Breakdown

| Domain | Focus Areas |
| :--- | :--- |
| **AWS Cloud Security** | VPC Architecture, Transit Gateway (TGW) Integration, GWLB Deployments, Auto-Scaling Groups, IAM Roles, and SDN Connectors |
| **Microsoft Azure Cloud Security** | VNet Peering, Azure Route Server, Azure Load Balancers (ALB/GWLB), Active-Passive/Active-Active HA, and User-Defined Routes (UDRs) |
| **Google Cloud Platform Security** | VPC Network Peering, Cloud Router, Internal/External Load Balancing, Managed Instance Groups (MIGs), and GCP Cloud Connectors |
| **Centralized Cloud Management** | FortiManager integration, FortiAnalyzer logging, Security Fabric cloud connectors, and API-based threat intelligence feed updates |

---

## 🧠 Core Exam Concepts & Study Notes

### 1. AWS Architecture & Deployments
* **Gateway Load Balancer (GWLB):** Decouples security inspection from traffic flows. Uses GENEVE encapsulation on port `6081` to forward raw packet streams to FortiGate-VM inspection clusters without changing IP headers.
* **Transit Gateway (TGW):** Acts as a cloud router. Uses Appliance VPCs (Security VPCs) for centralized ingress/egress inspection.
* **SDN Connectors:** Connects FortiOS to AWS APIs using IAM roles to dynamic-update firewall address objects based on EC2 tags.

### 2. Azure Infrastructure & High Availability
* **Active-Passive HA with Floating IP / API:** Uses Azure API calls to manipulate User-Defined Routes (UDRs) during failover, shifting traffic to the secondary node.
* **Azure Gateway Load Balancer (GWLB):** Configures VXLAN-encapsulated health checks and traffic inspection pipelines to eliminate complex API failover delays.
* **Azure Route Server:** Uses BGP over IPsec or direct VNet peering to inject dynamic routes directly into Azure VNets from FortiGate-VMs.

### 3. Google Cloud Platform (GCP) Security
* **Network Connectivity Center (NCC):** Leverages Cloud Router and BGP to route inter-VPC traffic through FortiGate inspection instances.
* **Multi-NIC Architecture:** Deploying FortiGate-VM instances across separate GCP VPC networks (External, Internal, DMZ) for strict tenant isolation.

---

## 🛠️ Practical Hands-on Labs

Execute these scenario-based exercises in a sandbox cloud tenant prior to sitting the exam:

1. **Deploy GWLB with FortiGate-VM in AWS:**
   * Launch a Gateway Load Balancer and create a target group for two FortiGate-VM instances.
   * Enable GENEVE inspection ports (`6081`) on FortiOS interfaces.
   * Configure GWLB Endpoints in application VPC subnets and verify packet encapsulation flow.
2. **Configure Azure Dynamic Address Resolution using SDN Connectors:**
   * Create a Service Principal in Azure Entra ID with Network Contributor role.
   * Configure the SDN Connector in FortiManager/FortiOS using Tenant ID, Client ID, and Secret.
   * Create a Firewall Policy using dynamic address filters (e.g., `Tag.Env = Production`).
3. **Configure AWS Transit Gateway Security VPC:**
   * Create a central Security VPC containing pair of FortiGate-VMs.
   * Connect Application VPCs to Transit Gateway attachments.
   * Update TGW Route Tables to point `0.0.0.0/0` ingress/egress to the Security VPC attachment.

---

## 📅 30-Day Certification Study Plan
