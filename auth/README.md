# GitHub Action Auth

## Description

GitHub Action that conditionally creates the Terraform command line interface config file that is used to authenticate with Terraform. Created only if not found.

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

## Inputs

| parameter                       | description                                    | required | default      |
| ------------------------------- | ---------------------------------------------- | -------- | ------------ |
| terraform-cli-credentials-token | The terraform cli config credentials token     | `true`   |              |
| terraform-cli-config-file       | Relative path to the terraform cli config file | `false`  | .terraformrc |

## Outputs

| parameter                         | description                                                       |
| --------------------------------- | ----------------------------------------------------------------- |
| terraform-cli-config-file-created | Indicates whether or not this action created the cli config file. |

## Runs

This action is an `composite` action.
