# SCAN-Simple Content Addressing Node
Scan node is a full node in the DSP network, with distributed DNS service and tiny high-speed payment channel capabilities, it mainly provides two functions
1) Provide resource addressing services for dsp network, including node wallet address-identity、 filehash-torrent mapping and retriving services. And achieve consistent network data synchronization as much as possible;
2) As a payment routing node, to ensure the payment routing access of the dsp network;

## Node Mechanism Principles
1. Scan nodes network is considered to be a small-world network (close-connected) with a number of orders of less than one hundred. Joining the network requires mutual authentication, relying on cryptographic identity rather than IP or other identities as the authentication condition.
2. For the database update and message processing system of hundreds of nodes in the P2P environment in the authentication system, each node uses the same algorithm (if not, see principle 3) to execute and get the same result. Able to handle a certain flow peak.
3. Scan nodes can freely choose their trusted nodes for connection and synchronization within the authentication system. If there are spoofing and data errors, the challenger finds that the nodes will receive economic reduction penalties. Need to design necessary contracts based on challenge/response model, increase economic mechanism with protection against spoofing, and introduce other roles such as verifier、challenger, etc.

## Basic Function

1. Service discovery
2. Data synchronization
3. Content addressing

### Service discovery
The service in the custom container is registered with bootstrap when it starts, and the client program can query the corresponding server address by a specific network id in a p2p environment. 

You can enhance your security on which people identified by their public key you know and trust. It tries to build a environment-of-trust automatically.


### Data synchronization

*Message*
```
message Torrent {
    bytes infoHash = 1;
    uint64 left = 2;
    bytes peerinfo = 3;
    int32 type = 4;
}

message Endpoint {
    string walletAddr = 1;
    string hostPort = 2;
    int32 type = 3;
}
```

Scan node provide p2p interaction interface to do complete torrent、query torrent peers、endpoint regist and query.

The scan node network sync message data with other nodes in their trusted environment.


### Content addressing
see [DNS spec](./DNS.md).
