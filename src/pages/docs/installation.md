---
title: Installation
description: Quidem magni aut exercitationem maxime rerum eos.
---

The installation method for different terminal platforms will not be the same, the next will introduce some common platform environment installation steps.

---

## Rust toolchain

Rust is a modern, type sound, and performant programming language that provides a rich feature set for building complex systems. The language also has an active developer community and a growing ecosystem of sharable libraries called crates.

## Learning Rust

Rust is the core language used to build Substrate-based blockchains, so if you intend to do Substrate development, you need to be familiar with the Rust programming language, compiler, and toolchain management.
If you are just getting started with Rust, you should bookmark The Rust Programming Language and refer to other Learn Rust resources on the Rust website to guide you. However, there are a few important points to be aware of as you prepare your development environment.

## About the Rust toolchain

The core tools in the Rust toolchain are the rustc compiler, the cargo build and package manager, and the rustup toolchain manager. At any given point in time, there can multiple versions of Rust available. For example, there are release channels for stable, beta, and nightly builds. You use the rustup program to manage the builds available in your environment and the versions of the toolchain programs that are used with different Rust builds.
The rustc compiler enables you to build binaries for different architectures, referred to as targets. Targets are identified by a string that specifies the kind of output the compiler should produce. This feature is important because Substrate is compiled to both a native Rust binary and a WebAssembly target.
WebAssembly is a portable binary format that can be executed on any modern computer hardware and through any browser accessing the internet. The WebAssembly (Wasm) target enables Substrate to produce portable blockchain runtimes. For more information about how these binaries are used, see Build process.

---


## Linux

### Linux development environment

Rust supports most Linux distributions. Depending on the specific distribution and version of the operating system you use, you might need to add some software dependencies to your environment. In general, your development environment should include a linker or C-compatible compiler such as clang and an appropriate integrated development environment (IDE).

### Before you begin

Check the documentation for your operating system for information about the packages that are installed and how to download and install any additional packages you might need. For example, if you use Ubuntu, you can use the Ubuntu Advanced Packaging Tool (apt) to install the build-essential package:


```shell
sudo apt install build-essential
```

At a minimum, you need the following packages before you install Rust:

```shell
clang curl git make
```

Because the blockchain requires standard cryptography to support the generation of public/private key pairs and the validation of transaction signatures, you must also have a package that provides cryptography, such as libssl-dev or openssl-devel.


### Install required packages and Rust

Install required packages and Rust
To install the Rust toolchain on Linux:

1. Log on to your computer and open a terminal shell.
2. Check the packages you have installed on the local computer by running an appropriate package management command for your Linux distribution.
3. Add any package dependencies you are missing to your local development environment by running an appropriate package management command for your Linux distribution.
   For example, on Ubuntu Desktop or Ubuntu Server, you might run a command similar to the following:
```shell
sudo apt install --assume-yes git clang curl libssl-dev
```
Click the tab titles to see examples for other Linux operating systems:
DebianArchFedoraOpensuse
```shell
sudo apt install --assume-yes git clang curl libssl-dev llvm libudev-dev make protobuf-compiler
```
Remember that different distributions might use different package managers and bundle packages in different ways. For example, depending on your installation selections, Ubuntu Desktop and Ubuntu Server might have different packages and different requirements. However, the packages listed in the command-line examples are applicable for many common Linux distributions, including Debian, Linux Mint, MX Linux, and Elementary OS.
4. Download the rustup installation program and use it to install Rust by running the following command:
```shell
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
5. Follow the prompts displayed to proceed with a default installation.
6. Update your current shell to include Cargo by running the following command:
```shell
source $HOME/.cargo/env
```
7. Verify your installation by running the following command:
```shell
rustc --version
```
8. Configure the Rust toolchain to default to the latest stable version by running the following commands:
```shell
rustup default stable
rustup update
```
9. Add the nightly release and the nightly WebAssembly (wasm) targets to your development environment by running the following commands:
```shell
rustup update nightly
rustup target add wasm32-unknown-unknown --toolchain nightly
```
10. Verify the configuration of your development environment by running the following command:
```shell
rustup show
rustup +nightly show
```
The command displays output similar to the following:
```shell
# rustup show

active toolchain
----------------

stable-x86_64-unknown-linux-gnu (default)
rustc 1.62.1 (e092d0b6b 2022-07-16)

