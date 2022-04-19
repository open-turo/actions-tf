# GitHub Action Test

## Description

GitHub Action that runs tests present within a Terraform based GitHub repository.

## Usage

```yaml
jobs:
  test:
    steps:
      - name: Test
        uses: open-turo/actions-tf/test@v3
        with:
          ## example value for terraform-cli-credentials-token provided below
          terraform-cli-credentials-token: ${{ secrets.TCCT }}
```

## Inputs

| parameter                       | description                                                                                     | required | default      |
| ------------------------------- | ----------------------------------------------------------------------------------------------- | -------- | ------------ |
| checkout-repo                   | Perform checkout as first step of action                                                        | `false`  | true         |
| terraform-cli-credentials-token | The terraform cli config credentials token                                                      | `true`   |              |
| terraform-cli-config-file       | Relative path to the terraform cli config file                                                  | `false`  | .terraformrc |
| aws-access-key-id               | Access key id that grants access to AWS services. Requires aws-secret-access-key input as well. | `false`  |              |
| aws-secret-access-key           | Secret access key that grants access to AWS services. Requires aws-access-key-id input as well. | `false`  |              |

## Runs

This action is an `composite` action.

## Notes

- By default, this action will perform actions/checkout as its first step.
