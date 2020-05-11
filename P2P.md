# ![](https://img.shields.io/badge/status-wip-orange.svg?style=flat-square) P2P Network Protocol
## Features

By itself, carrier is a low-level, stateless, concurrent networking library that easily allows you to incorporate fundamental features any modern p2p application needs such as:

1) cryptographic primitives (Ed25519, PoW, AES-256),
2) message serialization/deserialization schemes (byte-order little endian, protobuf, msgpack),
3) network timeout/error management (on dial, on receive message, on send buffer full),
4) network-level atomic operations (receive-then-lock),
5) and NAT traversal support (NAT-PMP, UPnP).

Out of its own low-level constructs, carrier additionally comes bundled with a high-level `protocol` package comprised of a large number of production-ready, high-level protocol building blocks such as:

1) handshake protocol implementations (Elliptic-Curve Diffie Hellman),
2) peer routing/discovery protocol implementations (S/Kademlia),
3) message broadcasting protocol implementations (S/Kademlia),
4) overlay network protocol implementations (S/Kademlia),
5) cryptographic identity schemes (Ed25519 w/ EdDSA signatures),
6) and authenticated encryption schemes (AES-256 GCM AEAD).

## Component
Application layer can define component by themself, which is an interface as follow:
```go
// ComponentInterface is used to proxy callbacks to a particular Component instance.
type ComponentInterface interface {
	// Callback for when the network starts listening for peers.
	Startup(net *Network)
	// Callback for when an incoming message is received. Return true
	// if the Component will intercept messages to be processed.
	Receive(ctx *ComponentContext) error
	// Callback for when the network stops listening for peers.
	Cleanup(net *Network)
	// Callback for when a peer connects to the network.
	PeerConnect(client *PeerClient)
	// Callback for when a peer disconnects from the network.
	PeerDisconnect(client *PeerClient)
}
```
1. When app layer implement the component interface, it can handle message dispatched from ReceiveMessage flow;
2. Component can choose to deal with the message it concerns in Receive Callback.
3. App layer can initial something when Startup(), and clear resource in Cleanup();
4. When a Connection or Disconnection occur, PeerConnect/Disconnect will be called;

## Session establishment
1. Node start Listening with a speciall IP/Port, which will be connectd from outbound. as well, you can setup transport protocol, for example: TCP/UDP/QUIC and so on.
2. Outbound connect to speciall node(IP:Port);
3. Connection will be standed for Client struct, which will be managed in ConnMgr Interface;
4. When remote node disconnect initiatively, or receivd an ERROR message, this node will disconnect;
5. There is only ONE connection between same pair nodes;

## Message&Broadcasting
- P2P by default encodes messages as bytes in little-endian order, and provides utility classes to assist with serializing/deserializing arbitrary Go types into bytes efficiently.
- For each message, there is a `opcode <-> message` pairing must be specified entirely up to the user in code.
- User must registe an opcode for special message as follow:
```go
type Opcode uint32
const (
	UnregisteredCode       Opcode = 0x00000 // 0
	BytesCode              Opcode = 0x00001 // 1
	KeepaliveCode          Opcode = 0x00002 // 2
	KeepaliveResponseCode  Opcode = 0x00003 // 3
	ProxyResponseCode      Opcode = 0x00009 // 9
	PingCode               Opcode = 0x0000a // 10
	PongCode               Opcode = 0x0000b // 11
	LookupNodeRequestCode  Opcode = 0x0000c // 12
	LookupNodeResponseCode Opcode = 0x0000d // 13
	DisconnectCode         Opcode = 0x0000e // 14
	ProxyRequestCode       Opcode = 0x0000f // 15
	MetricRequestCode      Opcode = 0x00010 // 16
	MetricResponseCode     Opcode = 0x00011 // 17
	AckResponseCode        Opcode = 0x00012 // 18

	ApplicationOpCodeStart Opcode = 1000
)
```

## Pair node disconnect
1. When disconnect by remote peer(EOF msg received), or receiving an ERROR message connection will be destoried;
2. Component's callback named Peerdisconnect Will be called foreach compoent in list;
3. Relative resource will be recycled in PeerClose flow;
4. User can rebuild a new connection immediatelly after disconnectiong;
5. When node quit, all connection will be auto to disconnect;
