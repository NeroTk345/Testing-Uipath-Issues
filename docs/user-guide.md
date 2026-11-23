# User guide

How to run an onboarding with the **Professional Services Toolkit**.

> **In short:** open the PROD app, choose the product, fill in the platform and token, tick what you want to create, click **Start** and read the run log.

---

## Before you start

You need:

- **Access to the app.** You must be in the user group for the product (for example DattoRMM or NOC). No access? See [Roles and permissions](roles-and-permissions.md).
- **The API token** of the customer's Datto RMM account.
- **The platform** the customer's Datto RMM account runs on (for example Pinotage).

Always use the **PROD** app for real onboardings. DEV and TEST are for developers and testers only.

---

## 1. Open the app

Open the Professional Services Toolkit with the link you received, or from Orchestrator under **Apps** in the PROD folder.

The home page shows the products you have access to. You only see the products that belong to your user group.

---

## 2. Choose the product

| Product | Use it for |
|---|---|
| **DattoRMM** | Setting up a new Datto RMM environment with the standard best-practice configuration |
| **NOC** | Preparing a Datto RMM environment for Kaseya 24/7 NOC monitoring |

---

## 3. Fill in the connection details

| Field | What to enter |
|---|---|
| **Platform** | The Datto RMM platform of the customer: Concord, Vidal, Pinotage, Merlot, Zinfandel or Syrah |
| **Token** | The API token of the customer's Datto RMM account |

The token and the platform must belong together. A token from one platform does not work on another.

> Never share the token in chat, email or an issue. If you think a token was exposed, follow the [security policy](../SECURITY.md).

---

## 4. Choose what to create (DattoRMM)

The options are grouped in steps. Tick the ones you need, or use **Select All**.

| Step | Option | What it creates |
|---|---|---|
| 1 · Basics | **UDF labels** | Labels on the user-defined fields |
| | **Site groups** | Site groups used for filtering |
| | **Filters** | Device filters |
| | **Device groups** | Device groups |
| 2 · Com-store | **Com-store components** | Components from the component store, plus our own |
| 3 · Policies and jobs | **Policies** | Monitoring and maintenance policies |
| | **Jobs** | Scheduled jobs |
| 4 · Reporting | **Reports** | Scheduled reports |
| | **Dashboards** | Dashboards |

### Configuration

| Choice | Meaning |
|---|---|
| **Base** | The standard configuration |
| **Base + K365** | The standard configuration plus the extra items for customers with the K365 add-on |

The **Summary** panel shows how many options you selected and whether K365 is on.

> **Good to know:** items that already exist in the customer's environment are skipped. Running the same option twice does not create duplicates.

For the NOC options, see the [NOC branch](https://github.com/NeroTk345/Testing-Uipath-Issues/tree/NOC).

---

## 5. Start the run

Click **Start**. The automation runs in the background on a robot. You can follow it in the **Run log** panel.

A run usually takes from a few seconds to a few minutes, depending on how many options you selected. The first run after a new release can take a little longer, because the robot first downloads the new version.

---

## 6. Read the run log

Example:

```text
=== Kaseya-Tool run ===
Date: 17-11-2026 13:18:12
Platform: Pinotage
Configuration: Base + K365

[UDF labels] Done
[Site groups] Skipped (not selected)
[Filters] Skipped (not selected)
...
=== Run finished 13:18:12 ===
```

| Result | Meaning | What to do |
|---|---|---|
| **Done** | The option ran successfully | Nothing |
| **Skipped (not selected)** | You did not tick this option | Nothing, or run it again with the option ticked |
| **Skipped (already exists)** | The item was already there | Nothing, this is expected |
| **Error / failed** | Something went wrong | See [Troubleshooting](troubleshooting.md). Still stuck? Open a [bug report](https://github.com/NeroTk345/Testing-Uipath-Issues/issues/new/choose) |

---

## 7. Check the result

Open the customer's Datto RMM environment and check that the items are there, for example the UDF labels under the account settings, or the new filters and policies.

---

## Something wrong or missing?

- Error or unexpected result → [Troubleshooting](troubleshooting.md), then a **Bug** report
- Question → a **Question** issue
- Missing option or improvement → an **Idea** issue
