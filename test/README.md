# GitHub Action Test

GitHub Action that runs test present within a terraform based GitHub repository.

## Usage

```yaml
jobs:
  test:
    steps:
      - name: Test
        uses: open-turo/actions-gha/test@v1
```

Note: by default, this action will perform actions/checkout as its first step.

## Test

For node based actions, it will run:

```shell
npm ci
npm test -- --coverage
```
