# Testing-Uipath-Issues

This repository is the central place for feedback, questions, bug reports and version information about the **DattoRMM** and **NOC** tooling that the consultants use during onboarding.

Use it to tell us what works, what does not, and what you would like to see improved. Every report is tracked, so nothing gets lost in chat or email.

---

## Environments

The tooling runs in three environments. Always state which one you were using in your report.

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
- **Process version**: the version of the automation behind it (for example `Dattormm-Onboarding-Automation 1.0.10`).

### What to put in your report

Always include both versions when you report a problem:

- App version (shown in the app or in Orchestrator under **Apps**)
- Process version (shown in Orchestrator under **Processes**)
- Environment (DEV, TEST or PROD)

If you do not know the versions, write "unknown" and say where you opened the tool. Do not guess.

---

## Release notes

Every new version gets a short release note, written in English, in the Releases section of this repository.

Each release note contains:

- **Version** and **date**
- **Environment** it was deployed to
- **New**: what was added
- **Changed**: what works differently now
- **Fixed**: what was repaired
- **Known issues**: what still does not work
- **Action needed**: anything the consultant must do differently, if any

Keep it short. One line per item is enough.

---

## Before you report

Check the open issues first. Someone may already have reported the same problem, and you can add your details to that issue instead of creating a new one.

If the problem appeared after a new version was released, check its release note first. It may be a known issue.

---

## How to create an issue

1. Go to the **Issues** tab.
2. Click **New issue**.
3. Choose the template that fits best:

| Template | Use it when |
|---|---|
| **Bug** | Something does not work the way it should |
| **Question** | You want to know how something works or how to do something |
| **Idea** | You have a suggestion to improve the tool |

4. Fill in every required field. Choose the product: **DattoRMM**, **NOC** or **Not sure**.
5. Fill in the app version, process version and environment.
6. Submit the issue.

One issue per problem keeps things trackable. If you have three separate problems, create three issues.

---

## What to include

A good report makes it much faster to help you. Where possible, include:

- **Versions and environment** (see above)
- **What you did**, step by step
- **What you expected** to happen
- **What actually happened**
- **The log line** from the run log, or a screenshot of the error
- **The run settings** you used (for example, which checkboxes were ticked)
- **Whether it happens every time** or only sometimes

---

## What never to include

- **API tokens, keys or passwords.** Not in the text, not in a screenshot, not in a log line. If a token was posted by accident, tell the repository owner straight away so it can be replaced.
- **Customer names, site names or personal data.** Replace them with a placeholder such as `[customer]` or `[site]`.
- **Full screenshots that show tokens or customer information.** Crop or blur them first.

---

## Labels and status

Issues are sorted with labels:

- `bug`: something is broken
- `question`: a question about how something works
- `idea`: a suggestion for improvement
- `DattoRMM` / `NOC`: the product the issue is about

When an issue is picked up, it moves through the project board: **New**, **In progress**, **Done**.

---

## Response times

- We aim to read new issues within **one working day**.
- Urgent problems that block an onboarding should also be raised directly with the responsible contact person, not only here.
- If an issue has had no reply after a few days, add a short comment so it gets attention again.

---

## Contact

For access requests, policy questions or anything that is not about the tooling itself, contact: **[contact person]**.

---

## Note on visibility

This repository may be visible to people outside the team. Do not put internal details, credentials or customer information in issues, comments, release notes or files.
