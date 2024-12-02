
# POC for Panopta

| Author     | Created on    | Version   | Last updated by | Last edited on  | Comment                    |
|------------|---------------|-----------|-----------------|-----------------|----------------------------|
| DevOps Team | 02-12-2024   | 1.0       | DevOps Team     | 02-12-2024      | Initial POC documentation  |

---

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

## Testing and Validation

| Test Case | Description                     | Expected Outcome                                      | Status |
|-----------|---------------------------------|------------------------------------------------------|--------|
| TC1       | Check server uptime monitoring  | Uptime should reflect 99.99%.                        | ✅ Pass |
| TC2       | Trigger CPU usage alert         | Alert should trigger if CPU exceeds 80%.             | ✅ Pass |
| TC3       | Integration with Slack          | Notification should appear in the specified channel. | ✅ Pass |
| TC4       | Downtime alert for MySQL        | Alert should trigger if MySQL stops responding.      | ✅ Pass |

---

## Troubleshooting

| Problem                        | Solution                                                                                      |
|--------------------------------|----------------------------------------------------------------------------------------------|
| Agent not registering          | Verify API key and ensure the agent can access the Panopta API endpoint.                     |
| Alerts not triggering           | Check thresholds and ensure the system is generating metrics correctly.                     |
| Dashboard not loading          | Confirm internet connectivity and verify login credentials.                                  |
| Metrics not appearing in UI    | Restart the Panopta agent: `sudo systemctl restart panopta-agent`.                           |

---

## Final Output

Once the setup is complete and all tests have passed, the monitoring dashboard will display real-time metrics and alerts for monitored resources.

---

## Contact Information

| Name       | Email Address                  |
|------------|--------------------------------|
| DevOps Team| devops-team@example.com        |

---

## Reference Links

| Links                                                       | Description                                         |
|-------------------------------------------------------------|-----------------------------------------------------|
| [Panopta Documentation](https://www.panopta.com/docs/)      | Official Panopta documentation.                    |
| [Slack Integration Guide](https://slack.com/integration)    | Step-by-step guide to integrating Panopta with Slack. |
| [Troubleshooting Agent](https://www.panopta.com/agent-help) | Help section for resolving agent-related issues.    |

---
