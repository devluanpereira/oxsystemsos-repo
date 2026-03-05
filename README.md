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

## Calamares package

This repository publishes `calamares` for OXSystemsOS live media.

- Manual build trigger: GitHub Actions workflow `Build Calamares Package`
- Output package path: `x86_64/calamares-*.pkg.tar.zst`

## Signing roadmap

This repository supports optional signing in CI via secrets:

- `OX_REPO_GPG_PRIVATE_KEY`: ASCII-armored private key
- `OX_REPO_GPG_KEY_ID`: key ID used for signatures
- `OX_REPO_GPG_PASSPHRASE`: optional passphrase

When configured, CI will produce `.sig` files for database artifacts.
