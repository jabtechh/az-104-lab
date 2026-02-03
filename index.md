---
title: Home
permalink: index.html
layout: home
nav_order: 1
---

# AZ-104: Microsoft Azure Administrator - Lab Solutions

Welcome to my personal AZ-104 lab solutions repository! This contains my notes, solutions, and screenshots for the Microsoft Azure Administrator certification labs.

## 📚 Quick Links

- [Official Microsoft Lab Instructions](https://microsoftlearning.github.io/AZ-104-MicrosoftAzureAdministrator/)
- [AZ-104 Exam Guide](https://learn.microsoft.com/en-us/credentials/certifications/azure-administrator/)
- [Interactive Lab Simulations](https://mslabs.cloudguides.com/guides/AZ-104%20Exam%20Guide%20-%20Microsoft%20Azure%20Administrator)

## 🗂️ Lab Solutions

| Lab | Topic | Solution |
| --- | --- | --- |
| Lab 01 | Manage Entra ID Identities | [View Solution](Instructions/Solution/LAB_01-Manage_Entra_ID_Identities-Solution.md) |
| Lab 02a | Manage Subscriptions and RBAC | Coming Soon |
| Lab 02b | Manage Governance via Azure Policy | Coming Soon |
| Lab 03b | Manage Azure Resources by Using ARM Templates | Coming Soon |
| Lab 04 | Implement Virtual Networking | Coming Soon |
| Lab 05 | Implement Intersite Connectivity | Coming Soon |
| Lab 06 | Implement Network Traffic Management | Coming Soon |
| Lab 07 | Manage Azure Storage | Coming Soon |
| Lab 08 | Manage Virtual Machines | Coming Soon |
| Lab 09a | Implement Web Apps | Coming Soon |
| Lab 09b | Implement Azure Container Instances | Coming Soon |
| Lab 09c | Implement Azure Container Apps | Coming Soon |
| Lab 10 | Implement Data Protection | Coming Soon |
| Lab 11 | Implement Monitoring | Coming Soon |

## 📖 Original Lab Instructions

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
| Module | Lab |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

---

> **Note:** This repository is based on the [official Microsoft Learning AZ-104 labs](https://github.com/MicrosoftLearning/AZ-104-MicrosoftAzureAdministrator) with my personal solutions added.
