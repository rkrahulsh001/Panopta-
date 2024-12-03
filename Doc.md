
# POC for Panopta
![image](https://github.com/user-attachments/assets/2f9b8e82-e143-43b8-982d-89c3950ce7a6)

.
| Author     | Created on    | Version   | Last updated by | Last edited on  | Comment                    |
|------------|---------------|-----------|-----------------|-----------------|----------------------------|
| NOC Team | 01-12-2024   | 1.0       | Rahul Sharma     | 02-12-2024      | Initial POC documentation  |

# Introduction 

Panopta is a comprehensive monitoring solution that provides real-time insights into the performance and availability of your infrastructure. It's ideal for monitoring servers, applications, network devices, and more, offering proactive alerts to ensure high uptime and optimal performance.

---
# Panopta Alerting Methods

This document summarizes the different types of alerts available in Panopta and their use cases.

| **Alert Type**               | **Description**                                                                 | **Use Case**                                                                        |
|------------------------------|---------------------------------------------------------------------------------|------------------------------------------------------------------------------------|
| **Phone Call Alerts**        | Sends voice alerts to notify the team about critical incidents, requiring immediate attention. | Used for high-priority incidents such as server failures, outages, etc.            |
| **SMS Alerts**               | Sends short text message notifications for quick issue identification and response. | Ideal for on-the-go notifications, especially when away from the desk.             |
| **Email Alerts**             | Sends detailed emails with information about the issue, including logs and recommendations for resolution. | Best for incidents requiring more details or when internet is available.           |
| **Third-Party Integrations** | Integrates with platforms like Slack, PagerDuty, Microsoft Teams, and OpsGenie for enhanced communication. | Streamlines notifications into collaboration tools for better team coordination.   |

This table summarizes the different types of alerts and how they can be used within the Panopta monitoring system.



## Table of Contents

| Index                                                                                                   |
|---------------------------------------------------------------------------------------------------------|
| [Key Features](#key-features)                                                                          |
| [Run-Time Dependencies](#run-time-dependencies)                                                        |
| [Installation Steps](#installation-steps)                                                              |
| [Configuration](#configuration)                                                                        |
| [Monitoring Setup](#monitoring-setup)                                                                  |
| [Testing and Validation](#testing-and-validation)                                                      |
| [Troubleshooting](#troubleshooting)                                                                    |
| [Final Output](#final-output)                                                                          |
| [Contact Information](#contact-information)                                                            |
| [Reference Links](#reference-links)                                                                    |

---

## Key Features

| No. | Feature Description         | Description                                                                 |
|-----|-----------------------------|-----------------------------------------------------------------------------|
| 1.  | Comprehensive Monitoring    | Monitors servers, cloud, containers, and applications with ease.            |
| 2.  | Alerting System             | Provides real-time alerts via integrations like Slack, PagerDuty, etc.      |
| 3.  | Dashboard & Reports         | Offers customizable dashboards and automated reports for better visibility. |
| 4.  | Root Cause Analysis         | Helps in pinpointing the root cause of incidents and reducing downtime.     |

---

## Run-Time Dependencies

| No. | Software/Tool           | Description                                         |
|-----|-------------------------|-----------------------------------------------------|
| 1.  | [Python 3.8+](https://www.python.org/downloads/) | Required for agent installation and scripting. |
| 2.  | Open Ports              | Ensure ports 443 and 8443 are open for communication. |
| 3.  | Web Browser             | Chrome/Firefox for accessing Panopta's dashboard.   |

---

## Installation Steps

![image](https://github.com/user-attachments/assets/73fae7d3-5bb0-44ae-885a-f0e6e0e6daf9)

![image](https://github.com/user-attachments/assets/56c32eee-954d-4419-8b6d-4a97faca1755)

![image](https://github.com/user-attachments/assets/f65a8a45-994f-4cb2-ab84-4dd46d07c394)

![image](https://github.com/user-attachments/assets/ceeb628a-ad8f-4cb4-b3fc-93580ed55a03)

![image](https://github.com/user-attachments/assets/3b8049a3-75e6-41c3-ad43-440d00551aba)

![image](https://github.com/user-attachments/assets/4df5894d-52e5-4d98-9b79-caba13456625)

![image](https://github.com/user-attachments/assets/799a2764-c605-4f8c-99b2-11cf35293fa0)

![image](https://github.com/user-attachments/assets/c48e654f-148c-4430-a941-c8059535eb2d)

![image](https://github.com/user-attachments/assets/982c16ba-b600-4a4d-b08d-760d22a4f30f)

![image](https://github.com/user-attachments/assets/440e1cea-857f-42aa-b73a-86ba0bc0d44d)

![image](https://github.com/user-attachments/assets/71004a64-bdb9-4f99-b733-f6c51cf6a198)

![image](https://github.com/user-attachments/assets/84af2384-e0ef-48d9-88a6-5c8a05abb483)



![image](https://github.com/user-attachments/assets/99df8253-2962-4b0b-80db-c87258f9da11)


| **Feature**              | **Included in Basic Plan** | **Included in Advanced Plan** | **Additional Cost**          |
|---------------------------|----------------------------|--------------------------------|-------------------------------|
| **Email Alerts**          | ✔ Unlimited               | ✔ Unlimited                   | None                         |
| **SMS Alerts**            | Limited or Not Included   | ✔ Included                    | Per SMS (e.g., $0.10–$0.20)  |
| **Phone Call Alerts**     | Limited or Not Included   | ✔ Included                    | Per Call (e.g., $0.20–$0.50) |
| **Slack/MS Teams Alerts** | Limited                   | ✔ Included                    | None for Premium Plans       |
| **Number of Contacts**    | Limited (e.g., 5 users)   | ✔ Expanded (10+ users)        | Additional users: $5–$10/mo  |
| **Third-Party Integrations** (PagerDuty, etc.) | Not Included           | ✔ Included                    | Integration-specific costs   |
| **Custom Escalation Rules**| Basic                    | ✔ Advanced                    | May require premium plans    |
| **Incident Analytics**    | Not Included             | ✔ Included                    | Included with premium plans  |

### Monthly Costs:
1. **Basic Plan**: $50–$150/month (email alerts, limited contacts, no SMS/calls).  
2. **Advanced Plan**: $200–$500/month (includes advanced alerting, unlimited email, SMS/calls, and integrations).  
3. **Add-Ons**: SMS/phone usage or additional recipients may increase costs.






1. **Add Panopta Agent Repository**  
   ```bash
   curl -s https://monitoring-api.panopta.com/agent/setup.sh | sudo bash
   ```

   *This script sets up the Panopta agent repository on your system.*

2. **Install the Panopta Agent**  
   ```bash
   sudo apt-get install panopta-agent
   ```

   *This installs the Panopta monitoring agent.*

3. **Verify Installation**  
   ```bash
   panopta-agent --version
   ```

   *This checks if the agent is installed correctly.*

---

## Configuration

1. **Agent Registration**  
   Run the following command to link the agent to your Panopta account:
   ```bash
   panopta-agent --register --key YOUR_API_KEY
   ```

   Replace `YOUR_API_KEY` with the API key provided in the Panopta dashboard.

2. **Configure Monitored Resources**  
   Define which servers, applications, or containers need to be monitored by editing the configuration file:  
   ```bash
   sudo vim /etc/panopta-agent.conf
   ```

   Example configuration for monitoring:  
   ```json
   {
       "monitoring": ["nginx", "mysql", "system_resources"]
   }
   ```

---

## Monitoring Setup

1. **Add Monitoring Points**  
   Log in to the Panopta web dashboard and add nodes for monitoring.  
   Example: Add an **EC2 instance** under the **Servers** tab.

2. **Set Up Alerts**  
   Go to the **Alerting** tab and configure:
   - Thresholds for CPU, RAM, Disk usage.
   - Notifications via Slack, Email, or PagerDuty.

---


## Troubleshooting

| Problem                        | Solution                                                                                      |
|--------------------------------|----------------------------------------------------------------------------------------------|
| Agent not registering          | Verify API key and ensure the agent can access the Panopta API endpoint.                     |
| Alerts not triggering           | Check thresholds and ensure the system is generating metrics correctly.                     |
| Dashboard not loading          | Confirm internet connectivity and verify login credentials.                                  |
| Metrics not appearing in UI    | Restart the Panopta agent: `sudo systemctl restart panopta-agent`.                           |

---


## Contact Information

| Name       | Email Address                  |
|------------|--------------------------------|
| NOC Team| rahul.sharma@tiket.com       |

---

## Reference Links

| Links                                                       | Description                                         |
|-------------------------------------------------------------|-----------------------------------------------------|
| [Panopta Documentation](https://www.panopta.com/docs/)      | Official Panopta documentation.                    |
| [Slack Integration Guide](https://slack.com/integration)    | Step-by-step guide to integrating Panopta with Slack. |
| [Troubleshooting Agent](https://www.panopta.com/agent-help) | Help section for resolving agent-related issues.    |

---
