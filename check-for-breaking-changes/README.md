# GitHub Action: Prerelease

<!-- prettier-ignore-start -->
<!-- action-docs-description -->
## Description

GitHub Action that check the current branch for any breaking change commits based on the commit message.
<!-- action-docs-description -->
<!-- prettier-ignore-end -->

## Usage

```yaml
jobs:
  test:
    steps:
      - name: Check for breaking changes
        uses: open-turo/actions-tf/check-for-breaking-changes@v3
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
| checkout-repo | Perform checkout as first step of action | `false` | true |
| commit-base-ref | Commit range to exclude from check | `false` | $GITHUB_BASE_REF |
| commit-head-ref | Commit range to include in check | `false` | $GITHUB_HEAD_REF |
| commit-msg-pattern | Pattern used to check | `false` | BREAKING:\|BREAKING CHANGE:\|BREAKING CHANGES: |
<!-- action-docs-inputs -->

<!-- action-docs-outputs -->
## Outputs

| parameter | description |
| --- | --- |
| contains-breaking-changes | Indicates whether or not the action found any breaking changes in the commit range. |
<!-- action-docs-outputs -->

<!-- action-docs-runs -->
## Runs

This action is a `composite` action.
<!-- action-docs-runs -->

<!-- action-docs-usage  -->
<!-- action-docs-usage -->
<!-- prettier-ignore-end -->
