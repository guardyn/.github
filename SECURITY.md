# Security Policy

## 🔒 Our Commitment

Security is at the core of everything we do at Guardyn. As a privacy-focused E2EE messaging platform, we take security vulnerabilities seriously and appreciate the security community's efforts to help keep our users safe.

## 🛡️ Supported Versions

We provide security updates for the following versions:

| Version | Supported          |
| ------- | ------------------ |
| main    | ✅ Active development |
| Latest release | ✅ Fully supported |
| Previous release | ⚠️ Critical fixes only |
| Older releases | ❌ No longer supported |

## 🔍 Scope

### In Scope

Security vulnerabilities in the following areas are in scope:

- **Cryptographic implementations**: Key generation, encryption, decryption, signing
- **Authentication and authorization**: User authentication, session management, access control
- **E2EE protocol**: Signal Protocol implementation, key exchange, forward secrecy
- **API security**: Input validation, injection attacks, API abuse
- **Infrastructure**: Kubernetes configurations, container security, network policies
- **Data protection**: Data at rest, data in transit, key storage
- **Dependencies**: Third-party library vulnerabilities
- **Client-side security**: XSS, CSRF, client-side cryptography

### Out of Scope

The following are generally out of scope:

- Social engineering attacks
- Physical security
- Denial of Service (DoS/DDoS) without demonstrated impact
- Issues in unsupported versions
- Issues requiring unlikely user interaction
- Rate limiting issues (unless leading to abuse)
- Theoretical attacks without proof of concept

## 📢 Reporting a Vulnerability

**Please do not report security vulnerabilities through public GitHub issues.**

### How to Report

Send vulnerability reports to: **security@guardyn.io**

Include the following information:

1. **Type of vulnerability** (e.g., RCE, authentication bypass, cryptographic weakness)
2. **Affected component(s)** and version(s)
3. **Step-by-step reproduction instructions**
4. **Proof of concept** (if applicable)
5. **Potential impact** of the vulnerability
6. **Suggested fix** (if you have one)
7. **Your contact information** for follow-up

### PGP Encryption

For highly sensitive disclosures, encrypt your report using our PGP key:

```
-----BEGIN PGP PUBLIC KEY BLOCK-----
[PGP Key will be published here]
-----END PGP PUBLIC KEY BLOCK-----
```

Fingerprint: `[To be added]`

### What to Expect

1. **Acknowledgment**: Within 24 hours of submission
2. **Initial assessment**: Within 3 business days
3. **Regular updates**: At least every 7 days
4. **Coordination**: We'll work with you on disclosure timeline
5. **Credit**: Public acknowledgment in security advisories (if desired)

## 🏆 Responsible Disclosure

We follow a coordinated disclosure process:

1. **Report received**: You report the vulnerability privately
2. **Validation**: We validate and assess the issue (1-7 days)
3. **Fix development**: We develop and test a fix (timeframe varies by severity)
4. **User notification**: We notify affected users if needed
5. **Public disclosure**: We publish a security advisory (typically 90 days after fix)
6. **Recognition**: We credit researchers in the advisory

### Disclosure Timeline

- **Critical vulnerabilities**: Immediate action, disclosure within 7-14 days of patch
- **High severity**: 30 days to patch and disclosure
- **Medium/Low severity**: 60-90 days to patch and disclosure

We may request extended timelines for complex issues and will communicate openly about delays.

## 🎯 Severity Classification

We use CVSS 3.1 scoring with the following categories:

### Critical (9.0-10.0)
- Remote code execution
- Complete authentication bypass
- Cryptographic key compromise
- **Response time**: Immediate (< 24 hours)

### High (7.0-8.9)
- Privilege escalation
- SQL injection
- Sensitive data exposure
- **Response time**: < 48 hours

### Medium (4.0-6.9)
- Cross-site scripting (XSS)
- CSRF vulnerabilities
- Information disclosure
- **Response time**: < 1 week

### Low (0.1-3.9)
- Minor information leaks
- Non-security-impacting bugs
- **Response time**: Best effort

## 🎁 Recognition

We believe in recognizing security researchers who help us improve:

### Hall of Fame

Security researchers who responsibly disclose vulnerabilities will be:

- Listed in our Security Hall of Fame
- Credited in security advisories (with permission)
- Acknowledged in release notes

### Bug Bounty Program

We are planning to launch a bug bounty program. Details will be announced here when available.

## 🔐 Security Best Practices

### For Contributors

When contributing to Guardyn:

- ✅ Use `cargo audit` to check dependencies
- ✅ Run `cargo clippy` and address security warnings
- ✅ Never commit secrets, keys, or credentials
- ✅ Use secure random number generation (`OsRng`)
- ✅ Clear sensitive data from memory (`zeroize`)
- ✅ Validate and sanitize all inputs
- ✅ Use constant-time comparisons for secrets
- ✅ Follow least-privilege principles

### For Users

To stay secure:

- ✅ Keep Guardyn updated to the latest version
- ✅ Verify authenticity of releases (check signatures)
- ✅ Use strong, unique passwords
- ✅ Enable two-factor authentication where available
- ✅ Verify safety numbers for E2EE contacts
- ✅ Report suspicious activity

## 🔄 Security Updates

### Notification Channels

Stay informed about security updates:

- **GitHub Security Advisories**: Watch the repository
- **Mailing list**: security-announce@guardyn.io (planned)
- **RSS feed**: GitHub releases
- **Website**: https://guardyn.io/security (planned)

### Update Policy

- **Critical patches**: Released immediately
- **Security updates**: Backported to supported versions
- **Automated updates**: Recommended for production deployments

## 📚 Security Resources

### Documentation

- [Threat Model](docs/threat-model.md) (planned)
- [Security Architecture](docs/security-architecture.md) (planned)
- [Cryptography Design](docs/cryptography.md) (planned)

### Security Audits

We conduct regular security audits and will publish results:

- **Last audit**: Planned for 2025
- **Next audit**: TBD
- **Audit reports**: Will be published at [guardyn.io/audits] (planned)

## 🙏 Thank You

We deeply appreciate the security community's efforts to keep Guardyn and our users safe. Your responsible disclosure helps us maintain the highest security standards.

### Past Contributors

(Security researchers who have helped will be listed here with permission)

---

**Remember**: Security is a shared responsibility. If you see something, say something. Together, we can build more secure communications infrastructure.
