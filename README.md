# 🦀 aichat (Pure Rust Fork) ⚡

[![Made with Rust](https://img.shields.io/badge/Made%20with-Rust-EA592E?style=for-the-badge&logo=rust)](https://www.rust-lang.org)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg?style=for-the-badge)](LICENSE-APACHE)
[![GitHub Repo stars](https://img.shields.io/github/stars/bengtfrost/aichat?style=for-the-badge&logo=github)](https://github.com/bengtfrost/aichat/stargazers)

> ⚡ A Rust-native fork of [sigoden/aichat](https://github.com/sigoden/aichat), built 100% in safe Rust and replacing `onig_sys` with the pure-Rust `fancy-regex` crate for regex functionality.

This fork prioritizes safety, portability, and a streamlined build process by eliminating C dependencies, offering a truly native Rust experience.

---

## ✨ Highlights

- 🛡️ **Safe & Portable:** Zero C dependencies—no `onig_sys`, only the pure-Rust `fancy-regex`. Enjoy improved memory safety and easier cross-compilation.
- ⚙️ **Easy to Build:** Pure Cargo workflow. Build with a single `cargo build` command on Linux, macOS, or Windows without needing external C toolchains.
- 🚀 **Feature-Complete:** Retains all of AIChat's powerful features: shell assistant, interactive chat-REPL, Retrieval Augmented Generation (RAG), configurable agents, response streaming, and more.

---

## 🚀 Why This Fork?

The upstream AIChat project utilizes `syntect` for syntax highlighting, which in turn relies on `onig_sys` (bindings to the Oniguruma C library). This fork was created to:

1. 🚫 **Eliminate C FFI & Dependencies**: Replaces Oniguruma C bindings with the excellent, pure-Rust [`fancy-regex`](https://crates.io/crates/fancy-regex) engine.
2. 🛠️ **Simplify Build Process**: No more hassles with system C libraries or complex toolchain setups. Just `cargo`!
3. 🔒 **Enhance Memory Safety**: Leverages Rust’s strong memory safety guarantees throughout the entire codebase by removing unsafe C bindings.
4. 🌍 **Improve Portability**: Builds and runs seamlessly on various architectures and environments, including musl-based systems (like Alpine Linux), Windows, WASM (potentially), and containerized setups.

---

## 📦 Installation

### 1. Prebuilt Binaries (Recommended)

Download the latest release for your platform from the [**GitHub Releases**](https://github.com/bengtfrost/aichat/releases) page.

```sh
# Example for Linux amd64
# Adjust <platform> and <version> accordingly
wget https://github.com/bengtfrost/aichat/releases/download/vX.Y.Z/aichat-vX.Y.Z-x86_64-unknown-linux-gnu.tar.gz
tar -xzf aichat-vX.Y.Z-x86_64-unknown-linux-gnu.tar.gz
chmod +x aichat
sudo mv aichat /usr/local/bin/aichat
```

````
### 2. Install via Cargo (from Git)

Ensure you have Rust and Cargo installed. Then:

```sh
cargo install --git https://github.com/bengtfrost/aichat --branch main
```

### 3. Build from Source

```sh
git clone https://github.com/bengtfrost/aichat.git
cd aichat
cargo install --path .
# The binary will be at target/release/aichat or ~/.cargo/bin/aichat
```

---

## 🦀 Powered by Rust

This project is proudly built using the [**Rust programming language**](https://www.rust-lang.org/).

<p align="center">
  <a href="https://www.rust-lang.org" target="_blank" rel="noopener noreferrer">
    <img src="https://www.rust-lang.org/static/images/rust-logo-blk.svg" alt="Rust Logo" width="120" />
  </a>
</p>

Rust's emphasis on safety, speed, and concurrency makes it an excellent choice for developing robust and high-performance command-line applications. By leveraging Rust:

- **Memory Safety:** Compile-time checks prevent common bugs like null pointer dereferences and data races, without a garbage collector.
- **Performance:** Rust provides C-like performance with high-level ergonomics.
- **Modern Tooling:** `cargo`, Rust's build system and package manager, simplifies dependency management and the build process.
- **Ecosystem:** A rich ecosystem of crates (libraries) like `fancy-regex` allows for building complex applications with pure Rust components.

This fork's commitment to 100% safe Rust further amplifies these benefits.

---

## 📂 Project Structure

```
/aichat
├── Cargo.toml         # Project manifest (e.g., version 0.29.0-native)
├── src/               # Rust source code (100% safe Rust)
├── vendor/            # Patched crates (e.g., onig_sys_dummy, onig_dummy for compatibility layers)
├── docs/              # Documentation: build, release, contributing guides
│   ├── BUILD.md       # Detailed build instructions
│   ├── RELEASE.md     # Release process guide
│   └── CONTRIBUTING.md# Contribution guidelines
├── README.md          # This file
├── LICENSE-APACHE     # Apache 2.0 License text
├── .gitignore         # Specifies intentionally untracked files
└── target/            # Build artifacts (not committed to version control)
```

---

## 🛠️ Getting Started & Development

For detailed build instructions, development environment setup, and troubleshooting, please see:
👉 [**docs/BUILD.md**](docs/BUILD.md)

If you'd like to contribute to the project, please read our contribution guidelines:
👉 [**docs/CONTRIBUTING.md**](docs/CONTRIBUTING.md)

---

## 📤 Release & Distribution

The process for bumping versions, tagging releases, and uploading binaries is documented in:
👉 [**docs/RELEASE.md**](docs/RELEASE.md)

---

## 📜 License

This project is licensed under the **Apache License 2.0**.

A copy of the license can be found in the [LICENSE-APACHE](LICENSE-APACHE) file.

```
Copyright [yyyy] [name of copyright owner]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

---

## 🙌 Credits & Acknowledgements

- **Original Project:** A huge thank you to **[@sigoden](https://github.com/sigoden)** for creating the original [sigoden/aichat](https://github.com/sigoden/aichat).
- **This Fork & Maintenance:** [bengtfrost/aichat](https://github.com/bengtfrost/aichat) by **[@bengtfrost](https://github.com/bengtfrost)**.
- **Core Regex Engine:** The [`fancy-regex`](https://crates.io/crates/fancy-regex) crate and its contributors, for providing a pure-Rust regex solution.
- **The Rust Community:** For creating and maintaining such a powerful and productive language and ecosystem.

```
```
````
