# Security Engineering Checklist

## Repository hygiene

- [ ] No passwords, API keys, tokens, certificates or private keys committed
- [ ] .gitignore covers local build artifacts and secret files
- [ ] Public documentation contains no private infrastructure details
- [ ] Dependencies are intentional and reviewed

## Authentication and authorization

- [ ] Authentication and authorization are separate concepts
- [ ] Privileged actions require explicit authorization
- [ ] Session expiration and revocation are defined
- [ ] Account / identity deletion behavior is documented

## Cryptography

- [ ] Platform or widely vetted primitives are used
- [ ] No custom encryption algorithm
- [ ] Key lifecycle is defined
- [ ] Nonce / IV requirements are satisfied
- [ ] Integrity / authenticity is verified
- [ ] Sensitive values are never written to logs

## Storage

- [ ] Sensitive data is minimized
- [ ] Protection class / secure storage choice is intentional
- [ ] Cached data has a retention policy
- [ ] Destructive deletion is tested

## Networking

- [ ] TLS is used for internet-facing APIs
- [ ] Responses are validated
- [ ] Timeouts are explicit
- [ ] Retries are bounded
- [ ] Offline and degraded states are supported
- [ ] P2P discovery does not automatically confer trust

## Input handling

- [ ] External data is treated as untrusted
- [ ] Decoding failures are handled safely
- [ ] Size limits exist where needed
- [ ] URLs / deep links are validated before use

## Privacy

- [ ] Collection is minimized
- [ ] User-facing permissions match actual behavior
- [ ] Analytics and third-party SDKs are documented
- [ ] Privacy policy matches the shipped version

## Release

- [ ] Threat model reviewed
- [ ] Debug logging reviewed
- [ ] Test credentials removed
- [ ] Destructive actions tested on physical device
- [ ] Security-sensitive error handling reviewed
- [ ] Recovery behavior tested