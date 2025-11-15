# Contributing to Guardyn

Thank you for your interest in contributing to Guardyn! We're building privacy-respecting, secure communications infrastructure, and we welcome contributions from developers, security researchers, and privacy advocates.

## 🔒 Security First

Before contributing, please familiarize yourself with our [Security Policy](SECURITY.md). If you discover a security vulnerability, **do not** open a public issue. Instead, follow our responsible disclosure process.

## 🎯 Ways to Contribute

### Code Contributions
- Implement new features
- Fix bugs
- Improve performance
- Enhance documentation
- Write tests

### Security Contributions
- Security audits and reviews
- Penetration testing
- Cryptographic analysis
- Dependency vulnerability reports

### Documentation
- Improve README files
- Write tutorials and guides
- Translate documentation
- Create diagrams and architecture docs

## 🛠️ Development Setup

### Prerequisites

For Rust projects:
```bash
# Install Rust toolchain
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
rustup update stable

# Install development tools
cargo install cargo-audit cargo-deny cargo-outdated
```

For Kubernetes projects:
```bash
# Install kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

# Install kind or minikube for local testing
brew install kind
# or
brew install minikube
```

### Project Setup

1. **Fork the repository** to your GitHub account
2. **Clone your fork**:
   ```bash
   git clone https://github.com/YOUR_USERNAME/REPO_NAME.git
   cd REPO_NAME
   ```
3. **Add upstream remote**:
   ```bash
   git remote add upstream https://github.com/guardyn/REPO_NAME.git
   ```

### Rust Development Workflow

```bash
# Build the project
cargo build

# Run tests
cargo test

# Run with all features
cargo test --all-features

# Check code without building
cargo check

# Format code
cargo fmt

# Lint code
cargo clippy -- -D warnings

# Security audit
cargo audit

# Check for outdated dependencies
cargo outdated
```

### Kubernetes Development Workflow

```bash
# Validate manifests
kubectl apply --dry-run=client -f k8s/

# Lint with kubeval or kubeconform
kubeval k8s/*.yaml

# Deploy to local cluster
kubectl apply -f k8s/

# Test deployments
kubectl get pods -w
kubectl logs -f deployment/guardyn-server
```

## 📝 Commit Guidelines

We follow [Conventional Commits](https://www.conventionalcommits.org/) for clear and structured commit history:

### Commit Message Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types
- **feat**: New feature
- **fix**: Bug fix
- **docs**: Documentation changes
- **style**: Code style changes (formatting, no logic change)
- **refactor**: Code refactoring
- **perf**: Performance improvements
- **test**: Adding or updating tests
- **chore**: Build process or auxiliary tool changes
- **security**: Security improvements or fixes

### Examples

```
feat(crypto): implement X3DH key agreement protocol

Add support for X3DH (Extended Triple Diffie-Hellman) key agreement
to establish shared secrets with forward secrecy.

Closes #123
```

```
security(server): fix potential timing attack in authentication

Use constant-time comparison for token validation to prevent
timing-based side-channel attacks.

CVE-XXXX-XXXXX
```

## 🔍 Code Review Process

1. **Create a pull request** with a clear description
2. **Link related issues** using "Fixes #123" or "Closes #123"
3. **Ensure CI passes**:
   - All tests pass
   - Code is formatted (`cargo fmt`)
   - No clippy warnings (`cargo clippy`)
   - Security audit passes (`cargo audit`)
4. **Address review feedback** promptly
5. **Squash commits** if requested (we typically squash on merge)

## ✅ Pull Request Checklist

Before submitting a PR, ensure:

- [ ] Code follows Rust style guidelines (run `cargo fmt`)
- [ ] All tests pass (`cargo test --all-features`)
- [ ] No clippy warnings (`cargo clippy -- -D warnings`)
- [ ] Security audit passes (`cargo audit`)
- [ ] Documentation is updated (if applicable)
- [ ] Commit messages follow conventional commits
- [ ] PR description clearly explains the changes
- [ ] Related issues are linked
- [ ] No sensitive data (keys, tokens, credentials) in commits

## 🧪 Testing Requirements

### Unit Tests
- Write unit tests for all new functions
- Aim for >80% code coverage
- Test edge cases and error conditions

### Integration Tests
- Add integration tests for API endpoints
- Test E2EE message flows end-to-end
- Verify cryptographic operations

### Security Tests
- Test authentication and authorization
- Verify input validation and sanitization
- Test for common vulnerabilities (injection, XSS, CSRF)

### Example Test Structure
```rust
#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn test_encrypt_decrypt_roundtrip() {
        let plaintext = b"secret message";
        let key = generate_key();
        
        let ciphertext = encrypt(&key, plaintext).unwrap();
        let decrypted = decrypt(&key, &ciphertext).unwrap();
        
        assert_eq!(plaintext, decrypted.as_slice());
    }

    #[test]
    fn test_invalid_key_fails() {
        let ciphertext = b"encrypted data";
        let wrong_key = generate_key();
        
        let result = decrypt(&wrong_key, ciphertext);
        assert!(result.is_err());
    }
}
```

## 📋 Code Style

### Rust Style
- Follow the [Rust API Guidelines](https://rust-lang.github.io/api-guidelines/)
- Use `cargo fmt` with default settings
- Address all `cargo clippy` warnings
- Prefer explicit error handling over `.unwrap()`
- Document public APIs with doc comments

### Example
```rust
/// Encrypts a message using AES-256-GCM.
///
/// # Arguments
/// * `key` - 256-bit encryption key
/// * `plaintext` - Message to encrypt
///
/// # Returns
/// Encrypted ciphertext with authentication tag
///
/// # Errors
/// Returns `CryptoError` if encryption fails
pub fn encrypt(key: &[u8; 32], plaintext: &[u8]) -> Result<Vec<u8>, CryptoError> {
    // Implementation
}
```

## 🏗️ Architecture Guidelines

### Security Principles
1. **Defense in Depth**: Multiple layers of security controls
2. **Least Privilege**: Minimal permissions and access
3. **Fail Secure**: System fails to a secure state
4. **Zero Trust**: Verify everything, trust nothing

### Rust Best Practices
- Use strong typing for security-critical values
- Leverage the type system to prevent misuse
- Avoid unsafe code unless absolutely necessary (document why)
- Use secure random number generation (`rand::rngs::OsRng`)
- Clear sensitive data from memory (`zeroize` crate)

### Kubernetes Best Practices
- Follow least-privilege RBAC
- Use network policies for pod isolation
- Implement resource limits and requests
- Use secrets management (not ConfigMaps for sensitive data)
- Enable Pod Security Standards

## 🤝 Community Guidelines

- Be respectful and inclusive
- Follow our [Code of Conduct](CODE_OF_CONDUCT.md)
- Help others learn and grow
- Provide constructive feedback
- Celebrate successes together

## 📞 Getting Help

- **Discussions**: Ask questions in GitHub Discussions
- **Issues**: Report bugs or request features
- **Security**: Follow our [Security Policy](SECURITY.md) for vulnerabilities
- **Support**: See [SUPPORT.md](SUPPORT.md) for help resources

## 📄 License

By contributing to Guardyn, you agree that your contributions will be licensed under the same license as the project (typically Apache-2.0 or MIT).

---

Thank you for helping us build secure, private communications for everyone! 🔒
