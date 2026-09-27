# iOS Security Toolkit

> A defensive checklist and architecture reference for Swift / SwiftUI projects.

## Objective

Make secure defaults visible during product development.

This lab is not an exploit kit. It is a collection of **defensive engineering questions** that can be applied during design and review.

## Security surfaces

```text
application
├── authentication
├── authorization
├── local storage
├── network transport
├── secrets
├── logs
├── deep links
├── user-generated content
├── privacy permissions
└── destructive actions
```

## Defensive review

### Identity
- Is identity local, remote or federated?
- What establishes trust?
- Can a lost or stolen session be revoked?
- Is account or identity deletion complete?

### Secrets
- Are secrets absent from the repository?
- Are tokens excluded from logs?
- Is sensitive material stored with platform protections?
- Is secret rotation possible?

### Networking
- Are remote responses treated as untrusted?
- Are timeouts handled?
- Is TLS used for internet transport?
- Are retries bounded?

### Data
- Is sensitive data minimized?
- Is retention intentional?
- Can the user delete stored data?
- Are backups and synchronization understood?

### UX
- Are dangerous actions explicit?
- Are security failures understandable?
- Does the UI distinguish offline, unauthenticated and unauthorized states?

## Release gate

```text
[ ] no credentials in source
[ ] privacy usage descriptions reviewed
[ ] destructive flows tested
[ ] offline behavior tested
[ ] authorization boundaries reviewed
[ ] logging reviewed
[ ] dependency surface reviewed
[ ] threat model updated
```

See the full [Security Checklist](../../docs/SECURITY-CHECKLIST.md).