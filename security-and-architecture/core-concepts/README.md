# AWS Architecture Core Concepts

## Table of Contents

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Least Privilege Access](#least-privilege-access)
- [Shared Responsibility Model](#shared-responsibility-model)
- [AWS Well-architected Framework](#aws-well-architected-framework)
  - [Operational Excellence](#operational-excellence)
  - [Security](#security)
  - [Reliability](#reliability)
  - [Performance Efficiency](#performance-efficiency)
  - [Cost Optimization](#cost-optimization)
- [Common Compliance Standards](#common-compliance-standards)
  - [PCI-DSS](#pci-dss)
  - [HIPAA](#hipaa)
  - [SOC 1, SOC 2, SOC 3](#soc-1-soc-2-soc-3)
  - [FedRAMP](#fedramp)
  - [ISO 27018](#iso-27018)
- [References](#references)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Least Privilege Access

> When granting permission for a user to access AWS resources,
> you should grant them the minimum permissions needed
> to complete their tasks and no more.

## Shared Responsibility Model

> **Security** and **Compliance** is a shared responsibility between AWS and the customer.

| **AWS Responsibility**                      | **Customer Responsibility**                                |
| ------------------------------------------- | ---------------------------------------------------------- |
| Access & training for Amazon employees      | Individual access to cloud resources and training          |
| Global data centers and underlying network  | Data security and encryption (both in transit and at rest) |
| Hardware for global infrastructure          | Operating system, network, and firewall configuration      |
| Configuration management for infrastructure | All code deployed onto cloud infrastructure                |
| Patching cloud infrastructure and services  | Patching guest operating system and custom applications    |

## [AWS Well-architected Framework](https://aws.amazon.com/architecture/well-architected)

The Well-architected Framework is a collection of best practices across give key pillars
for how to best create systems that create business value on AWS.

### Operational Excellence

> Running and monitoring systems for business value.

### Security

> Protecting information and business assets.

### Reliability

> Enabling infrastructure to recover from disruptions.

### Performance Efficiency

> Using resources efficiently to achieve business value.

### Cost Optimization

> Achieving minimal costs for the desired value.

## Common Compliance Standards

### PCI-DSS

Compliance standard for processing credit cards.

### HIPAA

Compliance standard for healthcare data.

### SOC 1, SOC 2, SOC 3

Third-party reviews of operational processes.

### FedRAMP

Standards for US government data handling.

### ISO 27018

Standard for handling **Personally Identifiable Information** (PII).

## References
