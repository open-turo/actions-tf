# GitHub Action Lint

GitHub Action runs lint on a terraform based GitHub repository.

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

Note: by default, this action will perform actions/checkout as its first step.

## Lint Checks

This action runs the following lint checks:

- [action-pre-commit](https://github.com/open-turo/action-pre-commit)

## Notes

- This expects that `.commitlintrc.yaml` will be present to enforce [`conventional-commit`](https://github.com/wagoid/commitlint-github-action).
- Checkout must have history to ensure that commit message linting works.
