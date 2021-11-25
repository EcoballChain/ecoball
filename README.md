# Ecoball Node

Ecoball Node is the Official Rust implementation of the Ecoball protocol. It is a fork of OpenEthereum - https://github.com/openethereum/openethereum and EVM compabile.


## Building

### 1. Build Dependencies

Ecoball requires **latest stable Rust version** to build.

We recommend installing Rust through [rustup](https://www.rustup.rs/). If you don't already have `rustup`, you can install it like this:

- Linux:
  ```bash
  $ curl https://sh.rustup.rs -sSf | sh
  ```

  Ecoball also requires `clang` (>= 9.0), `clang++`, `pkg-config`, `file`, `make`, and `cmake` packages to be installed.

- OSX:
  ```bash
  $ curl https://sh.rustup.rs -sSf | sh
  ```

  `clang` is required. It comes with Xcode command line tools or can be installed with homebrew.

- Windows:
  Make sure you have Visual Studio 2015 with C++ support installed. Next, download and run the `rustup` installer from
  https://static.rust-lang.org/rustup/dist/x86_64-pc-windows-msvc/rustup-init.exe, start "VS2015 x64 Native Tools Command Prompt", and use the following command to install and set up the `msvc` toolchain:
  ```bash
  $ rustup default stable-x86_64-pc-windows-msvc
  ```

Once you have `rustup` installed, then you need to install:
* [Perl](https://www.perl.org)
* [Yasm](https://yasm.tortall.net)

Make sure that these binaries are in your `PATH`. After that, you should be able to build Ecoball from source.

### 2. Build from Source Code

```bash
# download Ecoball code
$ git clone https://github.com/ecoball/ecoball
$ cd ecoball

# build in release mode
$ cargo build --release --features final
```

This produces an executable in the `./target/release` subdirectory.

Note: if cargo fails to parse manifest try:

```bash
$ ~/.cargo/bin/cargo build --release
```

Note, when compiling a crate and you receive errors, it's in most cases your outdated version of Rust, or some of your crates have to be recompiled. Cleaning the repository will most likely solve the issue if you are on the latest stable version of Rust, try:

```bash
$ cargo clean
```

This always compiles the latest nightly builds. If you want to build stable, do a

```bash
$ git checkout stable
```

### 3. Starting Ecoball

#### Manually

To start Ecoball manually, just run

```bash
$ ./target/release/ecoball
```

so Ecoball begins syncing the Ecoball blockchain.

## 4. Testing

Download the required test files: `git submodule update --init --recursive`. You can run tests with the following commands:

* **All** packages
  ```
  cargo test --all
  ```

* Specific package
  ```
  cargo test --package <spec>
  ```

You can show your logs in the test output by passing `--nocapture` (i.e. `cargo test --package evmbin -- --nocapture`)

## 5. Documentation

Be sure to [check out our wiki](https://docs.ecoball.org/) for more information.

## 7. Contributing

Guidelines are provided in [CONTRIBUTING](./.github/CONTRIBUTING.md).

### Contributor Code of Conduct

[CODE_OF_CONDUCT](./.github/CODE_OF_CONDUCT.md)

## 8. License

[LICENSE](./LICENSE)

