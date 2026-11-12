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
| `artcraft` | Interactive AI image and video creation IDE |
| `artcraft-launcher` | Launcher for the Craft app suite |
| `cadcraft` | Computer-aided design and drafting (AutoCAD) |
| `craft-anything` | Learn how software works and build your own |
| `deckcraft` | Presentations and slide shows (PowerPoint) |
| `designcraft` | Page layout and publishing (InDesign) |
| `effectcraft` | Motion graphics and visual effects (After Effects) |
| `figcraft` | Interface design and prototyping (Figma) |
| `filmcraft` | Video editing, color and sound (Premiere Pro) |
| `gridcraft` | Spreadsheets and data (Excel) |
| `lightcraft` | Photo library and raw development (Lightroom) |
| `materialcraft` | Node-based material designer |
| `pdfcraft` | PDF editing (Acrobat) |
| `photocraft` | Image editing (Photoshop) |
| `soundcraft` | Recording, editing and mixing audio (Pro Tools) |
| `texturecraft` | 3D texture painting |
| `vectorcraft` | Vector illustration (Illustrator) |
| `wordcraft` | Writing and document design (Word) |

The manifests track the upstream releases; this table intentionally does not duplicate their versions. Each manifest defines the available Windows architectures and download details. All applications ship portable x64 and arm64 builds except `artcraft`, which upstream provides as an x64 installer only.

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
