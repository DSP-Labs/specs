# ![](https://img.shields.io/badge/status-wip-orange.svg?style=flat-square) DSP SDK

## General

SDK is a full implementaion for DSP protocol, which can be used to develop DSP apps. SDK contains account management, layer-2 management and task for sharing data management. Apps use account to be identitied in DSP network. Account also be used as a payment channel endpoint. Each data sharing operations organized as a task in SDK. Task can be start, stop, pause and resume at any time. SDK promise this behavior to be handle atomically and make up as a transaction



## Features

1. Account management: create account, deposit, withdraw, login/logout.
2. Layer-2 management: open channel, close channel, deposit channel, withdraw channel, media transfer.
3. Task management: create tasks, start tasks, stop tasks, pause tasks, resume tasks.
4. Guarantee redundancy backup, recovery files from broken nodes.
5. P2P message communication between peers.



## Core Modules

1. Account, Assests and Smart Contracts APIs
2. File System APIs
3. Distributed Name Service APIs
4. Payment Channel APIs
5. Task Manage APIs



## Messages



#### Basic Message

```go
message Message {
    string msgId  = 1;
    string syn = 2;
    Header header = 3;
    bytes  data = 4;
    Signature sig = 5;
    Error error = 6;
}
```

basic message data structure



#### File Message

```go

message File {
   string sessionId = 1;
   string hash = 2;  
   repeated string blockHashes = 3;
   int32 operation = 4;
   bytes prefix = 5;
   int32 chunkSize = 6;
   Payment payInfo = 7;
   Tx tx = 8;
   Breakpoint breakpoint = 9;
   uint64 totalBlockCount = 10;
   Chain chainInfo = 11;
   string blocksRoot = 12;
}
```

handshake messga for sharing file.



#### BlockFlights Message

```go
message BlockFlights{
   int64 TimeStamp = 1;
   int32 PaymentId = 2;
   repeated Block blocks = 3;
}
```

batch send blocks between peers



#### Payment Message

```go
message Payment {
    string sender = 1; // payer wallet address
    string receiver = 2; // receiver wallet address
    int32 paymentId = 3; // paymentId
    int32 asset = 4; // asset id
    uint64 unitPrice = 5; // unit price per byte
    uint64 amount = 6; // amount
    string fileHash = 7; // file hash string
    string blockHash = 8; // block hash string
}
```

payment message for sharing data



#### Progress Message

```go
message Progress {
   string id = 1;
   string hash = 2;  
   int32 operation = 3;
   string sender = 4;
   repeated ProgressInfo infos = 5;
}
```

progress for sharing data 

