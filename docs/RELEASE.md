# Release Process for aichat

This document outlines the steps to create a new release for the `aichat` project.

## Prerequisites

- Ensure your local `main` branch is up-to-date with the remote repository.
  ```bash
  git checkout main
  git pull origin main
  ```
- Ensure all tests pass and the project is in a stable state.
- You have the [GitHub CLI (`gh`)](https://cli.github.com/) installed and authenticated for creating releases.
- You have `cargo-edit` installed for `cargo set-version`. If not, you can install it via:
  ```bash
  cargo install cargo-edit
  ```

## Release Steps

Follow these steps in order to publish a new version:

### 1. Update Version Number

Update the version in `Cargo.toml` using `cargo-set-version`. Replace `<new-version>` with the desired semantic version (e.g., `0.30.0` or `029.2-native`).

```bash
# Example: cargo set-version 0.30.0
cargo set-version <new-version>

# Stage the changes
git add Cargo.toml Cargo.lock
git commit -m "chore: bump version to v<new-version>"

# Example: git tag -a v0.30.0 -m "Release v0.30.0"
git tag -a v<new-version> -m "Release v<new-version>"

# Push the main branch and all tags
git push origin main --tags

# Clean previous builds
cargo clean

# Build the release binary
cargo build --release

# Prepare the binary for upload.
# Replace <platform>-<arch> with the actual platform and architecture.
# (e.g., aichat-linux-x86_64, aichat-macos-aarch64, aichat-windows-x86_64.exe)
# It's good practice to include the version in the filename for clarity.
cp target/release/aichat aichat-v<new-version>-<platform>-<arch>

# Example for a single Linux binary:
# gh release create v0.30.0 \
#   aichat-v0.30.0-linux-x86_64#"aichat v0.30.0 (Linux x86_64 binary)" \
#   --title "Release v0.30.0" \
#   --notes "This release is a pure-Rust build, replacing onig_sys with fancy-regex. Key updates include..."

gh release create v<new-version> \
  aichat-v<new-version>-<platform>-<arch>#"aichat v<new-version> (<platform>-<arch> binary)" \
  # If you have multiple binaries, add each as a new line argument like the one above:
  # aichat-v<new-version>-<other-platform>-<arch>#"aichat v<new-version> (<other-platform>-<arch> binary)" \
  --title "aichat v<new-version>" \
  --notes "Pure-Rust build replacing onig_sys with fancy-regex. Add detailed release notes here, describing changes, new features, and bug fixes since the last release. You can also link to the changelog if available."
```
