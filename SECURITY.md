# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| main    | :white_check_mark: |
| dev     | :white_check_mark: |
| < main  | :x:                |

## Reporting a Vulnerability

We take the security of Projet Résurgence seriously. If you believe you have found a security vulnerability, please report it to us as described below.

### How to Report

**For non-critical issues:** Open a [Security Report issue](https://github.com/Projet-Resurgence/ProjetResurgence/issues/new?template=security_report.yml) with the `security` label.

**For critical vulnerabilities:** Contact us directly via [Discord](https://discord.projet-resurgence.fr) and message an admin or maintainer.

### What to Include

- Description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if any)
- Your Discord username for follow-up

### What to Expect

- **Acknowledgment**: We will acknowledge receipt of your report within 48 hours
- **Assessment**: We will assess the vulnerability and determine its impact within 7 days
- **Resolution**: We will work on a fix and notify you when it's deployed
- **Disclosure**: We will coordinate public disclosure with you

### Security Best Practices

- **Never commit secrets** — API keys, tokens, passwords must go in `.env` files
- **Use parameterized queries** — Never concatenate user input into SQL
- **Validate all input** — Server-side validation is mandatory
- **Principle of least privilege** — Services should only access what they need
- **Internal URLs only** — Service-to-service communication uses Docker hostnames, not external URLs (Cloudflare challenges block external calls)

### Known Security Architecture

- All admin services (`admin.*`, `docs.*`) are VPN-only (10.8.0.0/24)
- JWT secrets are shared between related services — changing one requires changing the other
- Database access is restricted to backend network services only
- Cloudflare provides WAF protection for all public-facing services
- Let's Encrypt provides automatic TLS certificate management
