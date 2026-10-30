# Vaulthalla Homebrew Tap (moved)

Vaulthalla's Homebrew casks now live in the Valkyrian Labs tap,
[valkyrianlabs/homebrew-tap](https://github.com/valkyrianlabs/homebrew-tap). Install with the full name; Homebrew taps
`valkyrianlabs/tap` if needed and trusts the cask you name, so there is no `brew tap` or `brew trust` step:

```sh
brew install --cask valkyrianlabs/tap/vaulthalla            # the server
brew install --cask valkyrianlabs/tap/vaulthalla-desktop    # the Desktop app
```

An existing `vaulthalla/tap/vaulthalla` install follows the move on the next `brew update`
(`tap_migrations.json`). This repository stays to keep the `vaulthalla/tap` name.
