# SIEM Home Lab Project with Elastic Stack: Alerting and Notifications

## Table of Contents
- [Introduction](#introduction)
- [Objectives](#objectives)
- [Elastic Stack Components Used](#elastic-stack-components-used)
- [Lab Setup and Configuration](#lab-setup-and-configuration)
  - [System Requirements](#system-requirements)
  - [Installation Steps](#installation-steps)
- [Configuring Alerting and Notifications](#configuring-alerting-and-notifications)
- [Testing the Alerting and Notification Pipeline](#testing-the-alerting-and-notification-pipeline)
- [Conclusion](#conclusion)

## Introduction
This project demonstrates a SIEM (Security Information and Event Management) solution using Elastic Stack to monitor, detect, and alert on security events. The focus is on setting up alerting and notifications for potential security incidents.

## Objectives
- Set up Elastic Stack as a SIEM tool.
- Configure alerting mechanisms to notify about suspicious activities.
- Test the alerting pipeline to ensure effective monitoring.

## Elastic Stack Components Used
- **Elasticsearch**: Core data store and analytics engine.
- **Logstash**: Data processing pipeline for ingestion.
- **Kibana**: Visualization tool for dashboards and alert management.
- **Elastic Alerting and Notifications**: Configured for automatic alerts on security events.

## Lab Setup and Configuration

### System Requirements
- **Minimum**: 4GB RAM, 2 CPU cores
- **Recommended**: 8GB RAM, 4 CPU cores, SSD storage
- **Operating System**: Ubuntu 20.04 LTS
- **Network**: Local environment (no direct internet exposure for security)

### Installation Steps
1. **Install Elasticsearch**:
   ```bash
   wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.x.x-amd64.deb
   sudo dpkg -i elasticsearch-7.x.x-amd64.deb
   sudo systemctl start elasticsearch
   sudo systemctl enable elasticsearch
   
2. **Install Logstash**:
  ```bash
    wget https://artifacts.elastic.co/downloads/logstash/logstash-7.x.x.deb
    sudo dpkg -i logstash-7.x.x.deb
    sudo systemctl start logstash
    sudo systemctl enable logstash

3. Install Kibana:
  ```bash
    wget https://artifacts.elastic.co/downloads/kibana/kibana-7.x.x-amd64.deb
    sudo dpkg -i kibana-7.x.x-amd64.deb
    sudo systemctl start kibana
    sudo systemctl enable kibana
```
##Configuring Alerting and Notifications##
Elastic Stack's alerting capabilities allow for setting up rules and notifications for specific events.

#Define Alert Rules#
Go to Management > Alerts and Insights > Alert Rules in Kibana.
Choose Create Rule and select a predefined rule or create a custom rule.
Example: Set a rule for failed login attempts to detect brute-force attacks.

#Set Alert Conditions#
Define the conditions for triggering the alert, such as failed logins exceeding a threshold within a certain timeframe.
Set severity levels (e.g., low, medium, high) based on the risk impact.

#Configure Notification Settings#
Add an action to notify via email, Slack, or webhooks when an alert is triggered.
Example: Configure an email action to notify administrators of high-severity alerts.

#Testing the Alerting and Notification Pipeline#
Sample Data Generation
Generate synthetic events, such as multiple failed logins or abnormal network traffic, to simulate security incidents.
Use Logstash to ingest this data into Elasticsearch.

Trigger Alerts
Observe alert generation based on the conditions set and confirm notifications via configured channels.

#Sample Test Case#
Scenario: Detecting brute-force attacks on user accounts.
Steps:
Simulate repeated failed login attempts.
Verify alert generation and notification via email/Slack.
Confirm alert details in Kibana.

#Conclusion#
This Elastic Stack home lab demonstrates SIEM capabilities with a focus on alerting and notifications, laying the foundation for detecting and responding to threats in a controlled environment.

Note: This project is designed for educational purposes in a lab environment and should not be used in production without further configuration and security hardening.
