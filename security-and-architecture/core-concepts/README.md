# AWS Architecture Core Concepts

## Table of Contents

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Least Privilege Access](#least-privilege-access)
- [Shared Responsibility Model](#shared-responsibility-model)
- [AWS Well-architected Framework](#aws-well-architected-framework)
- [Reliability](#reliability)
- [Common Compliance Standards](#common-compliance-standards)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Least Privilege Access

> When granting permission for a user to access AWS resources,
> you should grant them the minimum permissions needed
> to complete their tasks and no more.

## [Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model)

> **Security** and **Compliance** is a shared responsibility between AWS and the customer.

| **AWS Responsibility**                      | **Customer Responsibility**                                |
| ------------------------------------------- | ---------------------------------------------------------- |
| Access & training for Amazon employees      | Individual access to cloud resources and training          |
| Global data centers and underlying network  | Data security and encryption (both in transit and at rest) |
| Hardware for global infrastructure          | Operating system, network, and firewall configuration      |
| Configuration management for infrastructure | All code deployed onto cloud infrastructure                |
| Patching cloud infrastructure and services  | Patching guest operating system and custom applications    |

## [AWS Well-architected Framework](https://aws.amazon.com/architecture/well-architected)

The Well-architected Framework is a collection of best practices across five key pillars
for how to best create systems that create business value on AWS.

| **Pillar**             | **Description**                                        |
| ---------------------- | ------------------------------------------------------ |
| Operational Excellence | Running and monitoring systems for business value.     |
| Security               | Protecting information and business assets.            |
| Reliability            | Enabling infrastructure to recover from disruptions.   |
| Performance Efficiency | Using resources efficiently to achieve business value. |
| Cost Optimization      | Achieving minimal costs for the desired value.         |

## Reliability

> Everything fails all the time.

Werner Vogels - CTO, Amazon

| **Strategy**      | **Description**                                                                         |
| ----------------- | --------------------------------------------------------------------------------------- |
| Fault Tolerance   | Being able to support the failure of components within your architecture.               |
| High Availability | Keeping your entire solution running the expected manner despite issues that may occur. |

## Common Compliance Standards

| **Compliance**                                                      | **Description**                                                        |
| ------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| PCI-DSS (Payment Card Industry Data Security Standard)              | Compliance standard for processing credit cards.                       |
| HIPAA (Health Insurance Portability and Accountability Act of 1996) | Compliance standard for healthcare data.                               |
| (System and Organization Controls) SOC 1, SOC 2, SOC 2+, SOC 3      | Third-party reviews of operational processes.                          |
| FedRAMP (Federal Risk and Authorization Management Program)         | Standards for US government data handling.                             |
| (International Organization for Standardization) ISO 27018          | Standard for protecting **Personally Identifiable Information** (PII). |
