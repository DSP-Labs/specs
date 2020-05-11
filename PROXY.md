# ![](https://img.shields.io/badge/status-wip-orange.svg?style=flat-square) PROXY Protocol

## General
If the user wants to map the address through proxy, the steps are as follows: 
Firstly, send a proxy request message to the proxy service port; 
After internal processing, proxy will assign a proxy address to the request host; 
When other hosts connect to the proxy address, the data will be forwarded to the request host.and the data from requst host will be forwarded to relative node.

## Message
All message that transfer between Node and Proxy are protobuf type. There are some basic message must be implement, descripted as follow:
- Proxy Request
```go
message ProxyRequest {
    string origin_address = 1;
}
```
When Node want to apply for a PROXY IP, it must to send ProxyRequest to proxy server. If server receive the proxy request, proxy server allocate the IP:Port to node and send ProxyResponse Message back.
- Proxy Response
```go
message ProxyResponse {
    string origin_address = 1;
    string proxy_address = 2;
}
```
In order to keep alive between node and proxy server, there is must be a keepalive message be sent to server each 15s default.
- Keepalive
```go
message Keepalive {
}
```
When a keepalive received, server will send back a response message to node.
- KeepaliveResponse
```go
message KeepaliveResponse {
}
```
Finally, all message will be packed a unified protobuf message as follow, the message will be serialized to byte, stored in Message.message:
```go
message Message {
    bytes message = 1;
    // Sender's address and net key.
    ID sender = 2;
    // Sender's signature of message.
    bytes signature = 3;
    // request_nonce is the request/response ID. Null if ID associated to a message is not a request/response.
    uint64 request_nonce = 4;
    // message_nonce is the sequence ID.
    uint64 message_nonce = 5;
    // reply_flag indicates this is a reply to a request
    bool reply_flag = 6;
    // opcode specifies the message type
    uint32 opcode = 7;
    uint32 netID = 8;
}
```
## Establish connection
1. Proxy server will be start firstly, and Listen on a special IP:PORT, which is known to all node.
2. Node send ProxyRequest protobuf message to the server. If Node has been request once, 
the server will send back the using proxy ip:port, else porxy server will send back a new one.
3. Server sends back ProxyResponse protobuf message to the node, which contains the proxy IP:port allocated by server.
4. Node will send Keepalive message to proxy server each 15s default, 
and the server will send back keepalive response at the same time.
5. The allocated proxy IP:Port will be memoried by proxy server for 180m default. 
That means, if a node disconnect with server and reconnect between 180s, it will get the same proxy ip:port as last time.

## Data transfer
1. Node1 establish connection with proxy server, named Main-Connection-1; 
2. Node2 establish connection with proxy server, named Main-Connection-2;
3. Proxy server start a proxy server listening on allocated ip:port for Node1, named Proxy-Server-1;
4. Proxy server start a proxy server listening on allocated ip:port for Node2, named Proxy-Server-2;
5. When Node1 want to exchange message with Node2, Node1 need to establish a connection with Proxy-Server-2 named connection-3 and Node2 need to establish a connection with Proxy-Server-1 named connection-4;
6. Node1 send message by connection-3 and proxy will transfer the data received from connection-3 to Main-Connection-2;
7. When Node2 send back message, it must use connection-4 and Main-Connection-1, which looks like Node1 send to Node2 in step6;
