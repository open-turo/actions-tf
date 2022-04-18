# GitHub Action for Authentication with Terraform

GitHub Action that creates the Terraform credentials file with a terraform based GitHub repository if it is not already present.

## Usage

```yaml
jobs:
  test:
    steps:
      - name: Authenticate
        uses: open-turo/actions-tf/auth@v3
        with:
          ## example value for terraform-cli-credentials-token provided below
          terraform-cli-credentials-token: ${{ secrets.TCCT }}
```

Note: by default, this action will perform actions/checkout as its first step.

## Authenticate
