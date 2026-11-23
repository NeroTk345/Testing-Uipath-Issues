# Troubleshooting

Common problems and how to solve them. Not listed here? Open a [bug report](https://github.com/NeroTk345/Testing-Uipath-Issues/issues/new/choose).

**Jump to:** [App and access](#app-and-access) · [Starting a run](#starting-a-run) · [Run log](#run-log) · [Results in Datto RMM](#results-in-datto-rmm) · [Known issues](#known-issues)

---

## App and access

### I cannot open the app

**Likely cause:** you have no access to the PROD folder, or no user licence.

**What to do:** ask an administrator to add you to the right user group. See [Roles and permissions](roles-and-permissions.md). After you are added, sign out and sign in again.

### I do not see the DattoRMM or NOC page

**Likely cause:** you are not in the user group for that product. The app only shows the products that belong to your groups.

**What to do:** ask an administrator to add you to the group for that product. Then sign out and sign in again.

### The run log shows a "NonProd" data bucket

**Likely cause:** you opened the DEV or TEST app instead of the PROD app.

**What to do:** close it and open the PROD app. Real onboardings always run in PROD.

---

## Starting a run

### Error: "Not enough Platform Units to run the automation"

```text
Serverless.Api.CreditsExceeded
```

**Likely cause:** the job was sent to a UiPath cloud robot instead of our own robot. This is a configuration problem in the environment, not something you did.

**What to do:** report it as a **Bug** with environment and versions. An administrator must check the robot assignment of the folder.

### The job stays on "Pending"

**Likely cause:**

- Another run is still busy. Each environment runs one job at a time, so your run waits in the queue.
- The robot machine is offline or restarting.

**What to do:** wait a few minutes. Still pending after 10 minutes? Report it, mentioning the environment and the time you started.

### The run starts but nothing happens for a while

**Likely cause:** the first run after a new release downloads the new version to the robot first ("Installing package").

**What to do:** wait one or two minutes. This only happens once per release.

---

## Run log

### Every option shows "Skipped (not selected)"

**Likely cause:** no option was ticked before you clicked Start.

**What to do:** tick the options you need, or use **Select All**, and start again.

### Error about authentication, 401 or "unauthorized"

**Likely cause:**

- The token is wrong, expired or incomplete (check for spaces at the start or end).
- The token belongs to a different platform than the one you selected.

**What to do:** check the platform first, then copy the token again. Still failing? Ask for a new token for that account.

### An option shows "Skipped (already exists)"

This is expected. The item was already in the environment, so the tool did not create it again.

---

## Results in Datto RMM

### An item was created twice

This should not happen, because existing items are skipped. Open a **Bug** report with the option, the item name (use a placeholder if it contains customer data) and the run log.

### An item is missing after a "Done"

Refresh the Datto RMM page first; some lists update with a delay. Still missing? Open a **Bug** report with the run log.

---

## Known issues

| Issue | Product | Status |
|---|---|---|
| The UDF label import uses fixed UDF numbers and can overwrite UDFs that a customer already uses | DattoRMM | A configurable UDF start number is planned |
| Security levels have no "already exists" check yet. Check the account before you run this option a second time | NOC | Planned |

Check the latest release note on the product branch for the most recent list.
