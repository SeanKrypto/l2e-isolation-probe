# Linux namespace feasibility probe

This repository is proposed for one manually approved, synthetic Linux network-namespace feasibility test on a standard GitHub-hosted Ubuntu 24.04 runner.

The workflow contains only inline synthetic probe code. It does not check out application source, use third-party Actions, install packages, upload artifacts, or intentionally contact external services. Its TCP positive controls use runner-local IPv4 and IPv6 loopback listeners.

The workflow is manual-only, requests no GitHub token permissions, and has a three-minute job limit and one-minute probe-step limit. Its first-attempt guard rejects reruns, but does not prevent a second fresh manual dispatch. Concurrency serializes runs; it does not enforce a one-run lifetime limit.

Success establishes only the observed namespace, privilege, native socket, descriptor, and fixed-child properties. DNS, proxy, pathname broker sockets, filesystem isolation, runner credentials, general descendant cleanup, and application-tool isolation remain unqualified. Success is not authorization to execute application tooling.

Workflow SHA256: `3beb4f5d60bbbc748faf11a755f6635c26c43e27631a9dbb37587bc0f3da9e71`.

Publication, repository settings, reference protection, and the single manual execution require separate owner approval. Treat code, commit metadata, and workflow logs as permanently public. Do not add application source, secrets, private configuration, or operational evidence.
