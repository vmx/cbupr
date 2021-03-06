
#UPR Project

UPR stands for "Universal Protocol for Replication" and the purpose of this project is to revamp the replication so that it can be used by all modules in the Couchbase ecosystem as well as third party applications.

###UPR High-level Details

* [UPR Overview](https://docs.google.com/document/d/1a774bZyKszX6q0HQvvMsYVRZmn29d8NHGNjP1DBOXCM/edit)
* [Transport Protocol Specification](tansport-spec.md)

###Use Cases

#####VBucket Move

A cluster rebalance is made up of multiple VBucket moves. Below are links to the current (2.x) and future (3.x) procedures.

* [VBucket Move (2.x)](https://github.com/couchbaselabs/ep-engine-designs/blob/master/architecture/vbucket-move.md)
* [Vbucket Move (3.x)](vbucket-move.md)

#####Indexing

In future versions of Couchbase indexing will no longer read from disk and instead get there data from an UPR replication stream. Below are links to the current (2.x) and future (3.x) strategy.

* [Indexing (2.x)](https://github.com/couchbaselabs/ep-engine-designs/blob/master/architecture/indexing.md)
* [Indexing (3.x)](https://docs.google.com/document/d/1_FAsprUf_N8cMI3NXqw5PWW3RakAHM7lMgpFFAyoD7w)

#####XDCR

XDCR currently reads items from disk in order to replicate them accross wide area networks. Future versions will stream data directly to the XDCR replicators via an UPR stream. Below are links to the current (2.x) and future (3.x) strategy.

* [XDCR (3.x)](https://docs.google.com/document/d/1Mh6VuZVkmvxg567h0fDLGOJNzQ4O5XSde1MzUuZ42LI)

#####Consistent Views

A major feature that has been asked for by customers is the ability to support consistent views. This means that when a user does a "set" command they can immediately query the view and expect to see the data that was set in the view. Below are links to the current (2.x) and future (3.x) plan.

* [Consistent Views (3.x)](ryow.md)

#####Third-Party

The current tap implementation is too difficult to use and laks the features needed to build third-party applications. Below are links to use cases for how UPR can be used to succesfully build new applications.

* Streaming all data from a cluster
* [Using filters on a tap stream](https://docs.google.com/document/d/1K6RGIxVMygQNUwu3fSn3HiSTSHL_iISxTN6fiZYVn5U)

#####Backwards Compatibility

we need to support upgrades from 2.x to 3.x. The link below describes how the upgrade process will work.

* [Upgrade (2.x) to (3.x)](https://docs.google.com/document/d/1GmSSGx-cmZNoNyX_83g2rydYDAtdJid2ryTzTu4c6eI)


###Implementation Designs

#####EP-Engine

* [Mutation Queues](mutation_queues.md)
* Replicator