<a>href=Https://Blockchain.com|Ramzey"</a>
  - The recipient of the transaction.
- **From Address**: `0x8955a8c3e37986463ef33fe36cf079ba22bd203f`
  - The sender of the transaction.
- **Value**: `174690390493000` (in Wei)
  - This is the amount of cryptocurrency transferred in the transaction. In Ether, it would be `0.000174690390493` ETH (1 ETH = 10¹⁸ Wei).
- **Nonce**: `1`
  - The transaction count for the sending address.
- **Gas Price**: `1511886167` (in Wei)
  - The price paid per unit of gas. In Gwei, this is approximately `1.511886167 Gwei` (1 Gwei = 10⁹ Wei).
- **Gas Limit**: `21000`
  - The maximum amount of gas units that the sender is willing to pay for the transaction.
- **Gas Used**: `21000`
  - The actual gas consumed by the transaction.
- **Transaction Index**: `27`
  - The position of the transaction within its block.
- **Success**: `true`
  - Indicates that the transaction was successful.
- **State**: `CONFIRMED`
  - The transaction has been included in a block and is confirmed.
- **Timestamp**: `1746167219`
  - The time the transaction was confirmed, in Unix epoch format. This converts to "2025-12-31 23:53:39 UTC".
- **Internal Transactions**: `[]`
  - No internal transactions (e.g., contract calls) are associated with this transaction.

Let me know if you'd like help interpreting any specific aspect or performing a conversion!
  sudo ./llvm.sh 16 all
```
Compile TON binaries
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
