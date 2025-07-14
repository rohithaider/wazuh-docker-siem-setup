# Wazuh SIEM Deployment with Docker on Linode

This repository contains configuration and setup instructions for deploying the Wazuh SIEM stack using Docker on a Linode cloud instance. The goal is to provide a scalable, cloud-based solution for threat detection, monitoring, and incident response.

---

## Limitations of Running Wazuh Locally

Running Wazuh on a local development or test machine may not be suitable for long-term or production use due to the following limitations:

- **Resource Constraints**: Wazuh requires significant CPU, memory, and disk I/O. Most local environments do not meet the recommended system requirements, especially when running the full stack (Wazuh Manager, Filebeat, Elasticsearch/OpenSearch, and Kibana/Dashboards).
- **Network Accessibility**: Local setups are typically behind NAT or firewalls, making it difficult to receive logs from remote agents or access dashboards externally.
- **Lack of Persistence and Isolation**: Without containerization or virtualization, it's harder to isolate services or maintain data across reboots and upgrades.
- **Security Risks**: A local setup often lacks proper access control, encryption, or hardened configurations required in production.
- **Scalability Issues**: Adding agents or scaling components becomes difficult on local machines not designed for distributed workloads.

---

## Advantages of Using Docker on Linode

Deploying Wazuh with Docker in a Linode cloud instance offers several benefits:

- **Scalability**: Easily scale components or distribute the stack across multiple nodes using Docker Compose or Swarm.
- **Resource Flexibility**: Choose Linode plans based on your needs and upgrade resources with minimal downtime.
- **Cloud Accessibility**: Enables secure, remote access to the Wazuh dashboards and supports receiving logs from distributed agents.
- **Isolation and Modularity**: Each component (e.g., Wazuh Manager, OpenSearch, Dashboard) runs in a separate container, reducing conflict and simplifying updates.
- **Automated Deployment**: Docker allows you to automate the entire deployment and redeployment process using version-controlled infrastructure.
- **Persistence and Backup**: Linode supports block storage, snapshots, and backup services to ensure your data is safe and recoverable.

---


---

# Wazuh SIEM Deployment with Docker on Linode

This repository provides a structured approach to deploying the Wazuh SIEM stack using Docker on a Linode cloud instance. Below is the full procedure broken down into manageable steps.

---

## Table of Contents

