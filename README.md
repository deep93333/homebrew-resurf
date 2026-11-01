# Resurf for Homebrew

Install [Resurf](https://resurf.so/), a personal library for Mac, together with its native `resurf` command:

```sh
brew install --cask deep93333/resurf/resurf
```

Requires macOS 14.3 or later. The same signed and notarized download supports Apple Silicon and Intel Macs.

## Updates

Resurf can update itself. To include apps with their own updater when upgrading through Homebrew:

```sh
brew update
brew upgrade --cask --greedy resurf
```

## Uninstall

```sh
brew uninstall --cask resurf
```

This removes the app and Homebrew's CLI link. Your library and iCloud data remain on your devices. Adding `--zap` also removes the app's preferences, cache, and saved window state; it preserves your library.

## Maintaining the cask

`Casks/resurf.rb` pins a published DMG with its SHA-256 checksum. Its Sparkle livecheck tracks the public release feed:

```sh
brew livecheck --cask deep93333/resurf/resurf
```

After publishing a release, update `version` as `marketing-version,build-number` and `sha256` using the final hosted DMG. Keep the matching download available while the cask points to it. Validate changes with:

```sh
brew style --cask deep93333/resurf/resurf
brew audit --cask --online deep93333/resurf/resurf
```

This is Resurf's own tap, maintained separately from Homebrew's main cask repository.
