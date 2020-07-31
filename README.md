# Definitions

Package definitions for JAMF packaging workflow

## Quick Links

* [Scripts Repo](https://github.com/duke-jamf/scripts)
* [Brew Casks](https://formulae.brew.sh/cask/)
* [Brew Formulae](https://formulae.brew.sh/formula/)
* [pkgbuild Manual](https://www.unix.com/man-page/osx/1/pkgbuild/)

## Usage

These definitions are designed to be used with [Duke JAMF Scripts](https://github.com/duke-jamf/scripts).
See documentation and usage at that repo.

## Format

Each definiton should follow these format guidelines.

### Slug

Definitions must have a unique and descriptive slug. This will match the name of the
definition directory and the `PKGSLUG` variable. Slugs should correspond to definition type
tokens (e.g. a Cask definition slug should be its Cask Token). If circumstances arise that
a slug needs to be created it should follow
[these conventions](https://github.com/Homebrew/homebrew-cask/blob/master/doc/cask_language_reference/token_reference.md).

### Variables

Definition directories must include a `variables` file: an executable shell script that defines
at least the following variables:

* `PKGNAME`: Full name of the product, used in the final package file. E.g. "Affinity Photo"
* `PKGSLUG`: *See above*. E.g.: "affinity-photo"
* `PKGTYPE`: One of the supported source types: `cask`, `formula`, `plist`, `tar`

Optional variables include:

* `PKGARGS`: Additional arguments to pass to the `pkgbuild` call

### Verification (optional)

Your definition may also include an executable script named `verify` to override basic
verification done by the workflow. This script should include whatever steps are necessary
to verify that a pre-existing installation of the package build was successful.

## Contributions

All definitions in this repo are destined for Duke University's JAMF Pro instance. Pull Requests
for other purposes will be closed. Issues and PRs related to the workflow itself should be
submitted to the [Scripts repo](https://github.com/duke-jamf/scripts).

New definitions should follow the **Format** defined above. See the [Scripts repo](https://github.com/duke-jamf/scripts)
for utilities to assist with generating definitions from existing sources.

All script files in a Definition should use this header:
```
##
# Duke JAMF Packaging Workflow Definition
# https://github.com/duke-jamf/definitions
##


```
