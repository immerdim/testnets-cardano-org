---
parent: 2020-05-05_16-12-19_installing-and-running-the-cardano-node
title: Building a node using Nix
description: Nix build - Shelley Haskell testnet
order: 1
external_href: ""
last_updated: 2020-05-05T16:17:15.000Z
---
## Building a node using Nix

[Nix](https://nixos.org/) is a purely functional, cross-platform package manager for Linux and Unix systems. It is the package manager of choice for IOHK's internal development teams, and thus the recommended method for building a Cardano node to run on your machine.

**Note:** The following instructions assume you are using Linux and have curl installed. See the [supported platforms](https://staging-updated-testnets-cardano.netlify.app/en/shelley-haskell/about/supported-platforms/) page for more details about supported platforms for the Shelley Haskell testnet.

1. Download and install the Nix package manager by running the following commands from a terminal:
```shell
curl https://nixos.org/nix/install > install-nix.sh
./install-nix.sh
```
2. Follow the instructions presented as part of the Nix installation process.
1. Once Nix is installed, open a new `nix-shell` session and enter the following commands, which will clone the Cardano node GitHub repository, open the node file directory, build the node itself, and then run it:
```shell
git clone https://github.com/input-output-hk/cardano-node
cd cardano-node
nix-build -A scripts.mainnet.node -o mainnet-node-local
./mainnet-node-local
```

Please be aware that the process of building the node may take some time, possibly several hours.

You should now have a Cardano node running on your machine, connected to the Shelley Haskell testnet.