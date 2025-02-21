# Zero 2 Production Project

In this repository I will be working through the Zero to Production Rust book where I will build an email newsletter 
backend service. This will be done to actively engage with the textbook and actually use the concepts within in the 
pursuit of learning Rust and some actual software project development. 

## Concepts

- Navigate and Leverage Rust's crates ecosystem.
- Structure your application for extensibility and modularity
- Write tests, single units to full-blown integration tests
- Authenticate and Authorize users of the API
- Enforce domain invariants with Rust's type system
- Implement a robust error handling system
- Observe the state of the application using structured logs
- Setup an extensive continuous integration and continuous development pipeline

## User Stories

1. ***As a** blog visitor, **I want to** subscribe to the newsletter, **so that** I can receive email updates when new 
content is published to the blog*
2. ***As the** blog author, **I want to** send an email to my subscribers, **So that** I can notify them when new 
content is published*

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

