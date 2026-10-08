# artcraft

Scoop bucket for the ArtCraft suite — https://getartcraft.com

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

Without a published release: `soundcraft`.

## Maintenance

| Command                             | Purpose                              |
| ----------------------------------- | ------------------------------------ |
| `.\bin\checkver.ps1 -Update`        | bump manifests to upstream releases  |
| `.\bin\formatjson.ps1`              | canonical JSON formatting            |
| `.\bin\missing-checkver.ps1`        | manifests without `checkver`         |
| `.\bin\test.ps1`                    | schema and style tests (needs Pester) |

`.github/workflows/autoupdate.yml` runs `checkver -Update` every 6 hours and
commits to `main`. `.github/workflows/ci.yml` validates manifests on push.

```
bucket/   manifests
bin/      wrappers around scoop's own scripts
```
