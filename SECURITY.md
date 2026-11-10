# Security Policy

## Supported versions

Security fixes are intended for the latest version on the default branch. This is an early-stage project and does not currently publish a formal support matrix.

## Reporting a vulnerability

Please do not report security vulnerabilities in public issues. If GitHub Private Vulnerability Reporting is enabled for this repository, use the repository's **Security → Report a vulnerability** flow. Otherwise, contact a repository maintainer privately through a verified channel listed on the repository profile.

Do not include live API keys, real customer records, policy documents, driving licences, RC documents, claim files or other sensitive material in a report.

## Security considerations

- The application runs in the user's browser and has no project-operated backend.
- Report and bill history plus letterhead settings are stored in browser `localStorage` and are not encrypted by this application.
- The Anthropic API key is held only in page memory and is used by browser-side API requests. Anyone able to inspect the active page or browser developer tools while the key is entered may be able to access it.
- OCR uploads are transmitted to Anthropic when the user invokes extraction. Users must ensure they have authority to send those documents to the service and must review the provider's current terms and data controls.
- Exported JSON/ZIP backups may contain sensitive claim and personal data. Store and share them securely.
- Do not deploy a shared public instance that asks every visitor to use a maintainer-owned API key. A hosted multi-user deployment needs a properly secured server-side integration, authentication, rate limiting, access controls and an appropriate privacy notice.
- Third-party scripts and fonts are loaded from CDNs. Review and pin dependencies appropriately before production deployment.
