# GitHub Action Test

GitHub Action that runs test present within a terraform based GitHub repository.

## Usage

```yaml
jobs:
  test:
    steps:
      - name: Test
        uses: open-turo/actions-tf/test@v1
        with:
          ## example value for terraform-cli-credentials-token provided below
          terraform-cli-credentials-token: ${{ secrets.TCCT }}
```

Note: by default, this action will perform actions/checkout as its first step.

## Test
