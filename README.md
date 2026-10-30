# Vaulthalla Homebrew Tap (moved)

Vaulthalla's Homebrew casks now live in the Valkyrian Labs tap,
[valkyrianlabs/homebrew-tap](https://github.com/valkyrianlabs/homebrew-tap). Install with the full name; Homebrew taps
`valkyrianlabs/tap` if needed and trusts the cask you name, so there is no `brew tap` or `brew trust` step:

| Cask | Installs | For |
|---|---|---|
| `valkyrianlabs/tap/vaulthalla` | Server + Desktop | local-first users, the full experience |
| `valkyrianlabs/tap/vaulthalla-desktop` | Desktop only | users of remote vaults |
| `valkyrianlabs/tap/vaulthalla-server` | Server only | headless and self-hosted deployments |

```sh
brew install --cask valkyrianlabs/tap/vaulthalla
```

The `vaulthalla` cask that used to live here installed the server only, so it moves to
`valkyrianlabs/tap/vaulthalla-server` (`tap_migrations.json`). Existing installs follow on the next `brew update`; run
`brew upgrade --cask valkyrianlabs/tap/vaulthalla-server` once so Homebrew trusts it from then on. This repository
stays to keep the `vaulthalla/tap` name.
