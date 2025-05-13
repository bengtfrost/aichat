# 🦀 aichat

[![Made with Rust](https://img.shields.io/badge/Made%20with-Rust-EA592E?style=for-the-badge&logo=rust)](https://www.rust-lang.org)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg?style=for-the-badge)](LICENSE-APACHE)

> ⚡ A Rust-native fork of [sigoden/aichat](https://github.com/sigoden/aichat), built 100% in safe Rust and replacing `onig_sys` with pure-Rust `fancy-regex` for regex functionality.

This fork prioritizes safety, portability, and a streamlined build process by eliminating C dependencies, offering a truly native Rust experience.

---

## ✨ Highlights

- 🛡️ **Safe & Portable:** Zero C dependencies—no `onig_sys`, only the pure-Rust `fancy-regex`. Enjoy improved memory safety and easier cross-compilation.
- ⚙️ **Easy to Build:** Pure Cargo workflow. Build with a single command on Linux, macOS, or Windows without needing external C toolchains.
- 🚀 **Feature-Complete:** Retains all of AIChat's powerful features: shell assistant, interactive chat-REPL, Retrieval Augmented Generation (RAG), configurable agents, response streaming, and more.

---

## 🚀 Why This Fork?

The upstream AIChat project utilizes `syntect` for syntax highlighting, which historically relied on `onig_sys` (bindings to the Oniguruma C library). This fork was created to:

1. 🚫 **Eliminate C FFI & Dependencies:** Replaces Oniguruma C bindings with the excellent, pure-Rust [`fancy-regex`](https://crates.io/crates/fancy-regex) engine.
2. 🛠️ **Simplify Build Process:** No more hassles with system C libraries or complex toolchain setups. Just `cargo`!
3. 🔒 **Enhance Memory Safety:** Leverages Rust’s strong memory safety guarantees throughout the entire codebase by removing unsafe C bindings.
4. 🌍 **Improve Portability:** Builds and runs seamlessly on various architectures and environments, including musl-based systems (like Alpine Linux), Windows, and containerized setups.

---

## 📦 Installation

### 1. Prebuilt Binaries (Recommended)

Download the latest release for your platform from the [**GitHub Releases**](https://github.com/bengtfrost/aichat/releases) page.

**Example (Linux x86_64):**

```sh
# Replace <version> and <platform-triple> with actual values from releases
# e.g., v0.29.0 and x86_64-unknown-linux-gnu
wget https://github.com/bengtfrost/aichat/releases/download/<version>/aichat-<version>-<platform-triple>.tar.gz
tar -xzf aichat-<version>-<platform-triple>.tar.gz
chmod +x aichat
sudo mv aichat /usr/local/bin/aichat
```

### 2. Install via Cargo (from Git)

Ensure you have the Rust toolchain installed. Then:

```sh
cargo install --git https://github.com/bengtfrost/aichat --branch main
```

### 3. Build from Source

```sh
git clone https://github.com/bengtfrost/aichat.git
cd aichat
cargo install --path .
# The binary will be located at target/release/aichat or typically in ~/.cargo/bin/
```

---

## 📂 Project Structure

/aichat
├── Cargo.toml # Project manifest (e.g., version 0.29.0-native)
├── src/ # Rust source code (100% safe Rust)
├── vendor/ # Patched crates (e.g., onig_sys_dummy, onig_dummy)
├── docs/ # Documentation: build, release, contributing guides
│ ├── BUILD.md # Detailed build instructions
│ ├── RELEASE.md # Release process guide
│ └── CONTRIBUTING.md# Contribution guidelines
├── README.md # This file
├── LICENSE-APACHE # Apache 2.0 License text
├── .gitignore # Specifies intentionally untracked files
└── target/ # Build artifacts (not committed to version control)

---

## 🛠️ Getting Started & Development

For detailed build instructions, development environment setup, and troubleshooting, please see:
👉 [**docs/BUILD.md**](docs/BUILD.md)

If you'd like to contribute to the project, we welcome your help! Please read our contribution guidelines:
👉 [**docs/CONTRIBUTING.md**](docs/CONTRIBUTING.md)

---

## 📤 Release & Distribution

The process for creating new releases, including version bumping, tagging, and uploading binaries, is documented in:
👉 [**docs/RELEASE.md**](docs/RELEASE.md)

---

## 📜 License

This project is licensed under the **Apache License 2.0**.

A copy of the license can be found in the [LICENSE-APACHE](LICENSE-APACHE) file in this repository.

---

## 🙌 Credits & Acknowledgements

- **Original Project:** A huge thank you to **[@sigoden](https://github.com/sigoden)** for creating the original [sigoden/aichat](https://github.com/sigoden/aichat).
- **This Fork & Maintenance:** [bengtfrost/aichat](https://github.com/bengtfrost/aichat) by **[@bengtfrost](https://github.com/bengtfrost)**.
- **Core Regex Engine:** The [`fancy-regex`](https://crates.io/crates/fancy-regex) crate and its contributors, for providing a robust pure-Rust regex solution.
- **The Rust Community:** For creating and maintaining such a powerful and productive language and ecosystem.
