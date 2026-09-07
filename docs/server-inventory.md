# Current Server Inventory

## Operating System

- Ubuntu 24.04 LTS (Noble Numbat)
- Linux-based headless server

Exact kernel and patch-level information is intentionally omitted from the public repository.

## Container Platform

- Docker Engine
- Container administration is performed through Portainer or privileged `sudo docker` commands.
- The regular administrative user is currently not a member of the `docker` group.

## Existing Services

The server currently runs:

- AdGuard Home
- Portainer CE
- Netdata

## Network

The server has both Ethernet and Wi-Fi connectivity.

Ethernet is configured as the preferred network path.

Private IP addresses, routing details, hostnames, and infrastructure identifiers are intentionally omitted from the public repository.

## Security

Before enabling remote cloud access, the following areas will be reviewed:

- Host firewall configuration
- Router exposure and port forwarding
- Docker-published services
- Remote administration interfaces
- IPv4 and IPv6 exposure
- Authentication and access control

Detailed operational network information is intentionally excluded from the public repository.