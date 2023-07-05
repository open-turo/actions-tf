# GitHub Action Check for Breaking Changes

## Description

GitHub Action that check the current branch for any breaking change commits based on the commit message.

## Usage

```yaml
jobs:
  test:
    steps:
      - name: Check for breaking changes
        uses: open-turo/actions-tf/check-for-breaking-changes@v3
```

## Inputs

| parameter          | description                              | required | default                                          |
| ------------------ | ---------------------------------------- | -------- | ------------------------------------------------ |
| checkout-repo      | Perform checkout as first step of action | `false`  | true                                             |
| commit-base-ref    | Commit range to exclude from check       | `false`  | $GITHUB_BASE_REF                                 |
| commit-head-ref    | Commit range to include in check         | `false`  | $GITHUB_HEAD_REF                                 |
| commit-msg-pattern | Pattern used to check                    | `false`  | 'BREAKING:\|BREAKING CHANGE:\|BREAKING CHANGES:' |

## Outputs

| parameter                 | description                                                                          |
| ------------------------- | ------------------------------------------------------------------------------------ |
| contains-breaking-changes | Indicates whether or not the action found a ny breaking changes in the commit range. |

## Runs

This action is an `composite` action.
