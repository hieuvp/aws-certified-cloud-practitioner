# CAP Theorem

> A distributed system can deliver only two of three desired characteristics:
> **consistency**, **availability**, and **partition tolerance**
> (the `C`, `A` and `P` in `CAP`).

## Table of Contents

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Consistency (`C`)](#consistency-c)
- [Availability (`A`)](#availability-a)
- [Partition Tolerance (`P`)](#partition-tolerance-p)
- [NoSQL Database Types](#nosql-database-types)
  - [`CP` Database](#cp-database)
  - [`AP` Database](#ap-database)
  - [`CA` Database](#ca-database)
- [Examples](#examples)
  - [MongoDB (`CP`)](#mongodb-cp)
  - [Cassandra (`AP`)](#cassandra-ap)
- [References](#references)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Consistency (`C`)

Consistency means that all clients see the same data at the same time,
no matter which node they connect to.
For this to happen, whenever data is written to one node,
it must be instantly forwarded or replicated to all the other nodes in the system
before the write is deemed **successful**.

## Availability (`A`)

Availability means that any client making a request for data gets a response,
even if one or more nodes are down.
Another way to state this,
all working nodes in the distributed system return a valid response for any request,
without exception.

## Partition Tolerance (`P`)

A partition is a communications break within a distributed system,
a lost or temporarily delayed connection between two nodes.
Partition tolerance means that the cluster must continue to work
despite any number of communication breakdowns between nodes in the system.

## NoSQL Database Types

> NoSQL (non-relational) databases are ideal for distributed network applications.
> Unlike their vertically scalable SQL (relational) counterparts,
> NoSQL databases are horizontally scalable and distributed by design,
> they can rapidly scale across a growing network consisting of multiple interconnected nodes.

### `CP` Database

A CP database delivers consistency and partition tolerance at the expense of availability.
When a partition occurs between any two nodes,
the system has to shut down the non-consistent node (i.e., make it unavailable)
until the partition is resolved.

### `AP` Database

An AP database delivers availability and partition tolerance at the expense of consistency.
When a partition occurs, all nodes remain available
but those at the wrong end of a partition might return an older version of data than others.
(When the partition is resolved,
the AP databases typically resync the nodes to repair all inconsistencies in the system).

### `CA` Database

A CA database delivers consistency and availability across all nodes.
It can't do this if there is a partition between any two nodes in the system,
however, and therefore can't deliver fault tolerance.

We listed this type last for a reason, in a distributed system, partitions can't be avoided.
So, while we can discuss a CA distributed database in theory, for all practical purposes,
a CA distributed database can't exist.
However, this doesn't mean you can't have a CA database
for your distributed application if you need one.
Many relational databases, such as PostgreSQL,
deliver consistency and availability and can be deployed to multiple nodes using replication.

## Examples

### MongoDB (`CP`)

MongoDB is a popular NoSQL database management system that stores data as BSON (binary JSON) documents.
It's frequently used for big data and real-time applications running at multiple different locations.
Relative to the CAP theorem, MongoDB is a CP data store,
it resolves network partitions by maintaining consistency,
while compromising on availability.

MongoDB is a single-master system,
each replica set can have only one primary node that receives all the write operations.
All other nodes in the same replica set are secondary nodes
that replicate the primary node's operation log and apply it to their own data set.
By default, clients also read from the primary node,
but they can also specify a read preference that allows them to read from secondary nodes.

When the primary node becomes unavailable,
the secondary node with the most recent operation log will be elected as the new primary node.
Once all the other secondary nodes catch up with the new master,
the cluster becomes available again.
As clients can't make any write requests during this interval,
the data remains consistent across the entire network.

### Cassandra (`AP`)

Apache Cassandra is an open source NoSQL database maintained by the Apache Software Foundation.
It's a wide-column database that lets you store data on a distributed network.
However, unlike MongoDB, Cassandra has a masterless architecture,
and as a result, it has multiple points of failure, rather than a single one.

Relative to the CAP theorem, Cassandra is an AP database,
it delivers availability and partition tolerance but can't deliver consistency all the time.
Because Cassandra doesn't have a master node,
all the nodes must be available continuously.
However, Cassandra provides eventual consistency
by allowing clients to write to any nodes at any time
and reconciling inconsistencies as quickly as possible.

As data only becomes inconsistent in the case of
a network partition and inconsistencies are quickly resolved,
Cassandra offers **repair** functionality to help nodes catch up with their peers.
However, constant availability results in a highly performant system
that might be worth the trade-off in many cases.

## References

- [CAP Theorem](https://www.ibm.com/cloud/learn/cap-theorem)
