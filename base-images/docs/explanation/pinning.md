# Why We Pin Base Images

## The Problem

Unpinned base images (`FROM node:20`) pull whatever `latest` happens to be at build time. This means:

- **Builds aren't reproducible** — same Dockerfile, different image
- **CVE scans become meaningless** — you scanned version A but deployed version B
- **Supply chain attacks** — a compromised upstream image propagates silently

## Our Approach

Every base image is pinned by SHA256 digest and rebuilt weekly from verified upstream sources. The rebuild pipeline:

1. Pulls the upstream official image
2. Runs Trivy and Grype vulnerability scans
3. Adds our standard CA certificates and monitoring agent
4. Pushes to our internal registry with a dated tag
5. Updates the `latest` tag only if scans pass
