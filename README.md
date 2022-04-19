# `open-turo/actions-tf`

GitHub Actions for `terraform` based repositories

[![GitHub release](https://img.shields.io/github/release/Naereen/StrapDown.js.svg)](https://GitHub.com/Naereen/StrapDown.js/releases/)
[![Release date][release-date-image]][release-url]
[![GitHub latest commit](https://badgen.net/github/last-commit/Naereen/Strapdown.js)](https://GitHub.com/Naereen/StrapDown.js/commit/)
[![GitHub license](https://img.shields.io/github/license/Naereen/StrapDown.js.svg)](https://github.com/Naereen/StrapDown.js/blob/master/LICENSE)
![CI](https://github.com/open-turo/actions-tf/actions/workflows/release.yaml/badge.svg)
[![semantic-release][semantic-image]][semantic-url]
[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-yellow.svg)](https://conventionalcommits.org)

## Actions

### action: [`lint`](./lint)

Lint will run pre-commit linters against the consumer repository, optionally checking out, installing the required tools with [action-setup-tools](https://github.com/open-turo/action-setup-tools), and creating credentials for Terraform Cloud.

See usage [here](./lint/README.md#usage).

Documentation is found [here](./lint/README.md).

### action: [`release`](./release)

Release will optionally checkout the consumer repository and attempt a [Semantic Release](https://semantic-release.gitbook.io/semantic-release/usage/configuration) using the root level configuration file (e.g. `.releaserc.json`) indicating branches and plugins to use to facilitate the release.

See usage [here](./release/README.md#usage).

Documentation is found [here](./release/README.md).

### action: [`test`](./test)

Tests the terraform artifacts present in the consumer repository, using golang to perform the tests. `open-turo/action-setup-tools` will be used to install golang, and the version of golang that will be installed is governed by the version present in the `.go-version` file found in the root level of the consumer repository.

See usage [here](./test/README.md#usage).

Documentation is found [here](./test/README.md).

### action: [`auth`](./auth)

The `auth` Action is publicly available but is essentially a private Action that will conditionally create the Terraform command line interface configuration file, if it is not found. The file is typically named `.terraformrc`, but is not found under git control since it houses secrets and such. This file is needed for authentication with Terraform at runtime.

See usage [here](./auth/README.md#usage).

Documentation is found [here](./auth/README.md).

## Get Help

Each Action has a detailed README for how to use it as referenced above. Please review Issues, post new Issues against this repository as needed.

## Contributions

Please see [here](https://github.com/open-turo/contributions) for guidelines on how to contribute to this project.

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
