# GitHub Action: Prerelease

<!-- prettier-ignore-start -->
<!-- action-docs-description -->
## Description

GitHub Action that conditionally creates the Terraform command line interface config file that is used to authenticate with Terraform. Created only if not found.
<!-- action-docs-description -->
<!-- prettier-ignore-end -->

## Usage

```yaml
jobs:
  test:
    steps:
      - name: Enable terraform authentication
        uses: open-turo/actions-tf/auth@v3
        with:
          ## example value for terraform-cli-credentials-token provided below
          terraform-cli-credentials-token: ${{ secrets.TCCT }}
```

**IMPORTANT**: `GITHUB_TOKEN` does not have the required permissions to operate on protected branches.
If you are using this action for protected branches, replace `GITHUB_TOKEN`
with [Personal Access Token](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line).
If using the `@semantic-release/git` plugin for protected branches, avoid persisting credentials as part
of `actions/checkout@v4` by setting the parameter `persist-credentials: false`. This credential does not have the
required permission to operate on protected branches.

<!-- prettier-ignore-start -->
<!-- action-docs-inputs -->
## Inputs

| parameter | description | required | default |
| --- | --- | --- | --- |
| terraform-cli-credentials-token | The terraform cli config credentials token | `true` |  |
| terraform-cli-config-file | Relative path to the terraform cli config file | `false` | .terraformrc |
<!-- action-docs-inputs -->

<!-- action-docs-outputs -->
## Outputs

| parameter | description |
| --- | --- |
| terraform-cli-config-file-created | Indicates whether or not this action created the cli config file. |
<!-- action-docs-outputs -->

<!-- action-docs-runs -->
## Runs

This action is a `composite` action.
<!-- action-docs-runs -->

<!-- action-docs-usage  -->
<!-- action-docs-usage -->
<!-- prettier-ignore-end -->
