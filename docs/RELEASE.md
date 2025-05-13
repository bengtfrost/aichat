## docs/RELEASE.md

````markdown
# Release Process for aichat

## 1. Bump Version

```bash
cargo set-version <new-version>
git add Cargo.toml Cargo.lock
git commit -m "chore: bump version to v<new-version>"
```
````

## 2. Tag & Push

```bash
git tag -a v<new-version> -m "Release v<new-version>"
git push origin main --tags
```

## 3. Build Binary

```bash
cargo clean
cargo build --release
cp target/release/aichat aichat-<platform>
```

## 4. Create GitHub Release

```bash
gh release create v<new-version> \
  aichat-<platform>#"aichat v<new-version> (<platform> binary)" \
  --title "aichat v<new-version>" \
  --notes "Pure-Rust build replacing onig_sys with fancy-regex."
```

````

