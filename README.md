# 🔐 AWS Cloud Security Monitoring & Threat Detection Pipeline

## 📌 Overview

This project demonstrates a real-time cloud security monitoring pipeline built on AWS to detect and alert on privileged (root-level) activity within an EC2 instance.

It simulates a Security Operations Center (SOC) detection workflow using CloudWatch Logs, metric filters, alarms, and SNS notifications.

---

## 🧱 Architecture

EC2 Instance → CloudWatch Agent → CloudWatch Logs → Metric Filter → CloudWatch Alarm → SNS → Email Alert 🚨

---

## ⚙️ Tech Stack

* AWS EC2 (Amazon Linux 2023)
* AWS CloudWatch (Logs, Metrics, Alarms)
* AWS SNS (Notifications)
* Linux System Logs (`/var/log/messages`)
* IAM Roles

---

## 🔍 Detection Logic

Metric filter used:

```
uid=0
```

This detects:

* Root access
* Privilege escalation (sudo)
* System-level command execution

---

## 🚨 Alerting

* CloudWatch Alarm triggers when:

  * RootActivity > 0
* SNS sends real-time email alerts

---

## 🧪 Testing

Simulated root activity using:

```
sudo logger "ROOT ALERT TEST"
```

---

## 📊 Example Output

* CloudWatch logs show root activity
* Alarm triggered
* Email notification received

---

## 🔐 Security Use Cases

* Privilege escalation detection
* Insider threat monitoring
* Unauthorized root access detection

---

## 🚀 Future Enhancements

* Detect `/etc/shadow` access
* Monitor failed login attempts
* Build CloudWatch dashboard
* Integrate with SIEM tools

---

## 💼 Resume Impact

Built a real-time AWS CloudWatch security monitoring pipeline detecting root-level activity using metric filters and SNS alerts, simulating SOC-based threat detection workflows.
