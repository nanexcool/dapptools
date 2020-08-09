# Dapp tools by DappHub [![Chat](https://img.shields.io/badge/community-chat-blue.svg?style=flat-square)](https://dapphub.chat)

Hello!

This repository contains the source code for several Ethereum tools
hand-crafted and maintained by DappHub, along with dependency management, courtesy of Nix.

Contents:

- [Dapp](./src/dapp) - all you need Ethereum development tool. Build, test, debug & deploy solidity contracts.
- [Seth](./src/seth) - Ethereum CLI. Query contracts, send transactions, follow logs, slice & dice data.
- [Hevm](./src/hevm) - Ethereum evaluator. Fully complient Haskell EVM implementation.
- [Ethsign](./src/ethsign) - sign Ethereum transactions from a local keystore.

## Installation

Install Nix if you haven't already:

```sh
# user must be in sudoers
curl -L https://nixos.org/nix/install | sh

# Run this or login again to use Nix
. "$HOME/.nix-profile/etc/profile.d/nix.sh"
```

Then install dapptools:

```
curl https://dapp.tools/install | sh
```

### Installing custom solc versions

You can specify a custom `solc` version to run within `dapp` with `dapp --use
solc:x.y.z test`, but you can also install any supported `solc` "standalone"
(i.e. add it to your `$PATH`) with:

```
nix-env -iA solc-versions.solc_x_y_z \
  -if https://github.com/dapphub/dapptools/tarball/master
```

*(NOTE: if you haven't installed dapptools with the one-line installer, you'll
have to manually pass substituters in the command above, or configure Cachix
manually, to avoid compilation)*

For a list of the supported `solc` versions, check
[`./nix/solc-versions.nix`](./nix/solc-versions.nix).

Versions of `solc` that haven't yet landed in nixpkgs can be found under the
`unreleased` key: `solc-versions.unreleased.solc_x_y_z`.

*(NOTE: not all versions are supported on macOS platforms.)*

### Contributing

Instructions for adding new versions of `solc` can be found at
[`nix/solc-updates.md`](./nix/solc-updates.md)

---
[![built with nix](https://builtwithnix.org/badge.svg)](https://builtwithnix.org)
