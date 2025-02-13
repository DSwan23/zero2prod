# Zero 2 Production Project

## CI and Building
### Setup
```cmd
# Additional components required to compute code coverage
rustup component add llvm-tools-preview
cargo install cargo-llvm-cov

# Additional components required for linting, not always included in minimal setups
rustup component add clippy

# Additional components required to add formatting 
rustup component add rustfmt

# Check for security vulnerabilities in our packages using cargo-audit tool
cargo install cargo-audit
```

### Running the CI pipeline (Locally)
```cmd
# Run tests
cargo tests

# Run code coverage
cargo llvm-cov

# Run linting, first is basic second is with failing with any warnings
cargo clippy
cargo clippy -- -D warnings

# Run formatting, first is to do formatting from the console and the second will add it to the pipeline
cargo fmt
cargo fmt -- --check

# Scan for vulnerabilities with cargo-audit
cargo audit
```

