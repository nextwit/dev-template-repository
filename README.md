# 🚀 dev-template-repository

> A production-ready developer template repository with best-practice folder structures, CI/CD workflows, branching strategies, and configuration standards. Jumpstart any project with consistent scaffolding for Power Platform, Azure, and modern full-stack solutions.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Maintained](https://img.shields.io/badge/Maintained-yes-green.svg)](https://github.com/nextwit/dev-template-repository)

---

## 📋 Table of Contents

- [Overview](#overview)
- [What's Included](#whats-included)
- [Getting Started](#getting-started)
- [Repository Structure](#repository-structure)
- [Branching Strategy](#branching-strategy)
- [CI/CD Workflows](#cicd-workflows)
- [Configuration Standards](#configuration-standards)
- [How to Use This Template](#how-to-use-this-template)
- [Customization Guide](#customization-guide)
- [Contributing](#contributing)
- [License](#license)

---

## 📖 Overview

This repository serves as a **GitHub Template Repository** — a standardized starting point for building enterprise-grade applications with consistent structure, tooling, and governance practices.

It is designed for developers and solution architects working with:

- **Microsoft Power Platform** (PCF Controls, Power Automate, Dataverse)
- **Azure Services** (Azure Functions, Container Apps, AI Services)
- **Full-stack web applications**
- **Any modern software project** requiring a clean, governed scaffold

Use this template to eliminate repetitive setup work and start every project aligned with best practices from day one.

---

## 📦 What's Included

| Feature | Description |
|---|---|
| 📁 Folder structure | Standardized layout for `src`, `docs`, `tests`, `scripts`, `.github` |
| ⚙️ GitHub Actions | Ready-made CI/CD workflow templates |
| 🔒 Branch protection | Pre-configured branching strategy documentation |
| 📝 Issue templates | Bug report & feature request templates |
| 🔁 PR template | Pull request checklist and review guidelines |
| 🧹 .gitignore | Comprehensive ignore rules for common stacks |
| 📄 License | MIT License pre-configured |
| 🤝 Contributing guide | Contribution standards and code of conduct |
| 🛡️ Security policy | Responsible disclosure guidelines |
| 📋 Changelog | CHANGELOG.md with Keep a Changelog format |

---

## 🚀 Getting Started

### Option 1: Use as a GitHub Template (Recommended)

1. Click the green **"Use this template"** button at the top of this repository.
2. Name your new repository and choose visibility.
3. Clone your new repo locally:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
```

4. Follow the [Customization Guide](#customization-guide) to tailor it to your project.

### Option 2: Clone Directly

```bash
git clone https://github.com/nextwit/dev-template-repository.git my-new-project
cd my-new-project

# Remove existing git history and start fresh
rm -rf .git
git init
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git add .
git commit -m "chore: initial project setup from template"
git push -u origin main
```

---

## 📂 Repository Structure

```
dev-template-repository/
│
├── .github/                        # GitHub-specific configuration
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md           # Bug report template
│   │   └── feature_request.md      # Feature request template
│   ├── workflows/
│   │   ├── ci.yml                  # Continuous integration workflow
│   │   ├── cd.yml                  # Continuous deployment workflow
│   │   └── pr-validation.yml       # PR title and branch validation
│   └── PULL_REQUEST_TEMPLATE.md    # Pull request checklist
│
├── docs/                           # Project documentation
│   ├── architecture/               # Architecture decision records (ADRs)
│   ├── api/                        # API documentation
│   └── guides/                     # Developer and user guides
│
├── src/                            # Source code
│   ├── components/                 # Reusable components / PCF controls
│   ├── services/                   # Business logic and service layer
│   ├── models/                     # Data models and schemas
│   └── utils/                      # Shared utilities and helpers
│
├── tests/                          # Test suites
│   ├── unit/                       # Unit tests
│   ├── integration/                # Integration tests
│   └── e2e/                        # End-to-end tests
│
├── scripts/                        # Automation and utility scripts
│   ├── deploy/                     # Deployment scripts
│   └── setup/                      # Environment setup scripts
│
├── .editorconfig                   # Editor configuration
├── .gitignore                      # Git ignore rules
├── CHANGELOG.md                    # Project changelog
├── CONTRIBUTING.md                 # Contribution guidelines
├── LICENSE                         # MIT License
├── SECURITY.md                     # Security policy
└── README.md                       # This file
```

---

## 🌿 Branching Strategy

This template follows a **trunk-based development** model with feature branches:

| Branch | Purpose | Protection |
|---|---|---|
| `main` | Production-ready code | ✅ Protected — requires PR + review |
| `develop` | Integration branch for features | ✅ Protected — requires PR |
| `feature/[name]` | New features and enhancements | ❌ Short-lived |
| `fix/[name]` | Bug fixes | ❌ Short-lived |
| `hotfix/[name]` | Critical production patches | ❌ Short-lived |
| `release/[version]` | Release preparation | ❌ Short-lived |

### Commit Message Convention

This template follows [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(optional scope): <short description>

Examples:
feat(auth): add OAuth2 token refresh
fix(api): handle null response from Dataverse
docs(readme): update branching strategy section
chore(deps): bump node version to 20
```

Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`, `perf`, `ci`

---

## ⚙️ CI/CD Workflows

### Continuous Integration (`ci.yml`)

Triggered on every push and pull request to `main` and `develop`:

- ✅ Lint and code style checks
- ✅ Unit and integration test execution
- ✅ Build validation
- ✅ Security vulnerability scanning

### Continuous Deployment (`cd.yml`)

Triggered on merge to `main`:

- 🚀 Build and package artifacts
- 🚀 Deploy to target environment (configure your environment secrets)
- 🚀 Post-deployment smoke tests

### PR Validation (`pr-validation.yml`)

- Validates PR title follows Conventional Commits format
- Enforces branch naming conventions
- Checks for linked issues

### Required GitHub Secrets

Configure the following secrets in your repository settings before enabling workflows:

| Secret | Description |
|---|---|
| `AZURE_CLIENT_ID` | Azure service principal client ID |
| `AZURE_CLIENT_SECRET` | Azure service principal secret |
| `AZURE_TENANT_ID` | Azure tenant ID |
| `POWER_PLATFORM_SPN_KEY` | Power Platform service principal key |
| `SONAR_TOKEN` | SonarCloud token (optional) |

---

## 🔧 Configuration Standards

### Editor & Code Style

- `.editorconfig` enforces consistent indentation, line endings, and charset across all editors.
- Recommended extensions for VS Code are listed in `.vscode/extensions.json`.

### Environment Variables

- Never commit secrets or credentials to the repository.
- Use `.env.example` as a template — copy to `.env` locally and populate values.
- All secrets should be managed via GitHub Secrets, Azure Key Vault, or environment-specific configuration services.

### Code Quality

- All code should pass linting before committing (use pre-commit hooks where applicable).
- Minimum test coverage target: **80%**.
- All public functions and classes must be documented.

---

## 🛠️ How to Use This Template

### Step 1 — Create from template

Click **"Use this template"** on GitHub and create your new repository.

### Step 2 — Update project identity

Replace all placeholder values with your project details:

```bash
# Files to update:
# - README.md         → project name, description, badges, links
# - package.json      → name, version, author (if Node.js)
# - LICENSE           → year and author name
# - CHANGELOG.md      → initial version entry
# - .github/workflows → environment targets and secrets references
```

### Step 3 — Configure branch protection

In your new repo: **Settings → Branches → Add rule** for `main` and `develop`:

- ✅ Require pull request reviews before merging
- ✅ Require status checks to pass
- ✅ Require conversation resolution before merging
- ✅ Restrict force pushes

### Step 4 — Set up secrets

Add the required secrets listed in the [CI/CD section](#cicd-workflows).

### Step 5 — Start building

You're ready. Remove any template-specific files not relevant to your project and begin development.

---

## ✏️ Customization Guide

| What to customize | Where |
|---|---|
| Project name & description | `README.md`, `package.json` |
| License type | `LICENSE` |
| Workflow triggers & targets | `.github/workflows/*.yml` |
| Folder structure | Rename/add folders in `src/` |
| Issue & PR templates | `.github/ISSUE_TEMPLATE/`, `.github/PULL_REQUEST_TEMPLATE.md` |
| Ignore rules | `.gitignore` |
| Editor settings | `.editorconfig` |

---

## 🤝 Contributing

Contributions, improvements, and suggestions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a pull request.

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-improvement`
3. Commit your changes following [Conventional Commits](#commit-message-convention)
4. Push to your fork and open a Pull Request

---

## 🛡️ Security

Please review our [Security Policy](SECURITY.md) for responsible disclosure guidelines. Do not open public issues for security vulnerabilities.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Zsolt Zombik** — Senior Power Platform Expert | AI & Dev Blogger  
🌐 [aidevme.com](https://aidevme.com) | 💼 [LinkedIn](https://www.linkedin.com/in/zsoltzombik/) | 🐙 [GitHub](https://github.com/nextwit)

---

> 💡 *Built with ❤️ to help developers ship faster without sacrificing quality.*