1. [Create and Configure Linode Instance](#1-create-and-configure-linode-instance)  
2. [Install Docker and Docker Compose](#2-install-docker-and-docker-compose)  
3. [Clone This Repository](#3-clone-this-repository)  
4. [Run Docker Compose Stack](#4-run-docker-compose-stack)  
5. [Verify Deployment and Access Dashboard](#5-verify-deployment-and-access-dashboard)  
6. [Connect Agents to Wazuh Manager](#6-connect-agents-to-wazuh-manager)  
7. [Monitoring and Logs](#7-monitoring-and-logs)  
8. [Security and Access Control](#8-security-and-access-control)  

---

## 1. Create and Configure Linode Instance
First use this link to create account in linode and get $100 free credit which will last you for 1 year. 
```url
https://www.linode.com/lp/linodetube/?ifso=networkchuck&utm_source=influencer&utm_medium=video&utm_campaign=networkchuck
```
<img width="1407" height="676" alt="image" src="https://github.com/user-attachments/assets/1ff52884-fa4d-4748-9fcd-83462a209252" />

<img width="1341" height="686" alt="Screenshot at Jul 13 23-10-05" src="https://github.com/user-attachments/assets/438b04c1-ec60-46c8-bcbb-cab5857ed49e" />

<img width="1254" height="691" alt="image" src="https://github.com/user-attachments/assets/012a3065-a2ed-4ea2-a6de-8dc377159fbc" />

<img width="1403" height="792" alt="selecting os config" src="https://github.com/user-attachments/assets/e5bcbc8f-ff35-4057-a81f-68368776ce2b" />

<img width="1411" height="686" alt="creating linode machine" src="https://github.com/user-attachments/assets/d2bfba9c-b2a0-47f2-a75f-a032581bdcda" />

<img width="1434" height="760" alt="installing Wazuh Docker" src="https://github.com/user-attachments/assets/3a50008f-0794-43cf-b4c5-76097bfd55cb" />

<img width="1331" height="756" alt="copy cred" src="https://github.com/user-attachments/assets/ad1b0728-4583-4957-9000-bb1cba6fe4ca" />

---

## 2. Install Docker and Docker Compose

<img width="984" height="726" alt="loggin in linode" src="https://github.com/user-attachments/assets/074b4761-91f4-4b32-9747-ae11930af73e" />

<img width="956" height="723" alt="update repo" src="https://github.com/user-attachments/assets/b96503f2-0642-4a96-9ac9-17b223033887" />

<img width="969" height="550" alt="installing docker " src="https://github.com/user-attachments/assets/b2079682-3bba-41ca-a862-06b709706a8f" />

<img width="948" height="690" alt="installatiion running" src="https://github.com/user-attachments/assets/0f469e09-9292-4a81-a262-d272409abd25" />


---

## 3. Clone This Repository

<img width="914" height="636" alt="cloning" src="https://github.com/user-attachments/assets/c5f7c52b-11da-48ee-b24e-3fdc734c9a6f" />

## 4. Run Docker Compose Stack

<img width="914" height="665" alt="check" src="https://github.com/user-attachments/assets/b767f7fe-23ca-40e7-9aa5-8fb36dd1e236" />

<img width="930" height="635" alt="showing node" src="https://github.com/user-attachments/assets/1c89992a-0a8a-4107-9f29-f33422ad43f5" />

<img width="925" height="620" alt="showing node 2" src="https://github.com/user-attachments/assets/b4335c8b-7c66-448a-9a17-3860a5b89f9c" />

<img width="1234" height="656" alt="copy docker code" src="https://github.com/user-attachments/assets/ccc1a8d8-2746-47c8-93fb-37bedd3cca03" />

<img width="1234" height="656" alt="copy docker code" src="https://github.com/user-attachments/assets/781b08c6-52c0-4486-9be0-947513ca3282" />

<img width="913" height="487" alt="pasting to terminal" src="https://github.com/user-attachments/assets/363166cd-cb4a-4fd4-83ae-b7c9e977ac12" />


<img width="923" height="410" alt="Deploying docker" src="https://github.com/user-attachments/assets/692fbe4e-12c8-4ae7-b770-c8bcf2d0b323" />

<img width="902" height="445" alt="wazuh complete" src="https://github.com/user-attachments/assets/d47a3f52-6431-4f61-a08e-317cfd328d7c" />

<img width="927" height="583" alt="wazuh running succes" src="https://github.com/user-attachments/assets/924cac6d-5785-4d0b-932b-3ec1eb603c4c" />

---

## 5. Access Dashboard

<img width="1350" height="790" alt="copy address" src="https://github.com/user-attachments/assets/0300a850-dce3-4aba-8e73-6b2afd92dca5" />

<img width="1403" height="709" alt="wazuh addrs" src="https://github.com/user-attachments/assets/18fc48c3-3e68-4d3d-b8ba-53931ab54fe6" />

<img width="1425" height="740" alt="wazuh open" src="https://github.com/user-attachments/assets/ae11e369-69a6-437e-938f-824654110ef6" />

<img width="872" height="473" alt="wazuh pass" src="https://github.com/user-attachments/assets/f6a45143-699b-47c0-baaf-111ec68ad13a" />

<img width="1417" height="723" alt="wazuh pass given" src="https://github.com/user-attachments/assets/4ff5ea09-c21f-4b07-ac64-6d5b25ba59ad" />

---

## 6. Connect Agents to Wazuh Manager

<img width="1415" height="735" alt="deploy agent" src="https://github.com/user-attachments/assets/91480e62-42e2-485c-8696-f1e7ac687a5b" />

<img width="1414" height="756" alt="adding agent 1" src="https://github.com/user-attachments/assets/c81de1ec-099c-4f1a-b5f1-cc3216d51644" />

<img width="1427" height="644" alt="run wazun command terminal" src="https://github.com/user-attachments/assets/35587a39-88c1-48c7-a45b-4811a6103689" />

<img width="1021" height="667" alt="wazuh added" src="https://github.com/user-attachments/assets/25992669-369a-4194-bf71-21c51f4504e6" />

<img width="1426" height="653" alt="mac connected" src="https://github.com/user-attachments/assets/023364f2-b0e1-4ff1-ba0d-213aed25c15e" />

## 7. Dashboard

<img width="1429" height="755" alt="mitre framework" src="https://github.com/user-attachments/assets/5ea176fa-0cdf-4922-89c2-5aa9f53e8b17" />

<img width="1421" height="817" alt="sca" src="https://github.com/user-attachments/assets/c701a00c-1494-4621-b18c-6e38e21842dc" />

<img width="881" height="587" alt="sca score" src="https://github.com/user-attachments/assets/a7001738-bb48-4aaa-8fd5-2e4a50f0b992" />

<img width="1411" height="762" alt="sca recommendation" src="https://github.com/user-attachments/assets/bc16d3a6-b0b8-455a-b9af-9cec72927a9a" />

<img width="1421" height="658" alt="image" src="https://github.com/user-attachments/assets/80ed84dd-637f-4cb0-bd99-87685ad0d1e1" />
























