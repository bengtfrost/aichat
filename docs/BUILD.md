# Building `aichat` from Source

This guide outlines the steps to build the `aichat` (pure Rust fork) application from its source code.

## Prerequisites

Before you begin, ensure you have the following installed:

-   **Rust & Cargo**: Stable version, >=1.70 is recommended.
    -   The easiest way to install Rust is via [rustup](https://rustup.rs/).
-   **Git**: Version 2.x or later.

No C toolchain or external system libraries are required for this pure Rust version.

## Build Steps

1.  **Clone the Repository**:
    Open your terminal and clone the project:
    ```bash
    git clone https://github.com/bengtfrost/aichat.git
    cd aichat
    ```

2.  **Build the Project**:
    Use Cargo to build the release version of the application:
    ```bash
    cargo build --release
    ```
    This command compiles the project and places the optimized binary in `target/release/aichat`.

3.  **Run the Application (from target directory)**:
    You can run the compiled binary directly from the build output directory:
    ```bash
    ./target/release/aichat --version
    # or to start a chat session:
    # ./target/release/aichat
    ```

4.  **Install Locally (Optional)**:
    If you want to install `aichat` to make it available system-wide from your Cargo binary directory (typically `~/.cargo/bin/`), you can use:
    ```bash
    cargo install --path .
    ```
    Ensure that `~/.cargo/bin` is in your system's `PATH` environment variable for the `aichat` command to be found directly.

## Verification

After building or installing, you can verify that `aichat` is working correctly:

```bash
# If installed locally and ~/.cargo/bin is in your PATH:
aichat --version

# Or, if running directly from the build directory:
# ./target/release/aichat --version
