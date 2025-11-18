# DataOps Databricks Project

A opinionated starter for DataOps workflows on Databricks. This repository contains infrastructure and application patterns to develop, test, and deploy data pipelines and analytics workloads on Databricks with repeatable CI/CD.

## Key goals
- Reproducible infrastructure as code (IaC) for Databricks workspaces and compute
- Automated CI/CD for notebooks, jobs, and libraries
- Testable local development workflows and integration pipelines
- Clear separation of environments (dev / staging / prod)

## Features
- Terraform (or IaC) templates to provision Databricks resources
- Structured repository layout for notebooks, jobs, and libraries
- Scripts and tooling to package and deploy Python wheels / JARs to Databricks
- Example job definitions and scheduling patterns
- Testing guidance for unit and integration tests

## Getting started

Prerequisites
- Databricks workspace (AWS / Azure / GCP)
- Terraform (if using IaC)
- Databricks CLI or databricks-sdk for deployment
- Python 3.8+ and pip
- Git

Quick start
1. Clone the repo:
   git clone <repo-url>
2. Configure credentials for your cloud provider and Databricks CLI.
3. Provision infrastructure (example with Terraform):
   terraform init
   terraform apply -var="env=dev"
4. Build and deploy code artifacts (example):
   ./scripts/build.sh
   ./scripts/deploy.sh --env dev

Adjust scripts and variables to match your cloud account and workspace.

## Development workflow
- Work in feature branches, keep notebooks and code modular.
- Write unit tests for transform logic; run them locally with pytest.
- Validate integration by running jobs against a short-lived dev cluster.
- Use CI to run tests, linting, and automated deployments to staging.

## Testing & Quality
- Unit tests: pytest + mocks for external I/O
- Integration tests: run against isolated Databricks dev workspace or staging
- Static analysis: flake8 / black for Python formatting

## CI/CD
- Recommended: GitHub Actions / Azure DevOps pipelines to run tests and deploy
- Protect main branches and require PR reviews before merging

## Contributing
- Open issues or PRs with clear descriptions
- Follow repository coding/style guidelines and tests for new features

## License
This project is licensed under the MIT License — see [LICENSE](DataOps_Databricks/LICENSE) for details.

## Contact
Project maintainer: see repository owner and issues for questions.