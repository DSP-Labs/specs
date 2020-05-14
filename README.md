# DSP specs
> This repository contains the specs for the DSP Protocol and associated subsystems.

## Spec badges and lifecycle

We use the following label system to identify the state of each spec:

- ![](https://img.shields.io/badge/status-wip-orange.svg?style=flat-square) - A work-in-progress, possibly to describe an idea before actually committing to a full draft of the spec.
- ![](https://img.shields.io/badge/status-draft-yellow.svg?style=flat-square) - A draft that is ready to review. It should be implementable.
- ![](https://img.shields.io/badge/status-reliable-green.svg?style=flat-square) - A spec that has been adopted (implemented) and can be used as a reference point to learn how the system works.
- ![](https://img.shields.io/badge/status-stable-brightgreen.svg?style=flat-square) - We consider this spec to close to final, it might be improved but the system it specifies should not change fundamentally.
- ![](https://img.shields.io/badge/status-permanent-blue.svg?style=flat-square) - This spec will not change.
- ![](https://img.shields.io/badge/status-deprecated-red.svg?style=flat-square) - This spec is no longer in use.

**The DSP protocol stack is under development and all specs are still `draft`**

## Index

The specs contained in this repository are:

- **DSP Protocol:**
  - [Protocol Architecture Overview](./ARCHITECTURE.md) - the top-level spec and the stack
- **SDK:**
  - [SDK](./SDK.md) - dsp protocol SDK
- **API:**
  - [REST_API](https://github.com/DSP-Labs/docs/blob/master/client/RESTFUL_API.md) - client restful api
  - [REST_API_ERROR](./RESTFUL_API_ERROR.md) - error code used in rest 
- **Network proxy:**
  - [Proxy](./PROXY.md) - proxy for exchange block data
- **Networking layer:**
  - [P2P](./P2P.md) - underlying communication module for the all services
- **Naming systems:**
  - [SCAN](./SCAN.md) - Simple Content Addressing Node
  - [DNS](./DNS.md) - Distributed Name Service
- **FS:**
  - [FS](./FS.md) - underlying module for file storage

## Contributing
Thank you for considering contributing to DSP. We welcome any individuals and organizations on the Internet to participate in this open source project.
