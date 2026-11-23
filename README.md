# Testing-Uipath-Issues: DattoRMM

This branch covers feedback, questions, bug reports and version information for the **DattoRMM** onboarding tooling that the consultants use.

Use it to tell us what works, what does not, and what you would like to see improved. Every report is tracked, so nothing gets lost in chat or email.

> Working on NOC? See the [NOC branch](https://github.com/NeroTk345/Testing-Uipath-Issues/tree/NOC).

[🐞 Report a bug](https://github.com/NeroTk345/Testing-Uipath-Issues/issues/new?template=bug.yml) ·
[❓ Ask a question](https://github.com/NeroTk345/Testing-Uipath-Issues/issues/new?template=question.yml) ·
[💡 Suggest an idea](https://github.com/NeroTk345/Testing-Uipath-Issues/issues/new?template=idea.yml) ·
[📋 Changelog](CHANGELOG.md)

---

## Quick start

1. Go to **Issues** and click **New issue**.
2. Pick **Bug**, **Question** or **Idea**.
3. Choose product **DattoRMM**.
4. Fill in the app version, process version and environment.
5. Submit.

---

## Documentation

| Page | What you find there |
|---|---|
| [Options reference](docs/components.md) | What each DattoRMM option creates, the run order and what to watch out for |
| [User guide](https://github.com/NeroTk345/Testing-Uipath-Issues/blob/main/docs/user-guide.md) | How to run an onboarding, step by step |
| [Troubleshooting](https://github.com/NeroTk345/Testing-Uipath-Issues/blob/main/docs/troubleshooting.md) | Common errors and what to do |
| [Release process](https://github.com/NeroTk345/Testing-Uipath-Issues/blob/main/docs/release-process.md) | How a new version reaches PROD |
| [Changelog](CHANGELOG.md) | What changed in each version |

---

## What the DattoRMM tool does

The DattoRMM onboarding app sets up a new Datto RMM environment with our standard configuration. You choose which parts to create, and the automation runs them in the background.

| Option | What it creates |
|---|---|
| **UDF labels** | Labels for the user-defined fields |
| **Site groups** | Site groups used for filtering |
| **Device groups** | Device groups |
| **Filters** | Device filters |
| **Components** | Components from the component store, plus our own |
| **Policies** | Monitoring and maintenance policies |
| **Jobs** | Scheduled jobs |
| **Dashboards** | Dashboards |
| **Reports** | Scheduled reports |

Items that already exist are skipped, so running the same option twice does not create duplicates. Some sites may need a manual decision, for example when two sites have almost the same name.

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
- **Process version**: the version of the automation behind it (for example `Dattormm-Onboarding-Automation 1.0.10`).

### What to put in your report

- App version (shown in Orchestrator under **Apps**, or in the app)
- Process version (shown in Orchestrator under **Processes**)
- Environment (DEV, TEST or PROD)

If you do not know the versions, write "unknown" and say where you opened the tool. Do not guess.

---

## Release notes

Every new DattoRMM version gets a short release note in English, in the **Releases** section of this repository.

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
- `DattoRMM`: the issue is about this tool

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

## Release checklist

Use this list every time a new version of the DattoRMM process is released.

1. Pick the next version number using MAJOR.MINOR.PATCH (see Versions above).
2. Test the process in DEV, then TEST. Note the results.
3. Add a new entry at the top of `CHANGELOG.md`: version, date, environment, process name, and what is New, Changed, Fixed, and Action needed.
4. Check that the process name in the changelog matches the name in Orchestrator.
5. Commit to this branch with a short message, for example `Changelog: DattoRMM 1.1.0`.
6. Tell the team in the issue tracker or in chat that the release is live.

The changelog is the place where consultants look for "what is new". Keep it short and plain.
