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

