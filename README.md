# DevSecOps Reference Pipeline

This repository contains an opinionated GitHub Actions workflow that demonstrates how to embed security throughout your CI/CD lifecycle. It automates static code analysis, dependency vulnerability scanning, secret scanning, container image scanning, infrastructure-as-code checks, SBOM generation and signed release publishing.

## Overview

Modern software delivery requires continuous security assurance. The reference pipeline integrates popular open-source tools to provide defence-in-depth for Python applications and infrastructure code.

## Features

- **Static Application Security Testing (SAST)** via Bandit and Semgrep.
- **Dependency vulnerability scanning** using pip-audit and osv-scanner.
- **Secret scanning** leveraging gitleaks to detect accidental credentials in code.
- **Container image scanning** with Trivy for OS packages and application dependencies.
- **Infrastructure-as-Code scanning** using Checkov to validate Terraform/Azure/AWS templates.
- **SBOM generation** using CycloneDX and dependency track upload.
- **Signed releases** using Cosign and GitHub OIDC for provenance.

## Repository Structure

- `.github/workflows/` – Continuous integration workflows:
  - `security.yml` – runs SAST, dependency, secret and IaC scans on pull request and push.
  - `release.yml` – builds container image, generates SBOM and signs release on version tags.
- `examples/` – Sample Python application and Terraform modules used for demonstration.
- `docs/` – Documentation on tool configuration and extending the pipeline.

## Usage

Fork or clone this repository and adapt the workflow YAML files to your project’s needs. Ensure secrets for container registry and signing keys are configured in your repository settings.

## Contributing

Feel free to contribute improvements or additional scanning tools. Please ensure changes include corresponding updates to the documentation and example code.

## License

This project is released under the Apache 2.0 license.

