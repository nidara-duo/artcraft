# artcraft

Scoop bucket for the ArtCraft suite — open-source Rust reimplementations of
Adobe and Microsoft applications, built at
[getartcraft.com](https://getartcraft.com).

## Install

```powershell
scoop bucket add artcraft https://github.com/nidara-duo/artcraft
scoop install artcraft/vectorcraft
```

## Packages

| Manifest      | Version | Architectures   |
| ------------- | ------- | --------------- |
| `vectorcraft` | 0.4.0   | x64, x86, arm64 |
| `effectcraft` | 0.4.0   | x64, x86, arm64 |
| `photocraft`  | 0.3.0   | x64, x86, arm64 |
| `pdfcraft`    | 0.2.1   | x64, x86        |
| `designcraft` | 0.2.1   | x64, x86        |
| `lightcraft`  | 0.2.1   | x64, x86        |
| `filmcraft`   | 0.2.1   | x64, x86        |
| `cadcraft`    | 0.1.0   | x64, x86, arm64 |
| `deckcraft`   | 0.1.0   | x64, x86        |
| `gridcraft`   | 0.1.0   | x64, x86, arm64 |
| `wordcraft`   | 0.1.0   | x64, x86, arm64 |

No published release yet: `soundcraft`.

Manifests package the portable `.zip` builds. The `.msi` builds are per-machine
installers, and Scoop discards everything an installer does besides unpacking
files, so there is nothing to gain from them.

## Autoupdate

`.github/workflows/autoupdate.yml` runs `bin/checkver.ps1 -Update` every six
hours and commits whatever changed straight to the default branch — no pull
requests. Hashes come from the `digest` field GitHub publishes for every release
asset, so nothing is downloaded.

Run it locally:

```powershell
.\bin\checkver.ps1 -Update
```

The workflow declares `permissions: contents: write`, which overrides the
repository's read-only default for `GITHUB_TOKEN`, so no change under
*Settings → Actions* is needed.

`.github/workflows/ci.yml` validates every manifest against the Scoop schema on
push.

## Layout

```
bucket/     one JSON manifest per package
bin/        checkver, formatjson, missing-checkver, test wrappers
```
