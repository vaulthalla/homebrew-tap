# Vaulthalla Homebrew Tap

Homebrew distribution of [Vaulthalla](https://github.com/vaulthalla/server) for macOS (Apple Silicon).
Linux installs come from the APT repository at `apt.vaulthalla.sh`; nothing here targets Linux.

```sh
brew tap vaulthalla/tap
```

## Status

Empty for now. macOS support is being built under the
[macOS initiative](https://github.com/vaulthalla/server/issues/199). The packaging shape is decided in
[#203](https://github.com/vaulthalla/server/issues/203), and the work is tracked in
[#219](https://github.com/vaulthalla/server/issues/219).

Planned:

| Name | Kind | For |
|---|---|---|
| `vaulthalla` | Cask | Operators. It installs the signed, notarized `.pkg`: LaunchDaemons, a `_vaulthalla` service account, the bundled web console. `brew uninstall` / `--zap` map to remove and purge. |
| `vaulthalla-dev` | Formula | Contributors. It builds from source (HEAD) and runs as the user via `brew services`. |

## Layout

- `Casks/`: casks, which wrap the notarized pkg from each GitHub release.
- `Formula/`: formulae.
- `.github/workflows/tests.yml`: `brew test-bot` on pull requests and pushes to `main` (macOS only).
- `.github/workflows/publish.yml`: the `brew pr-pull` workflow. It publishes bottles from a labeled PR.
- `.github/workflows/autobump.yml`: the scheduled `brew bump` for livecheck-able items.

The main repository's `release-macos` job will open a PR here (`brew bump-cask-pr`) after each notarized release.
