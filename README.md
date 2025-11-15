# .github

**Organization profile and community health files for Guardyn**

Guardyn is a privacy-focused secure messaging platform with end-to-end encryption (E2EE), built with Rust for memory safety and deployed on Kubernetes for scalability.

## 📁 Repository Contents

This repository contains organization-wide community health files and workflow templates for all Guardyn repositories:

### Community Health Files

- **[profile/README.md](profile/README.md)** - Organization profile displayed on github.com/guardyn
- **[CONTRIBUTING.md](CONTRIBUTING.md)** - Contributor guidelines for Rust + Kubernetes projects
- **[CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)** - Community standards and behavior expectations
- **[SECURITY.md](SECURITY.md)** - Security vulnerability reporting and disclosure policy
- **[SUPPORT.md](SUPPORT.md)** - Support resources and help channels

### Workflow Templates

Located in `workflow-templates/`, these templates are available when creating new workflows in Guardyn repositories:

- **[rust-ci.yml](workflow-templates/rust-ci.yml)** - Comprehensive Rust CI/CD pipeline with testing, linting, and security audits
- **[k8s-deploy.yml](workflow-templates/k8s-deploy.yml)** - Kubernetes deployment workflow with multi-stage rollouts
- **[security-scan.yml](workflow-templates/security-scan.yml)** - Security scanning with multiple tools (cargo-audit, CodeQL, Trivy, etc.)

### Issue & PR Templates

Located in `.github/ISSUE_TEMPLATE/` and `.github/`:

- **Bug Report** - Structured bug reporting template
- **Feature Request** - Feature proposal template
- **Security Issue** - Non-critical security issue template
- **Documentation** - Documentation improvement template
- **Pull Request Template** - Comprehensive PR checklist

## 🚀 Using These Templates

### For Repository Maintainers

These files are automatically inherited by all repositories in the Guardyn organization that don't have their own versions. To use workflow templates:

1. Go to the Actions tab in any Guardyn repository
2. Click "New workflow"
3. Guardyn templates will appear in the template selection

### For Contributors

Before contributing to any Guardyn project:

1. Read [CONTRIBUTING.md](CONTRIBUTING.md) for development guidelines
2. Review [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for community standards
3. Check [SECURITY.md](SECURITY.md) if reporting security issues
4. Visit [SUPPORT.md](SUPPORT.md) if you need help

## 🔒 Security First

Security is our top priority. All workflow templates include:

- Automated security audits with cargo-audit
- Dependency vulnerability scanning
- CodeQL static analysis
- Container security scanning with Trivy
- Secret scanning with TruffleHog
- SBOM generation

## 🛠️ Technology Stack

Our templates and guidelines are optimized for:

- **Rust** - Memory-safe systems programming
- **Kubernetes** - Container orchestration
- **GitHub Actions** - CI/CD automation
- **Security Tools** - cargo-audit, CodeQL, Trivy, Semgrep

## 📚 Resources

- **Organization Profile**: [github.com/guardyn](https://github.com/guardyn)
- **Discussions**: [GitHub Discussions](https://github.com/orgs/guardyn/discussions) (planned)
- **Security Policy**: [SECURITY.md](SECURITY.md)

## 📄 License

Community health files in this repository are available under [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/) (Public Domain).

Workflow templates are available under Apache-2.0 or MIT license (your choice).

---

*Building secure, private communications infrastructure that respects user privacy.* 🔒
