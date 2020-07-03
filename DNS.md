# ![](https://img.shields.io/badge/status-wip-orange.svg?style=flat-square) DNS-Distributed Name Service
DNS(Distributed Name Service) is a distributed, open source and extensible domain name mapping service based on smart contracts. Gradually change the data storage paths and extension protocols used by the system to words and abbreviations. Map specific service entities such as addresses, paths, id, content, etc. that can be marked in the layer2 network into a set of naming rules to achieve the reachability of the ecological services within the layer2 network.


## Senarios

1. Data sharing path mapping
2. Custom protocol extension
3. Account mapping

Examples
```
dsp://urlformultiservices
```
*dsp*:header

*urlformultiservices*:sharing url

Naming examples
```
Header：     protocol
URL：        link
Name ：      source path
Owner：      owner
Description：name description
BlockHeight：create height
TTL:         Expiration date
```
## Basic Function

 1. Registration service
 2. Management Service
 3. Inquiry service

### Registration service
The registration service is responsible for generating connections according to different registration methods, while storing the name owner, TTL and other content.
Interfaces:

#### url registration
1. Default mode: Use the default protocol and generate url randomly
2. Custom protocol mode: Use custom protocol and generate url randomly
3. Custom url mode: Use the default protocol and attach a custom url
4. Naming mode: both protocol and url are customized

#### header registration
 - Register a new header
 - Each registered header has an expiration date
 - Can't register system reservation header
 - Register the header mainly in the community governance mode

### Management Service
-  Provide services for the transfer, update and deletion of url / header.
-  Management of url / header, which requires name creator or service management account permissions.

Service mode
 1. Transfer: transfer the ownership of the url / header, the account with ownership can update and delete the url / header
 2. Update: update url mapping object path
 3. Delete: delete the url / header. If a header is deleted or expires, all links named by the header cannot be resolved

### Inquiry service
Query the mapping information, owner and TTL stored during header / url registration
