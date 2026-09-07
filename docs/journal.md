# Project Journal

This journal documents the implementation of the Linux Home Server & Private Cloud project step by step.

The goal is to record not only the final configuration, but also the commands used, technical decisions, verification steps, problems encountered, and their solutions.

---

## Stage 1 — Repository Initialization

### Objective

Create a public GitHub repository to document the construction and evolution of the home server infrastructure.

### Repository

`linux-home-server-private-cloud`

### Initial setup

The repository was created on GitHub with:

* Public visibility
* README
* MIT License

It was then cloned to the local development machine:

```powershell
git clone <repository-url>
cd linux-home-server-private-cloud
```

### Verification

The local repository connection was verified with:

```powershell
git status
git remote -v
```

Verified state:

* Branch: `main`
* Local branch synchronized with `origin/main`
* Working tree clean
* `origin` configured for fetch and push

### Project workflow

The project will be developed incrementally:

1. Make a small change.
2. Verify that it works.
3. Document the change.
4. Commit it to Git.
5. Push it to GitHub.

### Security rule

Sensitive information must never be committed to the repository.

This includes:

* Passwords
* API tokens
* Private keys
* SSH keys
* Credentials
* Personal data
* Real environment files containing secrets

### Previously completed infrastructure work

Some server configuration was completed before the repository was created.

These steps will be reconstructed and documented later, including:

* Stable local network address configuration
* Existing Docker installation
* Portainer
* AdGuard Home
* Netdata
* Headless remote administration

---

## Stage 2 — Current Server Inventory and Network Configuration

### Objective

Document the current state of the Linux home server before introducing new services or remote cloud access.

### Current Platform

The server currently uses:

- Ubuntu 24.04 LTS
- Docker Engine
- Portainer CE
- AdGuard Home
- Netdata

Docker containers are primarily administered through Portainer. Administrative Docker commands can also be executed with `sudo`.

The regular administrative user is not currently a member of the `docker` group.

### Network Review

The server has both Ethernet and Wi-Fi connectivity.

Ethernet is currently the preferred network path.

Operational network details such as real IP addresses, MAC addresses, routing information, hostnames, and Wi-Fi identifiers are intentionally excluded from the public repository.

### Stable LAN Address

A predictable local IPv4 address is required for reliable SSH administration and access to hosted services.

Ubuntu continues to obtain its network configuration through DHCP.

This was verified with:

```bash
nmcli -g ipv4.method connection show "Conexión cableada 1"
```

Result:

```text
auto
```

A DHCP reservation had previously been configured on the home router. The router associates the server's Ethernet interface with a reserved local IPv4 address, allowing the server to receive the same address while Ubuntu continues using DHCP.

### Security Review

Before enabling Nextcloud or any new Internet-facing service, the existing network exposure will be reviewed.

The review includes:

- Host firewall configuration
- Router exposure and port forwarding
- Docker-published services
- Remote administration interfaces
- IPv4 and IPv6 exposure
- Authentication and access control

No new remote services were enabled during this stage.

### Documentation Added

The following documentation was created:

- `docs/server-inventory.md`
- `docs/network.md`

### Result

The existing server platform and network configuration are now documented without exposing operational infrastructure details in the public repository.