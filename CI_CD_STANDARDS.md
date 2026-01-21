## 🎯 CI/CD Goals at Akrynix

Our CI/CD pipelines must:

* Catch bugs early
* Prevent broken code from reaching production
* Be reproducible across environments
* Be simple enough for new hires to understand

---

## 🧱 Environment Strategy (Mandatory)

We use **three environments**:

| Environment | Branch      | Purpose              |
| ----------- | ----------- | -------------------- |
| Development | `feature/*` | Local & experimental |
| Staging     | `develop`   | Integration & QA     |
| Production  | `main`      | Live users           |

📌 **Rule**: No direct deployments from feature branches.

---

## 🔁 CI Pipeline (All Repositories)

Triggered on:

* Pull Requests to `develop` or `main`

### Required Steps

1. Checkout code
2. Install dependencies
3. Lint code
4. Run tests
5. Build artifacts

### Example CI Workflow

```yml
name: CI

on:
  pull_request:
    branches: [develop, main]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Install dependencies
        run: npm ci

      - name: Run lint
        run: npm run lint

      - name: Run tests
        run: npm test
```

---

## 🚀 CD Pipeline (Production Deployment)

### Deployment Rules

* Deployments are triggered **only from `main`**
* CI must pass before deployment
* Production secrets are never exposed to CI logs

---

### Example CD Workflow (Node.js + AWS)

```yml
name: Deploy Production

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Install dependencies
        run: npm ci

      - name: Build
        run: npm run build

      - name: Deploy
        run: ./scripts/deploy.sh
```

📌 `deploy.sh` is environment-aware (staging vs prod).

---

## 🔐 Secrets Management

* All secrets stored in **GitHub Actions Secrets**
* Environment-scoped secrets:

  * `AKRYNIX_DEV_*`
  * `AKRYNIX_STAGING_*`
  * `AKRYNIX_PROD_*`
* Secrets never committed to code

---

## 🐳 Docker Usage (Recommended)

When applicable:

* Build Docker image in CI
* Push to registry
* Deploy immutable images

This ensures:

* Environment parity
* Rollbacks are trivial
* “Works on my machine” disappears

---

## 🔍 Observability & Safety

* CI logs retained
* Failed deployments block further releases
* Rollback procedures documented per repo

---

## 🚫 Forbidden CI/CD Practices

* Manual production deployments
* Deploying from feature branches
* Hardcoded credentials
* Skipping CI checks

Violations are treated as security incidents.

---
