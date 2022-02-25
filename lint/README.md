# GitHub Action Lint

GitHub Action runs lint on a GitHub Action

## Usage

```yaml
jobs:
  build:
    steps:
      - name: Checkout
        uses: actions/checkout@v2
        with:
          fetch-depth: 0
      - name: Action Lint
        uses: open-turo/actions-gha/lint@v1
```

Note: by default, this action will perform actions/checkout as its first step.

## Lint Checks

This action runs the following lint checks:

- [wagoid/commitlint-github-action](https://github.com/wagoid/commitlint-github-action)
- [pre-commit/action](https://github.com/pre-commit/action)
- [check-build](../check-build) - if the action is `node`, this checks that build has been run and committed.

## Notes

- If the repository has a `package-lock.json`
  - It will execute `npm ci` before running the `pre-commit` step.
  - It will run the `check-build` action.
- `actionlint` will be installed and in the path to ensure that https://github.com/rhysd/actionlint can be run directly.
- This expects that `.commitlintrc.yml` will be present to enforce [`conventional-commit`](https://github.com/wagoid/commitlint-github-action).
- Checkout must have history to ensure that commit message linting works.
