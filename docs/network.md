# Network Configuration

## Stable LAN Address

The home server requires a predictable local network address because several services and administrative tools depend on being able to reach the machine consistently.

## Problem

By default, the server receives its IPv4 address through DHCP.

A DHCP-assigned address may change over time, which could make remote administration and local services harder to reach.

## Decision

Instead of configuring a static IPv4 address directly inside Ubuntu, a DHCP reservation was configured on the home router.

This keeps the server configuration simple while allowing the router to centrally manage the local address assignment.

## Implementation

The server's Ethernet interface obtains its IPv4 configuration automatically through DHCP.

The router was accessed through its local administration interface and a DHCP reservation was created for the server.

The reservation associates the server's network interface with a fixed local IPv4 address.

The router identifies the server using its network interface MAC address and assigns the reserved address whenever the server connects.

Exact router menu names vary between manufacturers and are therefore not included in this documentation.

## Verification

The configuration can be verified on Ubuntu with:

```bash
nmcli -g ipv4.method connection show "Conexión cableada 1"
```

The expected result is:

```text
auto
```

This confirms that Ubuntu continues to use DHCP rather than a manually configured static IPv4 address.

The reserved address remains stable across server reboots and network reconnections.

## Result

The server now has a predictable local network address while continuing to use DHCP.

This provides a stable endpoint for:

- SSH administration
- Portainer
- AdGuard Home
- Netdata
- Future private-cloud services

## Security and Privacy

The following information is intentionally excluded from the public repository:

- Real local IPv4 addresses
- Router management address
- MAC addresses
- Wi-Fi network identifiers
- Router credentials
- Network passwords
- Detailed routing information

Only the configuration method, verification process, and technical decision are documented publicly.