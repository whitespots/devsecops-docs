# GitHub actions

### Project setting

Set the following environment variables in the GitHub group where your repositories are located:

* **PORTAL\_URL**: This is URL where the AppSec Portal deployed. For example [https://portal-demo.whitespots.io](https://portal-demo.whitespots.io)
* **GIT\_TOKEN**: This is your GitHub Token. You can [get](https://docs.github.com/en/actions/security-guides/automatic-token-authentication) it from your GitHub repository.
* **PORTAL\_TOKEN**: This is your AppSec Portal Auth Api Token

### Pull request commenter action

This workflow is automatically triggered when a new pull request is created or updated. The workflow checks for problems in the portal and comments the results in the pull request itself.

1. Make sure you have [entered](github-actions.md#project-setting) the values of the required variables.
2. Create a **pull-request-commenter.yml** file in your repository's `.github/workflows/` directory with the following content:

```
on:
  pull_request:
    types:
      - opened
      - synchronize

jobs:
  portal-issues:
    uses: whitespots/Whitespots-Security-Portal-CI/.github/workflows/pull-request-commenter.yml@main
    with:
      PORTAL_URL: ${{ vars.PORTAL_URL }}
    secrets:
      GIT_TOKEN: ${{ secrets.GIT_TOKEN }}
      PORTAL_TOKEN: ${{ secrets.PORTAL_TOKEN }}
```

###

### Auditor runner

This workflow performs a scan of your repository in [Auditor](broken-reference).

* Make sure you have [entered](github-actions.md#project-setting) the values of the required variables.

You can also set the value of the [`SEQUENCE`](../../auditor/settings/appsec-portal-cooperation/sequences/) variable, or the default value will be used.

* Create a **`auditor-runner.yml`**  file in your repository's `.github/workflows/` directory with the following content:

```
jobs:
  portal-issues:
    uses: whitespots/Whitespots-Security-Portal-CI/.github/workflows/auditor-runner.yml@main
    with:
      PORTAL_URL: ${{ vars.PORTAL_URL }}
    secrets:
        PORTAL_TOKEN: ${{ secrets.PORTAL_TOKEN }}
        GIT_TOKEN: ${{ secrets.GIT_TOKEN }}
```

If the portal does not have such a product, it will be created automatically.
