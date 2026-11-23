# Testing-Uipath-Issues: NOC

This branch covers feedback, questions, bug reports and version information for the **NOC** configuration tooling that the consultants use.

NOC is a separate product from DattoRMM. It sets up the NOC configuration in a Datto RMM environment. For DattoRMM, use the [DattoRMM branch](https://github.com/NeroTk345/Testing-Uipath-Issues/tree/DattoRmm).

Use it to tell us what works, what does not, and what you would like to see improved. Every report is tracked, so nothing gets lost in chat or email.

[🐞 Report a bug](https://github.com/NeroTk345/Testing-Uipath-Issues/issues/new?template=bug.yml) ·
[❓ Ask a question](https://github.com/NeroTk345/Testing-Uipath-Issues/issues/new?template=question.yml) ·
[💡 Suggest an idea](https://github.com/NeroTk345/Testing-Uipath-Issues/issues/new?template=idea.yml) ·
[📋 Changelog](CHANGELOG.md)

---

## Quick start

1. Go to **Issues** and click **New issue**.
2. Pick **Bug**, **Question** or **Idea**.
3. Choose product **NOC**.
4. Fill in the app version, process version and environment.
5. Submit.

---

## Documentation

| Page | What you find there |
|---|---|
| [NOC reference](docs/noc-reference.md) | How the NOC process is built, each option, and how security levels work |
| [User guide](https://github.com/NeroTk345/Testing-Uipath-Issues/blob/main/docs/user-guide.md) | How to run an onboarding, step by step |
| [Troubleshooting](https://github.com/NeroTk345/Testing-Uipath-Issues/blob/main/docs/troubleshooting.md) | Common errors and what to do |
| [Release process](https://github.com/NeroTk345/Testing-Uipath-Issues/blob/main/docs/release-process.md) | How a new version reaches PROD |
| [Changelog](CHANGELOG.md) | What changed in each version |

---

## What the NOC tool does

The NOC tool sets up the standard NOC configuration in a Datto RMM environment. You choose which parts to create, and the automation runs them in the background.

| Option | What it creates |
|---|---|
| **UDF labels** | NOC labels on the user-defined fields, for example service level, patch, backup, antivirus and role |
| **Security levels** | Security levels for the sites |
| **Device filters** | The `DNOC.` device filters |
| **Policies** | The NOC policies |
| **Custom components** | The five NOC components (`.cpt` packages): GPO Incident Monitor, Automatic Service Monitor and Remediation, Unexpected Shutdown Analyzer, GPO Heartbeat and Automatic Service Heartbeat |

Items that already exist are skipped, so running the same option twice does not create duplicates.

**Caution:** some NOC components restart services. Test a new version in DEV or TEST first, and start with the detect-only mode where the component offers one.

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

Every release has a version number in the form **MAJOR.MINOR.PATCH**, for example `2.0.0` or `1.0.10`.

| Part | Goes up when | Example |
|---|---|---|
| **MAJOR** | A change that alters how the tool works for users, or breaks existing runs | `1.0.10` → `2.0.0` |
| **MINOR** | New functionality that stays compatible | `1.0.10` → `1.1.0` |
| **PATCH** | A bug fix or small correction | `1.0.10` → `1.0.11` |

There are two kinds of version, and both matter:

- **App version**: the version of the app that consultants open (for example `Kaseya-Tool-PROD 2.0.0`).
- **Process version**: the version of the automation behind it (for example `DattoNOC-Onboarding-Automation 1.0.10`).

### What to put in your report

- App version (shown in Orchestrator under **Apps**, or in the app)
- Process version (shown in Orchestrator under **Processes**)
- Environment (DEV, TEST or PROD)

If you do not know the versions, write "unknown" and say where you opened the tool. Do not guess.

---

## Release notes

Every new NOC version gets a short release note in English, in the **Releases** section of this repository.

Each release note contains:

- **Version** and **date**
- **Environment** it was deployed to
- **New**: what was added
- **Changed**: what works differently now
- **Fixed**: what was repaired
- **Known issues**: what still does not work
- **Action needed**: anything the consultant must do differently, if any

---

## How to create an issue

1. Go to the **Issues** tab.
2. Click **New issue** and choose the template that fits:

| Template | Use it when |
|---|---|
| **Bug** | Something does not work the way it should |
| **Question** | You want to know how something works or how to do something |
| **Idea** | You have a suggestion to improve the tool |

3. Fill in every required field, including product, versions and environment.
4. Submit.

One issue per problem keeps things trackable.

---

## What to include

- **Versions and environment** (see above)
- **What you did**, step by step
- **What you expected** to happen
- **What actually happened**
- **The log line** from the run log, or a screenshot of the error
- **The options you ticked** when you started the run
- **Whether it happens every time** or only sometimes

Before you report, check the open issues and the latest release note. The problem may already be known.

---

## What never to include

- **API tokens, keys or passwords.** Not in the text, not in a screenshot, not in a log line. If a token was posted by accident, tell the repository owner straight away so it can be replaced.
- **Customer names, site names or personal data.** Replace them with a placeholder such as `[customer]` or `[site]`.
- **Screenshots that show tokens or customer information.** Crop or blur them first.

---

## Labels and status

- `bug`: something is broken
- `question`: a question about how something works
- `idea`: a suggestion for improvement
- `NOC`: the issue is about this tool

Issues move through the project board: **New**, **In progress**, **Done**.

---

## Response times

- We aim to read new issues within **one working day**.
- Urgent problems that block an onboarding should also be raised directly with the responsible contact person.
- If an issue has had no reply after a few days, add a short comment so it gets attention again.

---

## Contact

For access requests, policy questions or anything that is not about the tooling itself, contact: **[contact person]**.

---

## Note on visibility

This repository may be visible to people outside the team. Do not put internal details, credentials or customer information in issues, comments, release notes or files.

---

## Release checklist

Use this list every time a new version of the NOC process is released.

1. Pick the next version number using MAJOR.MINOR.PATCH (see Versions above).
2. Test the process in DEV, then TEST. Note the results. Pay extra attention to components that restart services.
3. Add a new entry at the top of `CHANGELOG.md`: version, date, environment, process name, and what is New, Changed, Fixed, Known issues and Action needed.
4. Check that the process name in the changelog matches the name in Orchestrator.
5. Create a GitHub Release with `.github/release/RELEASE_TEMPLATE.md`. Tag: `noc-v<VERSION>`, target branch `NOC`.
6. Tell the team in the issue tracker or in chat that the release is live.
