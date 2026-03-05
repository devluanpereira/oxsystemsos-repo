# oxsystemsos-keyring (scaffold)

This folder contains a package scaffold for the OXSystemsOS pacman keyring.
The committed `oxsystemsos.*` files are placeholders and must be replaced.

Before building the package, replace placeholder files with real keyring data:

- `oxsystemsos.gpg`: exported keyring
- `oxsystemsos-trusted`: trusted key fingerprints
- `oxsystemsos-revoked`: revoked key fingerprints (if any)

Suggested flow:

```bash
gpg --export > oxsystemsos.gpg
```

Then curate trusted/revoked fingerprint files and build:

```bash
makepkg -f
```
