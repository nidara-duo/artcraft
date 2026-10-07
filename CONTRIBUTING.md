# Contributing

Pull requests are welcome from users and ArtCraft developers. You can propose manifest fixes, update package details, or add an application when it has a usable Windows release.

## Manifest requirements

- Use the upstream release version and stable, direct download URLs. Do not guess versions or construct URLs from an unreleased build.
- Include a SHA-256 checksum for every download. Prefer a checksum published by upstream; otherwise calculate it from the release archive.
- Add `checkver` and `autoupdate` only when the upstream release tags and asset names follow a predictable pattern. Document any exception in the manifest's `notes` field.
- Keep architecture-specific URLs, checksums, and extraction directories in sync.
- Do not add a manifest for a planned application without an installable release asset.

## Before opening a pull request

Run the bucket checks locally if Scoop is installed:

```powershell
.\bin\test.ps1
```

For a manifest change, also check its update rule:

```powershell
.\bin\checkver.ps1 <manifest>
```

`checkver -Update` may download release archives to calculate checksums. The scheduled GitHub Actions workflow runs on GitHub-hosted infrastructure and commits upstream version changes to the default branch. CI must pass before a pull request is merged.
