<div align="center">

# Professional Services Toolkit · Feedback & Docs

**Feedback, questions, bug reports and documentation for the DattoRMM and NOC onboarding tooling.**

[![Validate files](https://github.com/NeroTk345/Testing-Uipath-Issues/actions/workflows/validate.yml/badge.svg)](https://github.com/NeroTk345/Testing-Uipath-Issues/actions/workflows/validate.yml)
[![Open issues](https://img.shields.io/github/issues/NeroTk345/Testing-Uipath-Issues?label=open%20issues)](https://github.com/NeroTk345/Testing-Uipath-Issues/issues)
[![Open bugs](https://img.shields.io/github/issues/NeroTk345/Testing-Uipath-Issues/bug?label=open%20bugs&color=d73a4a)](https://github.com/NeroTk345/Testing-Uipath-Issues/issues?q=is%3Aissue+is%3Aopen+label%3Abug)

[🐞 Report a bug](https://github.com/NeroTk345/Testing-Uipath-Issues/issues/new?template=bug.yml) ·
[❓ Ask a question](https://github.com/NeroTk345/Testing-Uipath-Issues/issues/new?template=question.yml) ·
[💡 Suggest an idea](https://github.com/NeroTk345/Testing-Uipath-Issues/issues/new?template=idea.yml) ·
[📘 User guide](docs/user-guide.md)

</div>

---

## What is this?

The **Professional Services Toolkit** is a UiPath app that sets up Kaseya environments with our standard best-practice configuration. It replaces the old PowerShell scripts: you tick what you need, click **Start**, and a robot does the rest.

This repository is the central place to tell us what works, what does not, and what you would like to see improved. Every report is tracked, so nothing gets lost in chat or email.

| Product | What it does | Details |
|---|---|---|
| **DattoRMM** | Sets up a new Datto RMM environment: UDF labels, site and device groups, filters, components, policies, jobs, reports and dashboards | [DattoRMM branch](https://github.com/NeroTk345/Testing-Uipath-Issues/tree/DattoRmm) |
| **NOC** | Prepares a Datto RMM environment for Kaseya 24/7 NOC monitoring: UDF labels, security levels, device filters, policies and NOC components | [NOC branch](https://github.com/NeroTk345/Testing-Uipath-Issues/tree/NOC) |

---

## Contents

- [Documentation](#documentation)
- [Environments](#environments)
- [Versions](#versions)
- [How to report](#how-to-report)
- [What never to include](#what-never-to-include)
- [Labels and status](#labels-and-status)
- [Repository structure](#repository-structure)
- [Contact](#contact)

---

## Documentation

| For | Page |
|---|---|
| Consultants | [User guide](docs/user-guide.md) · [Troubleshooting](docs/troubleshooting.md) |
| Developers and admins | [Architecture](docs/architecture.md) · [Release process](docs/release-process.md) · [Roles and permissions](docs/roles-and-permissions.md) |
| Contributors | [Contributing](CONTRIBUTING.md) · [Security policy](SECURITY.md) |

---

## Environments

The tooling runs in three environments. Always state which one you used in your report.

| Environment | Purpose | Who uses it |
|---|---|---|
| **DEV** | Development and first tests. May be unstable. | Developers |
| **TEST** | Testing before a release. Check new features here. | Developers and testers |
| **PROD** | The live version used for real onboardings. | Consultants |

If you are unsure which environment you used, look at the app name and the folder it was started from.

---

## Versions

Every release has a version number in the form **MAJOR.MINOR.PATCH**, for example `2.0.0` or `1.0.7`.

| Part | Goes up when | Example |
|---|---|---|
| **MAJOR** | A change that alters how the tool works for users, or breaks existing runs | `1.0.7` → `2.0.0` |
| **MINOR** | New functionality that stays compatible | `1.0.7` → `1.1.0` |
| **PATCH** | A bug fix or small correction | `1.0.7` → `1.0.8` |

There are two kinds of version, and both matter:

- **App version**: the version of the app that consultants open (for example `Kaseya-Tool-PROD 2.0.0`).
- **Process version**: the version of the automation behind it (for example `Dattormm-Onboarding-Automation 1.1.2`).

Always include both, plus the environment, when you report a problem. If you do not know them, write "unknown" and say where you opened the tool. Do not guess.

What changed in each version? See the **Releases** section and the `CHANGELOG.md` on each product branch.

---

## How to report

1. **Search first.** Check the [open issues](https://github.com/NeroTk345/Testing-Uipath-Issues/issues) and the latest release note. If it is already reported, add your details there.
2. Click **New issue** and pick a form:

   | Form | Use it when |
   |---|---|
   | 🐞 **Bug** | Something does not work the way it should |
   | ❓ **Question** | You want to know how something works |
   | 💡 **Idea** | You have a suggestion to improve the tool |

3. Fill in every required field. Labels for product, environment and priority are added **automatically** from your answers.
4. One issue per problem. Three problems? Three issues.

A good report contains: versions and environment, what you did step by step, what you expected, what happened, the run log lines, and whether it happens every time.

---

## What never to include

- **API tokens, keys or passwords.** Not in the text, not in a screenshot, not in a log line.
- **Customer names, site names or personal data.** Use placeholders such as `[customer]` or `[site]`.
- **Screenshots that show tokens or customer information.** Crop or blur them first.

Posted something by accident? Follow the [security policy](SECURITY.md) straight away.

---

## Labels and status

| Label | Meaning |
|---|---|
| `bug` · `question` · `idea` | Type of report |
| `DattoRMM` · `NOC` | Product |
| `env: PROD` · `env: TEST` · `env: DEV` | Environment where it happened |
| `priority: high` · `priority: medium` · `priority: low` | Impact on your work |
| `needs-triage` · `needs-info` | Status: new, or waiting for your reply |

Issues move through the project board: **New → In progress → Done**.

**Response times:** we aim to read new issues within **one working day**. Problems that block an onboarding should also be raised directly with the tooling owner.

---

## Repository structure

```text
main
├── .github/
│   ├── ISSUE_TEMPLATE/      Bug, Question and Idea forms
│   ├── workflows/           Validation, automatic labels, label sync
│   ├── labels.yml           Label definitions
│   └── pull_request_template.md
├── docs/                    User guide, troubleshooting, architecture, release process, roles
├── CONTRIBUTING.md
├── SECURITY.md
└── README.md

DattoRmm                     README, CHANGELOG and release template for DattoRMM
NOC                          README, CHANGELOG, release template and NOC docs
```

The automations themselves live in UiPath Studio Web, not in this repository.

---

## Contact

For access requests, policy questions or anything that is not about the tooling itself, contact: **[contact person]**.

> **Visibility:** this repository may be visible to people outside the team. Do not put internal details, credentials or customer information in issues, comments, release notes or files.
