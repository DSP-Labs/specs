# ![](https://img.shields.io/badge/status-wip-orange.svg?style=flat-square) DSP Architecture Overview
**Abstract**

This spec document defines the DSP protocol stack, the interfaces, and how it all fits together. This is meant as a top-level view of the protocol and how the system fits together.

 As a first pass to understanding what is DSP, please refer to the [DSP introduction](https://github.com/DSP-Labs/dsp/raw/master/DSP.pdf).

**Fs**
- File block management
- Storage business: including file upload storage, copy between nodes, shared data, delete and other operations.
- Content management: file access rights, including downloadable account lists, private / restricted / shared, etc.
- Data maintenance: When some storage nodes are abnormal, the new nodes are backed up, and integrity commitments are regularly generated.
- Account & Transaction: An account transaction system connected to the main chain, used to manage its own asset pledge, unlock, transfer, establish micro payment channels, etc.

**Scan**
- Node discovery: As the seed node of the chain network, it receives the handshake information of the online node and forwards the information of other nodes to the new online node, which is applicable to all nodes.
- Block synchronization: Bootstrap nodes need to synchronize blocks to facilitate access nodes to synchronize faster, and are used for DNS contract query services.
Path conversion: Convert customized short paths to tracker or other service (such as domain name) addresses.
- Service discovery: The service in the custom container is registered with bootstrap when it starts, and the client program can query the corresponding server address by a specific id.

**Layer2**
- Payment channel: Tiny high-speed payment layer between nodes

**Proxy**
- Address proxying: Assign a proxy address to the request host
- Data exchage Forward data to the request host, and the data from requst host will be forwarded to relative node.

**Client**
- Account management: user account management, pledge / unlock, import and export.
- Layer2-sdk: Share data blocks through a sharing protocol.
- Fs-SDK: storage protocol SDK.

**P2p** 
- P2P communication: the underlying communication module for the above services.