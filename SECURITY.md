# SOL Companion update-channel security

This public repository is distribution-only. It must not contain SOL source, credentials, ADB configuration, LAN host/token data, SSH material, or remote mutation APIs.

`latest.json` is the moving pointer to the newest accepted release. `accepted/<version>.json` is the immutable audit record for each promoted release.

A Companion update is permitted only when all of these hold:

1. `schema == 1`, `channel == "accepted"`, and `accepted == true`.
2. Package name is exactly `world.sol.companion`.
3. Signing certificate SHA-256 is exactly `dfa8ec276e8b111a2526217990703aa77e32518c90f8d134254f8e5344376645`.
4. Target versionCode is newer than the installed version.
5. APK URL is under this repository's GitHub Releases path and remains HTTPS through redirects.
6. Downloaded APK SHA-256 matches the accepted manifest.
7. The APK's own package, versionCode, and signing certificate match before installer launch.
8. Android's normal unknown-source and package-install confirmation remains mandatory.

The channel grants no remote command, filesystem, ADB, SSH, SOL-host, or arbitrary URL authority. A compromised channel cannot silently replace an installed Companion with a differently signed APK because Android's package-signing boundary remains in force; Companion additionally rejects digest/package/signer mismatches before invoking PackageInstaller.
