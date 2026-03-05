# OXSystemsOS repo signing

This document describes how to enable repository signing for GitHub Pages
publishing.

## 1) Generate a signing key

On a secure machine:

```bash
gpg --full-generate-key
gpg --list-secret-keys --keyid-format LONG
```

Export the private key (ASCII armored):

```bash
gpg --armor --export-secret-keys <KEY_ID>
```

## 2) Configure GitHub secrets

In `devluanpereira/oxsystemsos-repo` add:

- `OX_REPO_GPG_PRIVATE_KEY`: output of `gpg --armor --export-secret-keys`
- `OX_REPO_GPG_KEY_ID`: key id (example: `ABCDEF1234567890`)
- `OX_REPO_GPG_PASSPHRASE`: only if the key uses passphrase protection

## 3) Publish

Push to `main` (or run workflow dispatch). The workflow will:

- rebuild `oxsystemsos.db*` when packages exist
- sign repository database artifacts when secrets are configured

## 4) Client configuration (target state)

After publishing the public key via `oxsystemsos-keyring` package, move clients to:

```ini
[oxsystemsos]
SigLevel = Required DatabaseRequired
Server = https://devluanpereira.github.io/oxsystemsos-repo/$arch
```
