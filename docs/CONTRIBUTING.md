## docs/CONTRIBUTING.md

```markdown
# Contributing to aichat

## 🚀 Setup
```bash
...
```markdown
# Contributing to aichat

## Setup
```bash
git clone https://github.com/bengtfrost/aichat.git
cd aichat
cargo build
``` 

## Workflow
1. Create branch: `git checkout -b feature/your-feature`
2. Implement changes, then: `cargo fmt && cargo clippy && cargo test`
3. Commit: `git commit -m "feat: description of change"`
4. Push: `git push -u origin feature/your-feature`
5. Open PR via GitHub CLI: `gh pr create` 

## Guidelines
- Follow Rust style conventions
- Write descriptive commit messages
- Sync with upstream before merging: `git fetch upstream && git rebase upstream/main`
- Add tests for new functionality

## Code of Conduct
Please follow our [Code of Conduct](https://www.rust-lang.org/policies/code-of-conduct).
````

