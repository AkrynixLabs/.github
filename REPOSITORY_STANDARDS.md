# 📦 Akrynix Repository Standards

## 📛 Repository Naming Convention

### ✅ Format

```
<domain>-<project>-<type>
```

### Examples

| Repo                  | Purpose              |
| --------------------- | -------------------- |
| `web-akrynix-site`    | Company website      |
| `api-user-service`    | Backend API          |
| `mobile-akrynix-app`  | Mobile app           |
| `infra-aws-core`      | Cloud infrastructure |
| `devops-ci-templates` | Shared CI configs    |

### ❌ Not Allowed

* `test-repo`
* `backend-final`
* `new-api-v2`
* Personal names in repo titles

📌 **Rule**: Anyone should understand a repo’s purpose **without opening it**.

---

## 🧱 Repository Categories (Mandatory)

Every repo must fall into **one** category:

### 1️⃣ Frontend

```
web-*
```

* React
* Static sites
* Admin dashboards

### 2️⃣ Backend / APIs

```
api-*
service-*
```

* Node.js
* Laravel
* Microservices

### 3️⃣ Mobile

```
mobile-*
```

* React Native apps

### 4️⃣ Infrastructure

```
infra-*
```

* AWS
* Terraform
* CloudFormation

### 5️⃣ DevOps / Tooling

```
devops-*
```

* CI templates
* Internal scripts

---

## 🗂️ Standard Repository Structure

### 🌐 Frontend (React Example)

```
src/
 ├── components/
 ├── pages/
 ├── hooks/
 ├── services/
 ├── styles/
 └── utils/
public/
README.md
```

---

### ⚙️ Backend (Node.js API Example)

```
src/
 ├── controllers/
 ├── routes/
 ├── services/
 ├── models/
 ├── middlewares/
 └── utils/
config/
README.md
```

---

### ☁️ Infrastructure (Terraform Example)

```
modules/
environments/
 ├── dev/
 ├── staging/
 └── prod/
README.md
```

---

## 📄 Required Files (All Repositories)

Every repo **must** include:

```
README.md
.env.example
```

Optional but recommended:

```
CHANGELOG.md
```

❌ Repos without a README are **non-compliant**

---

## 📘 README.md Minimum Standard

Each README must contain:

```md
# Project Name

## Overview
What this project does.

## Tech Stack
Key technologies used.

## Setup
How to run locally.

## Scripts
Common commands.

## Contribution
Link to CONTRIBUTING.md
```

---

## 🔐 Public vs Private Repositories

### Public Repos

* Libraries
* Open-source tools
* Marketing or demo projects

### Private Repos

* Client work
* Internal tools
* Infrastructure
* Production APIs

📌 **Default = Private**

---

## 🧠 Ownership & Responsibility

* Every repo must have:

  * 1 Maintainer
  * Assigned GitHub Team
* No “orphan” repositories
* Owners oversee, do not micromanage

---

## 🚫 Anti-Patterns (Strictly Forbidden)

* Personal repos under Akrynix org
* Shared credentials in repos
* Direct pushes to `main`
* Unreviewed PRs

Violations may result in access removal.

---

## ✅ Compliance Checklist (Owners / Maintainers)

Before a repo is considered active:

* [ ] Naming standard followed
* [ ] README present and complete
* [ ] Team assigned
* [ ] Branch protection enabled
* [ ] CI workflow present
