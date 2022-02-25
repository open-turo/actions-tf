# GitHub Action Lint

GitHub Action runs lint on a GitHub Action

## Usage

```yaml
jobs:
  build:
    steps:
      - name: Action Lint
        uses: open-turo/actions-tf/lint@v1
```

Note: by default, this action will perform actions/checkout as its first step.

## Lint Checks

This action runs the following lint checks:

- [wagoid/commitlint-github-action](https://github.com/wagoid/commitlint-github-action)
- [pre-commit/action](https://github.com/pre-commit/action)

## Notes

- This expects that `.commitlintrc.yaml` will be present to enforce [`conventional-commit`](https://github.com/wagoid/commitlint-github-action).
- Checkout must have history to ensure that commit message linting works.
