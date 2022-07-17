<p align="center">
  <a href="https://github.com/kevincobain2000/gobrew">
    <img alt="gobrew" src="https://imgur.com/09fGpKY.png" width="360">
  </a>
</p>
<p align="center">
  Action for gobrew.
  Setup Go for Github Actions.
</p>

**Quick Setup:** One command to install Go and manage versions.

**Hassle Free:** Doesn't require root or sudo, or shell re-hash.

**Platform:** Supports (arm64, arch64, Mac, Mac M1, and Ubuntu).

**Flexible:** Manage multiple Go versions including beta and rc.


# Yaml

```yaml
on: [push]
name: CI
jobs:
  test:
    strategy:
      matrix:
        go-version: [1.13, 1.14, 1.15, 1.16.7, 1.17, 1.18, 1.18@latest, 1.19beta1, 1.19@dev-latest, latest, dev-latest]
        os: [ubuntu-latest, macos-latest]
    runs-on: ${{ matrix.os }}
    steps:
      - uses: actions/checkout@v2
      - uses: kevincobain2000/action-gobrew@v1
        with:
          version: ${{ matrix.go-version }}

      - name: Go
        run: go version
```

# About Go Versions

