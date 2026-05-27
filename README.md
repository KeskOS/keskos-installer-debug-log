# keskos-installer-debug-log

`keskos-installer-debug-log` is a tiny helper package that exposes the Calamares debug log through a launcher and a shell wrapper.

## What this is

This repository builds the package used to inspect the packaged installer log after a failed or suspicious install attempt.

## Role in KeskOS

Installer helper package.

## Package name

```txt
Package: keskos-installer-debug-log
Repo: [keskos]
Architecture: any
```

## What it installs or provides

- Installs `/usr/local/bin/keskos-open-installer-log`.
- Installs the GUI launcher `install-keskos-debug.desktop`.

## Commands and launchers

- `keskos-open-installer-log` opens `${XDG_CACHE_HOME:-$HOME/.cache}/keskos/calamares-installer.log` in Konsole/less when available.
- GUI launcher installed: `install-keskos-debug.desktop`.

## Config, logs, and state

- This package reads the installer log at `${XDG_CACHE_HOME:-$HOME/.cache}/keskos/calamares-installer.log`.
- No systemd units are shipped by the package.

## Dependencies

- Runtime dependency: `konsole`.
- Optdepends: `keskos-calamares-branding` because that package creates the installer log this viewer expects.
- Build with `makepkg -s --noconfirm`.

## Build

```bash
makepkg -s --noconfirm
```

## Packaging notes

- Keep this package small and focused on log access only.
- It complements, but should not duplicate, the installer package itself.

## Troubleshooting

- If no log opens, confirm `keskos-calamares-branding` created `${XDG_CACHE_HOME:-$HOME/.cache}/keskos/calamares-installer.log` during the failed install attempt.

## Docs website export notes

- Docs site usage: installer-log recovery note and launcher reference.
