# artcraft

Scoop bucket for the ArtCraft suite — https://getartcraft.com

## Install

```powershell
scoop bucket add artcraft https://github.com/nidara-duo/artcraft
scoop install artcraft/vectorcraft
```

## Packages

| Manifest      | Architectures   |
| ------------- | --------------- |
| `vectorcraft` | x64, x86, arm64 |
| `effectcraft` | x64, x86, arm64 |
| `photocraft`  | x64, x86, arm64 |
| `cadcraft`    | x64, x86, arm64 |
| `gridcraft`   | x64, x86, arm64 |
| `wordcraft`   | x64, x86, arm64 |
| `pdfcraft`    | x64, x86        |
| `designcraft` | x64, x86        |
| `lightcraft`  | x64, x86        |
| `filmcraft`   | x64, x86        |
| `deckcraft`   | x64, x86        |

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
