# Safe Infrastructure
![Safe Infrastructure Diagram](https://user-images.githubusercontent.com/6909403/231760296-afaa126c-db04-4f62-b996-c53b1d884247.png)

- **Tx Service** is the core of the Safe. It indexes multisig transactions, module transactions, token transfers, collects signatures... There must be **1 Tx Service per Chain**, with different workers, PostgreSQL, Redis and RabbitMQ.
- **Config Service** holds configuration for every Chain (blockexplorer, tx service url, apps enabled, wallets enabled...). **1 instance of the Config Service supports multiple Chains**
- **Client Gateway** provides an API optimized for clients (web ui, android, ios...). **1 instance of the Client Gateway supports multiple Chains**

## Setup

This repository contains the minimum viable local setup for our backend services.
The setup presented here, assumes that only L2 safes will be used. Last stable version will be used for every service, but you can adjust them on `.env`, e.g.:

```bash
CFG_VERSION=v2.26.0
CGW_VERSION=v3.29.0
TXS_VERSION=v4.6.1
UI_VERSION=v1.2.0
```

You can change them to the version you are interested available in [docker-hub](https://hub.docker.com/u/safeglobal) but be aware that not all versions of our services are compatible with each other, so do so **at your own risk.**

- [Guide to run our services locally](running_locally.md)
- [Guide to run our services for production](running_production.md)
