# GitHub Action Generate Breaking Changes Document

<!-- action-docs-description -->

## Description

GitHub Action that creates a breaking changes document based on the configured template.

<!-- action-docs-description -->

\_\_

## Usage

```yaml
jobs:
  check:
    name: Check for breaking changes
    runs-on: [self-hosted, general-ubuntu]
    outputs:
      contains-breaking-changes: ${{ steps.check.outputs.contains-breaking-changes }}
    steps:
      - name: Check for breaking changes
        id: check
        uses: open-turo/actions-tf/check-for-breaking-changes@v3

  generate:
    needs: [check-for-breaking-changes]
    if: ${{ needs.check.outputs.contains-breaking-changes == 'true' }}
    name: Generate and validate documentation
    runs-on: [self-hosted, general-ubuntu]
    steps:
      - name: Generate breaking changes document
        id: generate
        uses: open-turo/actions-tf/generate-breaking-changes-doc@v3
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
```

<!-- action-docs-inputs -->

## Inputs

| parameter               | description                                                                                                 | required | default                                                                                                         |
| ----------------------- | ----------------------------------------------------------------------------------------------------------- | -------- | --------------------------------------------------------------------------------------------------------------- |
| checkout-repo           | Perform checkout as first step of action                                                                    | `false`  | true                                                                                                            |
| github-token            | GitHub token that can checkout the consumer repository as well push against it. e.g. 'secrets.GITHUB_TOKEN' | `true`   |                                                                                                                 |
| template-url            | Breaking changes document template URL                                                                      | `false`  | https://raw.githubusercontent.com/open-turo/standards-terraform/main/templates/breaking-changes-doc-template.md |
| pr-comment              | Adds a comment to the pull request informing that the breaking changes document was added                   | `false`  | true                                                                                                            |
| pr-comment-author-name  | The pull request comment author name                                                                        | `false`  |                                                                                                                 |
| pr-comment-author-email | The pull request comment author email                                                                       | `false`  |                                                                                                                 |

<!-- action-docs-inputs -->

<!-- action-docs-outputs -->

## Outputs

| parameter     | description                                 |
| ------------- | ------------------------------------------- |
| document-path | The relative path to the generated document |

<!-- action-docs-outputs -->

<!-- action-docs-runs -->

## Runs

This action is a `composite` action.

<!-- action-docs-runs -->
