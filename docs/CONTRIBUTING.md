i# Contributing to `aichat` (Pure Rust Fork)

🎉 Thank you for considering contributing to this pure Rust fork of `aichat`! 🎉

We welcome contributions of all kinds, from bug reports and documentation improvements to new features and code enhancements. Your help is greatly appreciated in making this project better.

## Code of Conduct

This project and everyone participating in it is governed by the [Rust Code of Conduct](https://www.rust-lang.org/policies/code-of-conduct). By participating, you are expected to uphold this code. Please report unacceptable behavior.

## 🚀 Getting Started: Development Setup

To get your development environment set up, follow these steps:

1.  **Fork the Repository**:
    If you don't have write access, fork [bengtfrost/aichat](https://github.com/bengtfrost/aichat) to your own GitHub account.

2.  **Clone Your Fork**:
    Replace `<your-username>` with your GitHub username.
    ```bash
    git clone https://github.com/<your-username>/aichat.git
    # Or, if you have direct write access:
    # git clone https://github.com/bengtfrost/aichat.git
    cd aichat
    ```

3.  **Ensure Rust is Installed**:
    If you don't have Rust, install it via [rustup](https://rustup.rs/). This project typically uses the latest stable Rust version.

4.  **Build the Project**:
    Compile the project to ensure everything is working correctly.
    ```bash
    cargo build
    ```

## 📝 Contribution Workflow

Here's the general workflow for contributing:

1.  **Create a New Branch**:
    Create a descriptive branch name for your feature or fix.
    ```bash
    # Example: git checkout -b feature/new-regex-optimizer
    # Example: git checkout -b fix/config-parsing-bug
    git checkout -b <branch-type>/<short-description>
    ```

2.  **Implement Your Changes**:
    Write your code, add tests, and update documentation as necessary.

3.  **Format and Lint**:
    Before committing, ensure your code is well-formatted and passes linter checks.
    ```bash
    cargo fmt
    cargo clippy --all-targets --all-features -- -D warnings
    ```

4.  **Run Tests**:
    Make sure all existing tests pass and that you've added new tests for your changes.
    ```bash
    cargo test --all-features
    ```

5.  **Commit Your Changes**:
    Write clear and descriptive commit messages. We encourage following [Conventional Commits](https://www.conventionalcommits.org/) principles.
    ```bash
    # Example: git commit -m "feat: implement faster regex matching for highlights"
    # Example: git commit -m "fix: correct parsing of nested config values"
    git commit -m "<type>: <description of change>"
    ```

6.  **Keep Your Branch Updated (if necessary)**:
    If `main` has been updated while you were working, rebase your branch:
    ```bash
    git fetch origin # Assuming 'origin' points to your fork or the main repo
    git rebase origin/main
    # Resolve any conflicts, then continue
    ```

7.  **Push Your Branch**:
    Push your feature branch to your fork on GitHub.
    ```bash
    # Example: git push -u origin feature/new-regex-optimizer
    git push -u origin <branch-name>
    ```

8.  **Open a Pull Request (PR)**:
    -   Go to the [bengtfrost/aichat repository](https://github.com/bengtfrost/aichat) on GitHub.
    -   GitHub should show a prompt to create a PR from your recently pushed branch.
    -   Alternatively, you can use the GitHub CLI:
        ```bash
        gh pr create --base main --fill
        ```
    -   Ensure your PR description clearly explains the changes and the problem it solves. Link to any relevant issues.

## 📜 Contribution Guidelines

-   **Style**: Follow standard [Rust API Guidelines](https://rust-lang.github.io/api-guidelines/conventions.html) and idiomatic Rust practices. Use `cargo fmt` to ensure consistent formatting.
-   **Commit Messages**: Write descriptive commit messages. Adhering to [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) is highly recommended.
-   **Tests**: Add tests for any new functionality or bug fixes. Ensure all tests pass before submitting a PR.
-   **Documentation**: If you add new features or change existing ones, update relevant documentation (README, code comments, etc.).
-   **Keep PRs Focused**: Try to keep pull requests small and focused on a single issue or feature. This makes them easier to review.
-   **Communication**: If you're planning a large change, it's a good idea to open an issue first to discuss it.

## 🐛 Reporting Bugs or Suggesting Features

-   **Search Existing Issues**: Before creating a new issue, please check if a similar one already exists.
-   **Use Issue Templates**: If available, use the provided issue templates for bug reports or feature requests.
-   **Provide Details**:
    -   For bug reports: Include steps to reproduce, expected behavior, actual behavior, and your environment (OS, `aichat` version, Rust version).
    -   For feature requests: Clearly describe the feature, its use case, and any potential benefits or drawbacks.

Thank you again for your interest in contributing!