# rustup +nightly show

active toolchain
----------------

nightly-x86_64-unknown-linux-gnu (overridden by +toolchain on the command line)
rustc 1.65.0-nightly (34a6cae28 2022-08-09)
```

---
## MacOS

### macOS development environment
You can install Rust and set up a Substrate development environment on Apple macOS computers with either Intel or an Apple M1 processors.

### Before you begin
Before you install Rust and set up your development environment on macOS, verify that your computer meets the following basic requirements:

* Operating system version is 10.7 Lion, or later.
* Processor speed of at least 2Ghz, 3Ghz recommended.
* Memory of at least 8 GB RAM, 16 GB recommended.
* Storage of at 10 GB available space.
* Broadband Internet connection.

### Support for Apple M1
If you have a macOS computer with an Apple M1 ARM system on a chip, you must have Apple Rosetta installed to run the protoc tool during the Rust build process. The Rust toolchain and the target binaries remain native. You can install Rosetta on your macOS computer by opening the Terminal application and running the following command:

```shell
softwareupdate --install-rosetta
```

### Install Homebrew

In most cases, you should use Homebrew to install and manage packages on macOS computers. If you don't already have Homebrew installed on your local computer, you should download and install it before continuing.

To install Homebrew:

1. Open the Terminal application.
2. Download and install Homebrew by running the following command:
```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```
3.Verify Homebrew has been successfully installed by running the following command:
```shell
brew --version
```
The command displays output similar to the following:
```shell
Homebrew 3.3.1
Homebrew/homebrew-core (git revision c6c488fbc0f; last commit 2021-10-30)
Homebrew/homebrew-cask (git revision 66bab33b26; last commit 2021-10-30)
```

### Install required packages and Rust
Because the blockchain requires standard cryptography to support the generation of public/private key pairs and the validation of transaction signatures, you must also have a package that provides cryptography, such as openssl.

To install openssl and the Rust toolchain on macOS:

1. Open the Terminal application.
2. Ensure you have an updated version of Homebrew by running the following command:
```shell
brew update
```
3. Install the openssl package by running the following command:
```shell
brew install openssl
```
4. Download the rustup installation program and use it to install Rust by running the following command:
```shell
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
5. Follow the prompts displayed to proceed with a default installation.
6. Update your current shell to include Cargo by running the following command:
```shell
source ~/.cargo/env
```
7. Verify your installation by running the following command:
```shell
rustc --version
```
8. Configure the Rust toolchain to default to the latest stable version by running the following commands:
```shell
rustup default stable
rustup update
```
9. Add the nightly release and the nightly WebAssembly (wasm) targets to your development environment by running the following commands:
```shell
rustup update nightly
rustup target add wasm32-unknown-unknown --toolchain nightly
```
10. Verify the configuration of your development environment by running the following command:
```shell
rustup show
rustup +nightly show
```
The command displays output similar to the following:
```shell
# rustup show

active toolchain
----------------

stable-x86_64-apple-darwin (default)
rustc 1.61.0 (fe5b13d68 2022-05-18)

# rustup +nightly show

active toolchain
----------------

nightly-x86_64-apple-darwin (overridden by +toolchain on the command line)
rustc 1.63.0-nightly (e71440575 2022-06-02)
```
i.Install cmake using the following command:
```shell
brew install cmake
```
---
## Compile a Web3Games node
Now that you have Rust installed and the Rust toolchains configured for Substrate development, you are ready to finish setting up your development environment by cloning the Web3Games Node files and compiling a Web3Games node.
The node template provides a working environment that includes all of the most common features you need to build a blockchain without any extraneous modules or tools. To ensure that the node template offers a relatively stable working environment for you to experiment with, the recommended best practice is to clone Web3Games node template from the Web3Games Developer Hub repository, rather than from the core Web3Games repository.

To compile the Web3Games node template:

1. Clone the node template repository by running the following command:
```shell
git clone https://github.com/web3gamesofficial/web3games-blockchain.git
```
2. Change to the root of the node template directory by running the following command:
```shell
cd web3games-blockchain
```
3. Compile the node template by running the following command:
```shell
cargo build --release
```
Because of the number of packages required, compiling the node can take several minutes.

After the build completes successfully, your local computer is ready for Web3Games development activity.


