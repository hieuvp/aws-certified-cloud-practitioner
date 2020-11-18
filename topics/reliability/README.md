# Reliability

## Table of Contents

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [High Availability](#high-availability)
  - [ASG Example](#asg-example)
- [Fault Tolerance](#fault-tolerance)
  - [AZ Example](#az-example)
- [References](#references)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## High Availability

A highly available system has resources that cooperate to guarantee essential services.
Engineers design highly available systems aiming to limit downtime with minimal implementation costs.
Designing a system for high availability does not mean
it will prevent an outage or incident from occurring.
It's an effort to reduce the downtime and negative impact to the end user
by restoring essential services when a system, component, or application fails.

### ASG Example

Let's look at how high availability can be configured
in the cloud for Amazon Web Services (AWS) EC2 instances.
AWS has capabilities such as Elastic Load Balancing (ELB) and Auto Scaling Groups (ASGs)
to achieve high availability when running EC2 instances.

- An ELB monitors the health of an EC2 instance and distributes traffic between healthy EC2 instances.
- An ASG is used for managing the number of EC2 instances based on demand.

EC2 instances can be part of an ASG running behind an ELB.
In the event of a failure with one EC2 instance,
the ASG would launch another EC2 instance.
The launching of an EC2 instance is not instantaneous,
but often takes less than a minute.
Most companies are willing to absorb a small amount of downtime
with high availability rather than pay higher costs for providing fault tolerance.

![Source: Amazon Web Services](https://miro.medium.com/max/1104/1*hT2F0oZOfsbq7b4p3OYyag.png)

## Fault Tolerance

A fault tolerant system is a critical system that requires being operational with zero downtime,
while a highly available system can tolerate short interruptions in service.
Both high availability and fault tolerance require the ability to detect failure.
A fault tolerant system typically has significantly higher costs than a highly available system.
The higher costs are due to having physical redundancy added to the system.
Redundancy is achieved by having mirrored components up and running,
so failure of a component will not mean failure of the entire system.

### AZ Example

Let's look at how fault tolerance can be configured in the cloud.
AWS provides services that are available in multiple geographical Regions around the globe.
Each Region has multiple Availability Zones (AZs)
that are connected via redundant ultra low latency networks.

![Source: Amazon Web Services](https://miro.medium.com/max/1680/1*Hlh4_7_sT4VvIjnt9-jQEw.png)

An AZ is one or more data centers that are physically isolated
and can operate independent from another AZ.
This helps to achieve greater fault tolerance and low latency
by giving customers the ability to create redundant applications or databases
and mirror them in one or more AZs in the same Region.
This would prevent loss of operations in the event of a failure in one AZ
because the AZs are connected to each other with private fiber-optic networking
that automatically fails over between AZs without interruption of service.

![A Region consists of Multiple Availability Zones](https://miro.medium.com/max/1267/1*TKRQlgltMq1GNtzFO0UmSg.png)

Below is an architectural diagram showing two AZs in the same Region.
The EC2 instances that are part of an ASG deployed and running
in separate AZs running behind an ELB.
If an outage were to occur in one AZ,
the ELB would distribute traffic to EC2 instances in the other isolated AZ.

![Users](https://miro.medium.com/max/1262/1*m_dQx9nKjZnng9fBD9Cl5g.png)

In addition to replicating a system across multiple AZs in the same Region,
redundancy and fault tolerance can be increased further
by replicating the application, data, or entire system across Regions for global business continuity.

There is a distinction between high availability and fault tolerance.
Just remember, a highly available system has little to no down time
and a fault tolerant system has zero down time
and is typically more complex and costly to implement.
An understanding of the terms help facilitate clear communication
when discussing requirements of a system.

## References

- [What's the Difference Between High Availability and Fault Tolerance?](https://medium.com/@KHuffstetler/whats-the-difference-between-high-availability-and-fault-tolerance-9bea141d8c1f)
- [What is Fault Tolerance and Why It Differs From High Availability](https://www.vxchnge.com/blog/fault-tolerance-vs-high-availability)
