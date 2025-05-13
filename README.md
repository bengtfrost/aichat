
# aichat

> ⚡ A Rust-native fork of [sigoden/aichat](https://github.com/sigoden/aichat), replacing the `onig_sys` C dependency with pure-Rust `fancy-regex` for safety, portability, and simplicity.

## ✨ Why this fork?

The original `aichat` is a fantastic CLI for LLM interactions, but it relies on `syntect` + `onig_sys`, which pulls in the Oniguruma C library. This fork eliminates all native C dependencies by using:

* ✅ `fancy-regex` — A Rust-native regex engine
* ✅ Patch to `syntect` to replace `onig`
* ✅ Clean and portable build using only Rust crates

This makes it:

* 🛡 Safer (memory-safe, no FFI)
* 📦 Easier to compile (no external C toolchains needed)
* 💻 Ideal for Linux, macOS, and WASM targets

---

## 📦 Installation

### Option 1: Install Prebuilt Binary

Download the latest binary from [Releases](https://github.com/bengtfrost/aichat/releases):

```sh
chmod +x aichat-linux-x86_64
./aichat
```

### Option 2: Install via Cargo from Git

```sh
cargo install --git https://github.com/bengtfrost/aichat
```

### Option 3: Build from Source

```sh
git clone https://github.com/bengtfrost/aichat
cd aichat
cargo install --path .
```

---

## 🛠 Building & Development

To contribute, you need:

* Rust toolchain (>= 1.70)
* `cargo` CLI
* Optional: `gh` for GitHub releases

### Patch Setup

We patch `syntect` to remove the `onig` dependency:

```toml
[patch.crates-io]
syntect = { path = "vendor/syntect" }
```

See [`docs/building.md`](docs/building.md) for full details.

---

## 🧪 Testing

To verify everything works:

```sh
cargo check
cargo test
```

---

## 📤 Release Process

1. Build release binary:

   ```sh
   cargo build --release
   ```

2. Upload to GitHub Releases:

   ```sh
   gh release create v0.29.1 target/release/aichat --title "aichat v0.29.1" --notes "Rust-native build with fancy-regex"
   ```

See [`docs/release-process.md`](docs/release-process.md).

---

## 🙌 Credits

Original project by [sigoden](https://github.com/sigoden/aichat). Fork and rewrite by [bengtfrost](https://github.com/bengtfrost).

---

## 📄 License

MIT OR Apache-2.0
