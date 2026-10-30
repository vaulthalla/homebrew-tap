# Vaulthalla Homebrew Tap

Homebrew distribution of [Vaulthalla](https://github.com/valkyrianlabs/vaulthalla-server) for macOS (Apple Silicon).
Linux installs come from the APT repository at `apt.vaulthalla.sh`; nothing here targets Linux.

Install with the full name. Homebrew taps `vaulthalla/tap` if needed and trusts the cask you name, so there is no
separate `brew tap` or `brew trust` step ([Tap trust](https://docs.brew.sh/Tap-Trust)):

```sh
brew install --cask vaulthalla/tap/vaulthalla            # the server
brew install --cask vaulthalla/tap/vaulthalla-desktop    # the Desktop app
```

In a `Brewfile`: `cask "vaulthalla/tap/vaulthalla-desktop", trusted: true`.

## Casks

| Name | For | Source |
|---|---|---|
| `vaulthalla` | Operators. It installs the server's `.pkg`: LaunchDaemons, a `_vaulthalla` service account, the bundled web console. `brew uninstall` / `--zap` map to remove and purge. | [vaulthalla-server](https://github.com/valkyrianlabs/vaulthalla-server) releases |
| `vaulthalla-desktop` | Everyone with a Vaulthalla node. The signed, notarized Desktop app (macOS 27+). It updates itself with Sparkle (`auto_updates`); `--zap` removes the node registry and settings. | [vaulthalla-desktop](https://github.com/valkyrianlabs/vaulthalla-desktop) releases |

Each repository's release workflow renders its cask from a template it owns and commits it here once the GitHub
release exists, so edit the templates there (`tools/macos/pkg/homebrew/vaulthalla.rb.in`,
`tools/release/homebrew/vaulthalla-desktop.rb.in`), not the files in `Casks/`.

Planned: a `vaulthalla-dev` formula for contributors, built from source (HEAD) and run as the user via
`brew services`.

## Layout

- `Casks/`: the casks above.
- `Formula/`: formulae (none yet).
- `.github/workflows/tests.yml`: `brew test-bot` on pull requests and pushes to `main` (macOS only).
- `.github/workflows/publish.yml`: the `brew pr-pull` workflow. It publishes bottles from a labeled PR.
- `.github/workflows/autobump.yml`: the scheduled `brew bump` for livecheck-able items.
