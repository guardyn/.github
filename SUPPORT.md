# Support

Need help with Guardyn? Here's how to get support for our privacy-focused E2EE messaging platform.

## 📚 Documentation

Before asking for help, check our documentation:

- **README files**: Each repository has detailed README with setup instructions
- **API Documentation**: Generated from code comments (cargo doc)
- **Architecture docs**: High-level system design and decisions
- **Wiki**: Community-maintained guides and tutorials (planned)

## 💬 Community Support

### GitHub Discussions

For general questions, ideas, and community discussion:

👉 [GitHub Discussions](https://github.com/orgs/guardyn/discussions) (planned)

**Best for**:
- "How do I...?" questions
- Architecture discussions
- Feature ideas and feedback
- Showing off your integrations

### Real-time Chat

Join our community chat for real-time help:

- **Matrix**: `#guardyn:matrix.org` (planned)
- **Discord**: Coming soon

**Best for**:
- Quick questions
- Community interaction
- Real-time troubleshooting
- Getting to know other users

## 🐛 Bug Reports

Found a bug? Help us fix it!

### Before Reporting

1. **Search existing issues**: Your bug might already be reported
2. **Test on latest version**: The bug might already be fixed
3. **Minimal reproduction**: Create the smallest example that shows the bug

### How to Report

[Create an issue](https://github.com/guardyn/REPO_NAME/issues/new) with:

- **Clear title**: Describe the bug in one line
- **Environment**: OS, Rust version, Guardyn version
- **Steps to reproduce**: Numbered steps to trigger the bug
- **Expected behavior**: What should happen
- **Actual behavior**: What actually happens
- **Logs/errors**: Relevant error messages or logs
- **Screenshots**: If applicable

**Not a security issue?** Report it in the appropriate repository.
**Is it a security issue?** Follow our [Security Policy](SECURITY.md) instead!

## 💡 Feature Requests

Have an idea for a new feature?

### Before Requesting

1. **Check existing issues**: Feature might be planned or discussed
2. **Review roadmap**: See if it aligns with project direction
3. **Consider scope**: Is this a general need or specific to your use case?

### How to Request

[Create an issue](https://github.com/guardyn/REPO_NAME/issues/new) with:

- **Use case**: Why do you need this feature?
- **Proposed solution**: How should it work?
- **Alternatives**: What other solutions did you consider?
- **Impact**: Who benefits from this feature?

## 🔧 Technical Support

### Self-Service

Most issues can be resolved with:

```bash
# Update to latest version
git pull origin main
cargo update
cargo build

# Check for common issues
cargo check
cargo clippy

# Clean rebuild
cargo clean
cargo build

# Run tests to verify setup
cargo test
```

### Kubernetes Issues

For deployment problems:

```bash
# Check pod status
kubectl get pods -n guardyn

# View logs
kubectl logs -f deployment/guardyn-server -n guardyn

# Describe pod for events
kubectl describe pod POD_NAME -n guardyn

# Check resource usage
kubectl top pods -n guardyn
```

### Common Issues

#### Build Failures

**Symptom**: `cargo build` fails
**Solution**:
1. Update Rust: `rustup update`
2. Clean build: `cargo clean && cargo build`
3. Check dependencies: `cargo tree`

#### Test Failures

**Symptom**: `cargo test` fails
**Solution**:
1. Run specific test: `cargo test TEST_NAME -- --nocapture`
2. Check test logs for details
3. Ensure test environment is clean

#### Kubernetes Deployment Issues

**Symptom**: Pods not starting
**Solution**:
1. Check pod events: `kubectl describe pod`
2. View logs: `kubectl logs POD_NAME`
3. Verify secrets and configs exist
4. Check resource limits

## 📧 Direct Support

### For Contributors

If you're contributing code and need guidance:
- Comment on your PR with questions
- Tag relevant maintainers
- Join development discussions

### For Organizations

Enterprise support options (planned):
- Priority bug fixes
- Dedicated support channel
- Custom feature development
- Security consulting

Contact: **enterprise@guardyn.io** (planned)

## 🗺️ Roadmap

See what we're working on:

- [Public Roadmap](https://github.com/orgs/guardyn/projects) (planned)
- [Milestones](https://github.com/guardyn/REPO_NAME/milestones)
- [Release Notes](https://github.com/guardyn/REPO_NAME/releases)

## 🌍 Community Guidelines

When seeking support:

- ✅ Be respectful and patient
- ✅ Search before asking
- ✅ Provide context and details
- ✅ Follow up if you find a solution
- ✅ Help others when you can

Follow our [Code of Conduct](CODE_OF_CONDUCT.md) in all interactions.

## 📖 Learning Resources

### Rust Resources

- [The Rust Book](https://doc.rust-lang.org/book/)
- [Rust by Example](https://doc.rust-lang.org/rust-by-example/)
- [Async Book](https://rust-lang.github.io/async-book/)

### Kubernetes Resources

- [Kubernetes Documentation](https://kubernetes.io/docs/)
- [Kubernetes Patterns](https://k8spatterns.io/)
- [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)

### Cryptography Resources

- [Signal Protocol](https://signal.org/docs/)
- [Cryptography Engineering](https://www.schneier.com/books/cryptography-engineering/)
- [Applied Cryptography](https://www.schneier.com/books/applied-cryptography/)

## 🚫 What We Don't Support

To keep support channels effective, we cannot help with:

- ❌ Modified or forked versions (unless it's your contribution)
- ❌ Unsupported/EOL versions
- ❌ Issues already reported and being tracked
- ❌ Security vulnerabilities (use [Security Policy](SECURITY.md) instead)
- ❌ Third-party integrations not officially supported
- ❌ Generic Rust or Kubernetes help (see learning resources)

## 🙏 Support the Project

If Guardyn is useful to you:

- ⭐ Star our repositories
- 🐛 Report bugs and issues
- 💡 Contribute code or documentation
- 📢 Spread the word about privacy-focused messaging
- 💰 Sponsor development (planned)

## 📬 Contact

- **General inquiries**: hello@guardyn.io (planned)
- **Security issues**: security@guardyn.io (See [SECURITY.md](SECURITY.md))
- **Code of Conduct**: conduct@guardyn.io
- **Enterprise support**: enterprise@guardyn.io (planned)

---

*We're building this together. Thank you for being part of the Guardyn community!* 🔒
