# ✨ Contributing Guidelines (Rust Project)

Thank you for your interest in contributing to this Rust project! Your help is greatly appreciated. Please read the following guidelines to get started smoothly.

---

## 📜 Code of Conduct

All contributors are expected to follow our [Code of Conduct](./CODE_OF_CONDUCT.md). Be respectful and constructive in all interactions.

---

## 🚀 How to Contribute

1. **Fork** the repository.
2. **Clone** your fork and create a new branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Make your changes and commit with a clear message:
   ```bash
   git commit -m "feat: describe your change"
   ```
4. Push to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```
5. Open a **Pull Request** (PR) targeting the `main` branch.

---

## 🛠 Development Setup

1. **Install Rust and Cargo**  
   Follow instructions from [https://rustup.rs](https://rustup.rs).

2. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

3. **Build the project**:
   ```bash
   cargo build
   ```

4. **Run tests**:
   ```bash
   cargo test
   ```

5. **Lint and format**:
   ```bash
   cargo fmt --all
   cargo clippy --all --all-targets --all-features -- -D warnings
   ```

> Optional: Use `just` or `make` if a `Justfile` or `Makefile` is provided.

---

## 🔁 Pull Request Process

- Make sure your branch is up to date with `main`.
- Keep changes focused and atomic.
- Ensure that:
  - Code builds (`cargo build`)
  - Tests pass (`cargo test`)
  - Lint checks pass (`cargo clippy`)
  - Code is formatted (`cargo fmt`)
- Include **unit tests** or **integration tests** for new logic.
- Add/update documentation where needed (especially in public APIs).
- Respond to review feedback and check off all GitHub suggestions.

---

## 🎨 Code Style Guide

We follow **Rust community conventions**:
- Use `cargo fmt` to format code.
- Use `cargo clippy` to catch common mistakes.
- Prefer explicitness and clarity over cleverness.
- Use idiomatic `Result<T, E>` and `Option<T>` patterns.
- Document public functions with `///` doc comments.

---

## 🐛 Reporting Bugs

Open an issue with:
- Clear steps to reproduce
- Expected vs. actual behavior
- Stack traces or logs if available
- Your environment (OS, Rust version, etc.)

Run `rustc --version` and include it in your report.

---

## 💡 Suggesting Features

Please include:
- What problem the feature solves
- Why it would benefit the project
- Rough idea of implementation (optional)

If you're unsure, open a discussion or draft PR first.

---

## ✅ Useful Commands

```bash
# Run all tests
cargo test

# Run linter and deny warnings
cargo clippy --all --all-targets --all-features -- -D warnings

# Format code
cargo fmt --all

# Build with debug symbols
cargo build

# Run the binary (adjust if using workspace)
cargo run
```

---

Thanks again for contributing! 🦀💪  
Let us know in [issues](../../issues) or [discussions](../../discussions) if you have any questions.
