# Veyra desktop updates

Official Windows x64 release channel for Veyra, published by ImpressionsDirect360.

[Download the latest Veyra installer](https://github.com/ImpressionsDirect360/veyra-updates/releases/latest) · [Signed update feed](https://github.com/ImpressionsDirect360/veyra-updates/releases/latest/download/release.json)

## Automatic updates

Veyra checks its configured release channel 20 seconds after startup and every six hours while running. It downloads a newer stable release in the background and installs it after a normal browser exit. It does not force an active browsing session to close. Open Veyra again to use the installed update. Automatic updates can be paused in About Veyra.

The browser verifies an Ed25519 signature on the release metadata and a SHA-512 digest of the installer before installation. The public verification key is included here; the private signing key is kept offline from this repository. Windows Authenticode signing is not configured.

This repository contains release installers, public metadata and documentation. GitHub's automatically generated source archives contain only this release-channel repository, not the complete browser source. Upstream code, filter data and license notices accompany the installer. See THIRD-PARTY-NOTICES.md.

The update client sends no browsing history, search key, cookies or persistent installation identifier to the release host. GitHub still receives ordinary connection metadata, such as the requesting IP address.

New versions must be built, tested, signed and published by the maintainer. Automatic updates distribute published releases; they do not develop or build new versions.

## Stable channel contract

- Each stable release uses a unique tag such as `v2.6.0`.
- Each release includes `Veyra-Setup-VERSION-x64.exe`, `release.json`, and `SHA256SUMS.txt`.
- The manifest signs the exact versioned HTTPS installer URL, app identity, platform, architecture, size and SHA-512 digest.
- Upload all assets to a draft release, verify them, then publish it as the latest stable release.
- Never replace a published installer. Ship a new, higher patch version for corrections. Clients reject downgrades and invalid signatures.
- Do not put credentials, user profiles or private signing keys in this repository or its release assets.

Free hosting uses GitHub Releases, with no paid workflow or server required. [GitHub's release documentation](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases) describes the release asset limits.
