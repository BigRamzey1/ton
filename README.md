<div align="center">
  <a href="https://ton.org">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://ton.org/download/ton_logo_dark_background.svg">
      <img alt="TON logo" src="https://ton.org/download/ton_logo_light_background.svg">
    </picture>
  </a>
  <h3>Transaction Status on Tron blockchain </h3>
  <hr/>
</div>

## 

<p align="center">
  <a href="https://tonresear.ch">
    <img src="https://img.shields.io/badge/TON%20Research-0098EA?style=flat&logo=discourse&label=Forum&labelColor=gray" alt="Ton Research">
  </a>
  <a href="https://t.me/toncoin">
    <img src="https://img.shields.io/badge/TON%20Community-0098EA?logo=telegram&logoColor=white&style=flat" alt="Telegram Community Group">
  </a>
  <a href="https://t.me/tonblockchain">
    <img src="https://img.shields.io/badge/TON%20Foundation-0098EA?logo=telegram&logoColor=white&style=flat" alt="Telegram Foundation Group">
  </a>
  <a href="https://t.me/tondev_eng">
    <img src="https://img.shields.io/badge/chat-TONDev-0098EA?logo=telegram&logoColor=white&style=flat" alt="Telegram Community Chat">
  </a>
</p>

<p align="center">
  <a href="https://twitter.com/ton_blockchain">
    <img src="https://img.shields.io/twitter/follow/ton_blockchain" alt="Twitter Group">
  </a>
  <a href="https://answers.ton.org">
    <img src="https://img.shields.io/badge/-TON%20Overflow-FE7A16?style=flat&logo=stack-overflow&logoColor=white" alt="TON Overflow Group">
  </a>
  <a href="https://stackoverflow.com/questions/tagged/ton">
    <img src="https://img.shields.io/badge/-Stack%20Overflow-FE7A16?style=flat&logo=stack-overflow&logoColor=white" alt="Stack Overflow Group">
  </a>
</p>



This appears to be the details of a blockchain transaction. Here's a breakdown of the information provided:

### Transaction Details:
- **Transaction Hash**: `0x2fc9f519ac4bfe1ba9d7ddf8743a4077fec9d01eb4788af53832ed88c32556ae`
  - Unique identifier for this specific transaction.
- **Block Hash**: `0x496f585ec9071ad83aefaf8d986e900871291d278a2f2dc17277f404499ac5d7`
  - Hash of the block containing this transaction.
- **Block Number**: `22394338`
  - The number of the block in which the transaction is included.
- **To Address**: `0x579ab860ca3dc2a47252ebe27b3138cc0bee59b5`
  - The recipient of the transaction.
- **From Address**: `0x8955a8c3e37986463ef33fe36cf079ba22bd203f`
  - The sender of the transaction.
- **Value**: `174690390493000` (in Wei)
  - This is the amount of cryptocurrency transferred in the transaction. In Ether, it would be `0.000174690390493` ETH (1 ETH = 10¹⁸ Wei).
- **Nonce**: `1`
  - The transaction count for the sending address.
- **Gas Price**: `1511886167` (in Wei)
  - The price paid per unit of gas. In Gwei, this is approximately `1.511886167 Gwei` (1 Gwei = 10⁹ Wei).
- **Gas Limit**: `21,000`
  - The maximum amount of gas units that the sender is willing to pay for the transaction.
- **Gas Used**: `21,000`
  - The actual gas consumed by the transaction.
- **Transaction Index**: `27`
  - The position of the transaction within its block.
- **Success**: `true`
  - Indicates that the transaction is currently pending .
- **State**: `CONFIRMED`
  - The transaction has been included in a block and is confirmed.
- **Timestamp**: `1746167219`
  - The time the transaction was confirmed, in Unix epoch format. This converts to "2025-12-31 23:53:39 UTC".
- **Internal Transactions**: `[]`
  - No internal transactions (e.g., contract calls) are associated with this transaction.

Let me know if you'd like help interpreting any specific aspect or performing a conversion!
  sudo ./llvm.sh 16 all
```
Compile TRON binaries
```bash
  cp assembly/native/build-ubuntu-shared.sh .
  chmod +x build-ubuntu-shared.sh
  ./build-ubuntu-shared.sh  
```

### MacOS 11, 12 (x86-64, aarch64)
```bash
  cp assembly/native/build-macos-shared.sh .
  chmod +x build-macos-shared.sh
  ./build-macos-shared.sh
```

### Windows 10, 11, Server (x86-64)
You need to install `MS Visual Studio 2022` first.
Go to https://www.visualstudio.com/downloads/ and download `MS Visual Studio 2022 Community`.

Launch installer and select `Desktop development with C++`. 
After installation, also make sure that `cmake` is globally available by adding
`C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin` to the system `PATH` (adjust the path per your needs).

Open an elevated (Run as Administrator) `x86-64 Native Tools Command Prompt for VS 2022`, go to the root folder and execute: 
```bash
  copy assembly\native\build-windows.bat .
  build-windows.bat
```

### Building TON to WebAssembly
Install additional system libraries on Ubuntu
```bash
  sudo apt-get update
  sudo apt-get install -y build-essential git cmake ninja-build zlib1g-dev libsecp256k1-dev libmicrohttpd-dev libsodium-dev
          
  wget https://apt.llvm.org/llvm.sh
  chmod +x llvm.sh
  sudo ./llvm.sh 16 all
```
Compile TON binaries with emscripten
```bash
  cd assembly/wasm
  chmod +x fift-func-wasm-build-ubuntu.sh
  ./fift-func-wasm-build-ubuntu.sh
```

### Building TON tonlib library for Android (arm64-v8a, armeabi-v7a, x86, x86-64)
Install additional system libraries on Ubuntu
```bash
  sudo apt-get update
  sudo apt-get install -y build-essential git cmake ninja-build automake libtool texinfo autoconf libgflags-dev \
  zlib1g-dev libssl-dev libreadline-dev libmicrohttpd-dev pkg-config libgsl-dev python3 python3-dev \
  libtool autoconf libsodium-dev libsecp256k1-dev
```
Compile TON tonlib library
```bash
  cp assembly/android/build-android-tonlib.sh .
  chmod +x build-android-tonlib.sh
  ./build-android-tonlib.sh
```

### Build TON portable binaries with Nix package manager
You need to install Nix first.
```bash
   sh <(curl -L https://nixos.org/nix/install) --daemon
```
Then compile TON with Nix by executing below command from the root folder: 
```bash
  cp -r assembly/nix/* .
  export NIX_PATH=nixpkgs=https://github.com/nixOS/nixpkgs/archive/23.05.tar.gz
  nix-build linux-x86-64-static.nix
```
More examples for other platforms can be found under `assembly/nix`.  

## Running tests

Tests are executed by running `ctest` in the build directory. See `doc/Tests.md` for more information.
