# Contributing

Thanks for helping to improve the DattoRMM and NOC tooling. There are two ways to contribute: **reporting** and **changing**.

---

## 1. Reporting (everyone)

Most contributions are reports from consultants who use the tooling every day.

1. Check the [open issues](https://github.com/NeroTk345/Testing-Uipath-Issues/issues) first. Add a comment to an existing issue instead of creating a duplicate.
2. Click **New issue** and choose **Bug**, **Question** or **Idea**.
3. Fill in every required field. Labels are added automatically based on your answers.
4. Keep one problem per issue.

See the [README](README.md) for what to include and what never to include.

---

## 2. Changing (developers)

### Repository structure

| Branch | Contains |
|---|---|
| `main` | Issue forms, labels, workflows and shared documentation (`docs/`) |
| `DattoRmm` | DattoRMM README, changelog and release template |
| `NOC` | NOC README, changelog, release template and NOC documentation |

Issue forms only work from `main`, so everything under `.github/` lives there.

### Workflow

1. Create a branch from the branch you want to change, for example `docs/update-user-guide` from `main`.
2. Make your change and commit with a short, clear message:
   - `Docs: add troubleshooting for token errors`
   - `Changelog: DattoRMM 1.2.0`
   - `Forms: add environment field to idea form`
3. Open a **pull request** and fill in the template.
4. The `Validate files` check must pass (valid JSON/YAML, no secrets).
5. A code owner reviews and merges.

### Changing the automation itself

The automations are not stored in this repository. They live in UiPath Studio Web and are released through UiPath Solutions. See [docs/release-process.md](docs/release-process.md) for how a change moves from DEV to TEST to PROD.

---

## Writing style

- Write in **English**, in short sentences.
- Write for consultants: explain **what it does for them**, not how it is built.
- Use placeholders for anything sensitive: `[token]`, `[customer]`, `[site]`.
