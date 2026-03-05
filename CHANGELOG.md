# Changelog

This file tracks notable changes to **DevSecOps‑Reference‑Pipeline** following
the [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) format.

## [0.1.0] – 2026‑03‑01

### Added

* **CI pipeline:** Added a GitHub Actions workflow under
  `.github/workflows/ci.yml` that performs linting, unit test execution,
  secret scanning with `gitleaks` and dependency scanning with
  `osv‑scanner`/`pip‑audit`.  The workflow installs Python dependencies,
  runs static analysis and fails gracefully when optional tools are
  unavailable.
* **Initial scaffolding:** Created standard repository files (LICENSE,
  SECURITY.md, CODE_OF_CONDUCT.md, CONTRIBUTING.md, CODEOWNERS) to establish
  project governance and encourage secure contributions.
* **Initial release:** Published version `v0.1.0` as a baseline reference
  implementation for DevSecOps pipelines.
