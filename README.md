# ArtCraft Scoop bucket

Scoop manifests for ArtCraft's Windows applications.

## Install

```powershell
scoop bucket add artcraft https://github.com/nidara-duo/artcraft
scoop install artcraft/vectorcraft
```

Replace `vectorcraft` with any manifest name listed below.

## Applications

| Manifest | Application |
| --- | --- |
| `designcraft` | Page layout and publishing (InDesign) |
| `effectcraft` | Motion graphics and visual effects (After Effects) |
| `filmcraft` | Video editing (Premiere Pro) |
| `lightcraft` | Photo management and development (Lightroom) |
| `pdfcraft` | PDF editing (Acrobat) |
| `photocraft` | Raster image editing (Photoshop) |
| `vectorcraft` | Vector illustration (Illustrator) |

The manifests track the upstream releases; this table intentionally does not duplicate their versions. Each manifest defines the available Windows architectures and download details.

### Not packaged yet

`wordcraft`, `soundcraft`, `gridcraft`, `deckcraft`, and `cadcraft` do not have manifests in this bucket yet. Add one when there is a usable Windows release with a stable download URL and verifiable checksum.

## Updates

GitHub Actions checks upstream GitHub releases every six hours and commits changed manifests directly to the default branch. Scoop ignores pre-releases in GitHub release checks. The workflow runs on a GitHub-hosted runner and never installs ArtCraft applications on your PC. Scoop uses release digests when available; if an upstream release omits one, `checkver` may download that archive on the runner to calculate its SHA-256. Grant GitHub Actions read and write access so the workflow can push updates.

For a local version check, run:

```powershell
.\bin\checkver.ps1 vectorcraft
```

A local update with `-Update` can download the new release archive to calculate its checksum when upstream does not publish one. Run it only when you want that check and have the bandwidth available:

```powershell
.\bin\checkver.ps1 vectorcraft -Update
```

## Contributing

Pull requests are welcome, including from ArtCraft developers. See [CONTRIBUTING.md](CONTRIBUTING.md) for the manifest requirements and review process. CI checks manifest format and Scoop compatibility on pull requests.

## Repository layout

- `bucket/` — one Scoop JSON manifest per application
- `bin/` — wrappers around Scoop's manifest tools
- `.github/workflows/` — CI and scheduled manifest updates
