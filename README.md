# actions-tf

[![GitHub release](https://img.shields.io/github/release/Naereen/StrapDown.js.svg)](https://GitHub.com/Naereen/StrapDown.js/releases/)
[![Release date][release-date-image]][release-url]
[![GitHub latest commit](https://badgen.net/github/last-commit/Naereen/Strapdown.js)](https://GitHub.com/Naereen/StrapDown.js/commit/)
[![GitHub license](https://img.shields.io/github/license/Naereen/StrapDown.js.svg)](https://github.com/Naereen/StrapDown.js/blob/master/LICENSE)
![CI](https://github.com/open-turo/actions-tf/actions/workflows/release.yaml/badge.svg)
[![semantic-release][semantic-image]][semantic-url]
[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-yellow.svg)](https://conventionalcommits.org)

GitHub Actions for `terraform` based repositories

## Actions

### action: [`lint`](./lint)

```yaml
jobs:
  build:
    steps:
      - name: Lint
        uses: open-turo/actions-tf/lint@v1
        with:
          ## example value for terraform-cli-credentials-token provided below
          terraform-cli-credentials-token: ${{ secrets.TCCT }}
```

### action: [`release`](./release)

```yaml
jobs:
  build:
    steps:
      - name: Release
        uses: open-turo/actions-tf/release@v1
        with:
          ## example value for github-token provided below
          github-token: ${{ secrets.GITHUB_TOKEN }}
```

### action: [`test`](./test)

NOTES: half of time, user of `action-tf` is using golang to test terraform module, this repo mostly likely need a `.go-version` file in the root level

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

<!-- Links: -->

[version-image]: https://img.shields.io/github/package-json/v/open-turo/actions-tf.svg
[workflows-badge-image]: https://github.com/cycjimmy/semantic-release-action/workflows/Test%20Release/badge.svg
[release-date-image]: https://img.shields.io/github/release-date/open-turo/actions-tf.svg
[release-url]: https://github.com/cycjimmy/semantic-release-action/releases
[semantic-image]: https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg
[semantic-url]: https://github.com/semantic-release/semantic-release
[license-image]: https://img.shields.io/npm/l/@cycjimmy/semantic-release-action.svg
[license-url]: https://github.com/cycjimmy/semantic-release-action/blob/master/LICENSE
[changelog-url]: https://github.com/cycjimmy/semantic-release-action/blob/master/docs/CHANGELOG.md
[github-packages-registry]: https://github.com/features/packages
