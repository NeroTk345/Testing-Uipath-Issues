# Security policy

This repository is used for feedback on internal onboarding tooling. It must never contain credentials or customer information.

## What counts as a security problem

- An **API token, key or secret** was posted in an issue, comment, screenshot or file.
- **Customer names, site names or personal data** were posted.
- **Internal details** that should not be public, such as server addresses or login details.

## What to do

1. **Do not** open a new public issue about it. That only spreads the information further.
2. **Contact the repository owner directly** (Teams or email) and say where the information was posted.
3. If it was a **token or key**, it must be **revoked and replaced** in the source system, even after it has been removed here. Deleting a comment does not remove it from notifications or other people's email.
4. The repository owner removes or edits the content and confirms when it is done.

## Prevention

- Every issue form asks you to confirm that you removed tokens and customer data.
- An automatic check (`Validate files` workflow) blocks commits that contain private IP addresses, passwords or tokens.
- Use placeholders such as `[token]`, `[customer]` and `[site]` in every report.
