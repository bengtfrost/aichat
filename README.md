## README.md

````markdown
# aichat

> ⚡ A Rust-native fork of [sigoden/aichat](https://github.com/sigoden/aichat), built 100% in safe Rust and replacing `onig_sys` with pure-Rust `fancy-regex` for regex functionality.

**Highlights:**

- 🛡 **Safe & Portable:** Zero C dependencies—no `onig_sys`, only `fancy-regex`.
- ⚙️ **Easy to Build:** Pure Cargo workflow; build with a single command on Linux, macOS, or Windows.
- 🚀 **Feature-Complete:** Retains all AIChat features: shell assistant, chat-REPL, RAG, agents, streaming, and more.

---

## 🚀 Why This Fork?

The upstream AIChat project relies on `syntect` + `onig_sys` (Oniguruma C library) for syntax highlighting. This fork:

1. **Drops C FFI**: Replaces Oniguruma with the pure-Rust [`fancy-regex`](https://crates.io/crates/fancy-regex) engine.
2. **Simplifies Builds**: No need for system C libraries or toolchains; just Rust.
3. **Boosts Safety**: Leverages Rust’s memory safety guarantees.
4. **Enhances Portability**: Works seamlessly on musl-based, Windows, WASM, and container environments.

---

## 📦 Installation

### 1. Prebuilt Binaries (Recommended)

Download the latest release from [GitHub Releases](https://github.com/bengtfrost/aichat/releases) for your platform, then:

```sh
chmod +x aichat-<platform>
sudo mv aichat-<platform> /usr/local/bin/aichat
```
````

### 2. Install via Cargo (Git)

```sh
cargo install --git https://github.com/bengtfrost/aichat --branch main
```

### 3. Build from Source

```sh
git clone https://github.com/bengtfrost/aichat.git
cd aichat
cargo install --path .
```

---

## 🛠 Project Structure

```
/aichat
├── Cargo.toml         # project manifest (0.29.0-native)
├── src/               # Rust source code
├── vendor/            # patched crates (onig_sys_dummy, onig_dummy)
├── docs/              # build, release, contributing guides
│   ├── BUILD.md
│   ├── RELEASE.md
│   └── CONTRIBUTING.md
├── README.md
├── LICENSE-APACHE
├── LICENSE-MIT
├── .gitignore         # ignores target/, binaries, Cargo.lock
└── target/            # build artifacts (not committed)
```

---

## 🛠 Getting Started & Development

See [docs/BUILD.md](docs/BUILD.md) for detailed build instructions, and [docs/CONTRIBUTING.md](docs/CONTRIBUTING.md) for contribution guidelines.

---

## 📤 Release & Distribution

Follow the process in [docs/RELEASE.md](docs/RELEASE.md) to bump versions, tag releases, and upload binaries.

---

## 🙌 Credits & License

- Original: [sigoden/aichat](https://github.com/sigoden/aichat)
- Fork & Maintenance: [bengtfrost/aichat](https://github.com/bengtfrost/aichat)
- License: MIT OR Apache-2.0

````
---

## docs/BUILD.md
```markdown
# Building aichat from Source

## Prerequisites
- Rust & Cargo (stable, >=1.70): `rustup` recommended
- Git 2.x

## Steps

1. **Clone**:
   ```bash
git clone https://github.com/bengtfrost/aichat.git
cd aichat
````

2. **Build**:

   ```bash
   ```

cargo build --release

````
3. **Run**:
   ```bash
./target/release/aichat
````

4. **Install locally** (optional):

   ```bash
   ```

cargo install --path .

```
## Notes
- No C toolchain or system libraries required.
- Uses `fancy-regex` instead of `onig_sys` for regex support.
```

