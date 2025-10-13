# 🧺 Asset management

## General information

We support 5 types of assets:

<figure><img src="../../../.gitbook/assets/image (2) (1).png" alt="" width="199"><figcaption></figcaption></figure>

Our platform uses them to manage scans and scan results.

This is how it works:

1. You create/import asset (for example any repository)
2. Portal sends this repository in `REPOSITORY` variable to auditor
3. Auditor performs scans and calls Portal's API endpoint with REPOSITORY parameter and a report from scanner
4. Now portal knows where to put all asset-related vulnerabilities
