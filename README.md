# DevSecOps-Reference-Pipeline

[![Secure CI](https://github.com/Popoo2020/DevSecOps-Reference-Pipeline/actions/workflows/ci.yml/badge.svg)](https://github.com/Popoo2020/DevSecOps-Reference-Pipeline/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**DevSecOps-Reference-Pipeline** is a practical GitHub Actions reference pipeline for integrating security and quality checks into a repeatable CI workflow.  
It is designed as a recruiter-friendly and engineer-friendly example of how lightweight controls can be embedded directly into development workflows without pretending to be a full enterprise platform.

> **Status:** working reference pipeline / active expansion.

## Implemented checks

| Capability | Status |
|---|---|
| Repository checkout with full history | ✅ Implemented |
| Python environment setup | ✅ Implemented |
| Conditional dependency installation | ✅ Implemented |
| Ruff linting when Python code exists | ✅ Implemented |
| Pytest execution when tests exist | ✅ Implemented |
| Bandit SAST when Python code exists | ✅ Implemented |
| `pip-audit` dependency review when manifest exists | ✅ Implemented |
| Gitleaks secret scanning | ✅ Implemented |
| SBOM generation | 🟡 Planned |
| Signed releases / provenance | 🟡 Planned |
| Container and IaC scanning | 🟡 Planned |

## Why this matters

The repository demonstrates a security-first CI pattern that:

- avoids false confidence from `pytest || true`
- runs meaningful checks when applicable
- skips irrelevant checks transparently when a matching codebase or manifest is absent
- provides a clear foundation for supply-chain security controls
- is intentionally understandable for teams adopting DevSecOps incrementally

## Workflow overview

```text
Push / Pull Request
        │
        ▼
Checkout + Python setup
        │
        ▼
Install project/tooling dependencies
        │
        ├── Ruff lint
        ├── Pytest
        ├── Bandit SAST
        ├── pip-audit
        └── Gitleaks secret scan
```

## Example use cases

- educational reference for CI/CD security hygiene
- starting point for Python-oriented repositories
- baseline for adding policy gates to proof-of-concept security projects
- portfolio evidence of practical DevSecOps implementation

## Current limitations

This repository is a **reference implementation**, not a universal CI platform.  It currently focuses on:

- Python-oriented checks
- secrets detection
- dependency auditing
- lightweight static analysis

The following are intentionally left for further expansion:

- SBOM generation
- release signing
- container image scanning
- IaC scanning with tools such as Checkov or Trivy
- policy-as-code enforcement

## Recommended next steps

1. Add CycloneDX SBOM generation
2. Add container/IaC scanning examples
3. Include a small sample vulnerable app so the pipeline output is demonstrable
4. Publish screenshots or sample workflow outputs
5. Add branch protection guidance in documentation
