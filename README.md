# NeutronTech Homebrew tap

Homebrew casks published by NeutronTech.

## Neutron Studio

[Neutron Studio](https://studio.neutrontech.ai/) is an offline AI assistant for
documents and writing on the Mac.

```sh
brew install --cask founder-neutrontech/tap/neutron-studio
```

Requirements: macOS 27 or later on a Mac with Apple silicon.

The cask installs the notarized, Developer ID signed app from
studio.neutrontech.ai. After that, Neutron Studio updates itself through
Sparkle (**Neutron Studio → Check for Updates…**), so the cask is marked
`auto_updates`. `brew upgrade` does not touch it unless you pass `--greedy`
(or `--greedy-auto-updates`):

```sh
brew upgrade --cask --greedy neutron-studio
```

To remove the app and its data:

```sh
brew uninstall --cask --zap neutron-studio
```

`--zap` deletes the app's sandbox container and app group container, which hold
your Neutron Studio library. Without `--zap`, only the app is removed.

## Maintainers

Casks here are rendered and committed by `scripts/publish-update.sh --tap`
in the Neutron Studio repository (see `scripts/PACKAGING.md`, Homebrew). Do not
edit `Casks/neutron-studio.rb` by hand.
