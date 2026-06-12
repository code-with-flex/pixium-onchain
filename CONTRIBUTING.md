# Contributing to `onchain`

This repo contains the Soroban smart contracts powering Pixium. Contracts are written in Rust using the Soroban SDK.

For general contribution guidelines (branching, commits, code of conduct), see the [org-level contributing guide](https://github.com/Pixium-Org/.github/blob/main/CONTRIBUTING.md).

---

## Prerequisites

```bash
# Install Rust
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Add the wasm32 target
rustup target add wasm32-unknown-unknown

# Install Stellar CLI
cargo install --locked stellar-cli --features opt
```

---

## Setup

```bash
git clone https://github.com/Pixium-Org/onchain.git
cd onchain
cargo build
```

---

## Running Tests

```bash
cargo test
```

---

## Building Contracts

```bash
cargo build --target wasm32-unknown-unknown --release
```

---

## Code Style

All PRs must pass formatting and linting checks:

```bash
cargo fmt
cargo clippy -- -D warnings
```

---

## Deploying to Testnet

```bash
stellar contract deploy \
  --wasm target/wasm32-unknown-unknown/release/<contract>.wasm \
  --network testnet \
  --source <YOUR_ACCOUNT>
```

---

## Submitting a PR

1. Fork the repo and create a branch: `feature/<issue-number>-short-description`
2. Make your changes and ensure tests pass
3. Run `cargo fmt` and `cargo clippy`
4. Open a PR targeting the `dev` branch
5. Fill in the PR template and link the issue

---

## Resources

- [Soroban Documentation](https://soroban.stellar.org/docs)
- [Stellar CLI Reference](https://developers.stellar.org/docs/tools/stellar-cli)
- [Rust Book](https://doc.rust-lang.org/book/)
