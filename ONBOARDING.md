# Developer Onboarding – Akrynix

Welcome to Akrynix 👋  
This document defines the official onboarding process for all engineers contributing to Akrynix repositories.

The goal is to ensure **fast onboarding**, **high code quality**, and **secure collaboration**.

---

## 🧑‍💻 Roles & Access Levels

Access is assigned based on role:

| Role | Access |
|----|----|
| Owner | Admin |
| Maintainer | Maintain |
| Engineer | Write |
| Contractor / Intern | Read or Limited Write |

> Direct access to production branches is **not permitted** for any role.

---

## 📅 Day 0 – Account & Access Setup

Before writing any code:

- [ ] GitHub account added to the Akrynix organization
- [ ] Assigned to the appropriate GitHub Team
- [ ] Two-Factor Authentication (2FA) enabled
- [ ] Read:
  - `README.md`
  - `CONTRIBUTING.md`
  - `CODE_OF_CONDUCT.md`
  - `SECURITY.md`

---

## 💻 Day 1 – Local Environment Setup

Each developer must:

- Install:
  - Git
  - Node.js (LTS)
  - Docker (if required)
- Clone assigned repositories
- Configure environment variables using `.env.example`
- Confirm the project builds successfully locally

---

## 🌱 Day 2 – First Task (Required)

Every new contributor must complete a **small, low-risk task**:

Examples:
- Fix a typo or documentation issue
- Improve logging or comments
- Add a small UI tweak

Process:
1. Create a `feature/<short-description>` branch
2. Commit changes with a clear message
3. Open a Pull Request
4. Request review from a maintainer

> This confirms tooling, permissions, and workflow understanding.

---

## 🔍 Code Review & Standards

- All changes must go through Pull Requests
- PRs require at least **one approval**
- CI checks must pass
- Maintain clean, readable, and documented code

---

## 🔐 Security Rules (Strict)

- Never commit secrets or credentials
- Never disable CI checks
- Never push directly to protected branches
- Report vulnerabilities responsibly

Violations may result in immediate access removal.

---

## ✅ Completion Criteria

A developer is considered **fully onboarded** when:
- First PR is merged
- CI checks are passing
- Code review feedback is addressed properly

---

Welcome aboard 🚀  
Let’s build great software together.
