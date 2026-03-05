# OXSystemsOS pacman repository

This repository publishes the OXSystemsOS pacman repository over GitHub Pages.

## Layout

- `x86_64/`: architecture directory for packages and repository database files.
- `index.html`: landing page used by GitHub Pages.

## Repository URL

Use this URL in pacman config:

```ini
[oxsystemsos]
SigLevel = Optional TrustAll
Server = https://devluanpereira.github.io/oxsystemsos-repo/$arch
```

Packages and repo DB files can be added under `x86_64/`.
