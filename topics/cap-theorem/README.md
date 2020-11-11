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
before the write is deemed `successful`.

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

### `CP` Database

### `AP` Database

### `CA` Database

## Examples

### MongoDB (`CP`)

### Cassandra (`AP`)

## References

- [CAP Theorem](https://www.ibm.com/cloud/learn/cap-theorem)
