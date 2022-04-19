# GitHub Action Lint

## Description

GitHub Action that lints a Terraform based repository via [action-pre-commit](https://github.com/open-turo/action-pre-commit)

## Usage

```yaml
jobs:
  build:
    steps:
      - name: Lint
        uses: open-turo/actions-tf/lint@v3
        with:
          ## example value for terraform-cli-credentials-token provided below
          terraform-cli-credentials-token: ${{ secrets.TCCT }}
```

## Inputs

| parameter                       | description                                                | required | default        |
| ------------------------------- | ---------------------------------------------------------- | -------- | -------------- |
| checkout-repo                   | Perform checkout as first step of action                   | `false`  | true           |
| terraform-cli-credentials-token | The terraform cli config credentials token                 | `true`   |                |
| terraform-cli-config-file       | Relative or absolute path to the terraform cli config file | `false`  | ./.terraformrc |

## Runs

This action is an `composite` action.

## Lint Checks

This action runs the following lint checks:

- [action-pre-commit](https://github.com/open-turo/action-pre-commit)

## Notes

- By default, this action will perform actions/checkout as its first step.
- This expects that the `.commitlintrc.yaml` file will be present at the root level of the consumer repository to enforce [`conventional-commit`](https://github.com/wagoid/commitlint-github-action).
