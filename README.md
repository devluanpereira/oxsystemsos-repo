# OXSystemsOS pacman repository

This repository publishes the OXSystemsOS pacman repository over GitHub Pages.

## Layout

- `x86_64/`: architecture directory for packages and repository database files.
- `index.html`: landing page used by GitHub Pages.

## Repository URL

Use this URL in pacman config:

```ini
[oxsystemsos]
SigLevel = Optional DatabaseOptional
Server = https://devluanpereira.github.io/oxsystemsos-repo/$arch
```

Packages and repo DB files can be added under `x86_64/`.

## Installer packages

This repository publishes two installer packages:

- `calamares`: installer runtime used by OXSystemsOS live media.
- `oxsystemsos-calamares-config`: OXSystemsOS branding/runtime config
  (`/etc/calamares/*`), fully decoupled from the ISO source tree.

- Manual/automatic build: GitHub Actions workflow `Build Installer Packages`
- Output package paths:
  - `x86_64/calamares-*.pkg.tar.zst`
  - `x86_64/oxsystemsos-calamares-config-*.pkg.tar.zst`

## Signing roadmap

This repository supports optional signing in CI via secrets:

- `OX_REPO_GPG_PRIVATE_KEY`: ASCII-armored private key
- `OX_REPO_GPG_KEY_ID`: key ID used for signatures
- `OX_REPO_GPG_PASSPHRASE`: optional passphrase

When configured, CI will produce `.sig` files for database artifacts.
