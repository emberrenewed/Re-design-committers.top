# Security Policy

## Reporting a vulnerability

Please report security issues privately instead of opening a public issue. Include reproduction steps, affected flows, and the likely impact.

## Areas to review carefully

- GitHub API token handling
- network requests and rate limiting
- generated output and deployment workflows
- dependency updates

## Secret handling

- Never commit credentials, tokens, or populated environment files.
- Rotate exposed credentials immediately.
- Prefer least-privilege GitHub tokens.
