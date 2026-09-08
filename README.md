# SOL Companion Updates

Public read-only distribution channel for accepted SOL Companion Android releases.

This repository intentionally contains no SOL source, credentials, LAN endpoints, ADB configuration, or remote-control authority. Android package signing remains the final update-compatibility boundary.

Clients should read `latest.json`, require `accepted: true`, verify package/version/digest/signing identity, download the named APK over HTTPS, and hand installation to Android's normal PackageInstaller flow.
