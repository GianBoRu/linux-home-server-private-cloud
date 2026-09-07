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
